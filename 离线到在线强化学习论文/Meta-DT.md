# Meta Decision Transformer(Meta-DT)



## 理解任务（做什么）

我们预训练一个上下文感知世界模型来学习紧凑的任务表示,并将其作为上下文条件注入到因果Transformer中,以指导面向任务的序列生成。

“新颖的离线元强 化学习框架,它借鉴了条件序列建模的进展,具有强大的任务表示学习能力” (Wang 等, p. 4)

“设计了一 种互补提示以在未见任务上进行有效泛化” (Wang 等, p. 4)









## 动机（为什么做这个）

“能否设计一个 离线元RL框架,在利用可扩展Transformer架构的序列建模范式进展的同时,实现对未见过 任务的高效泛化?” (Wang 等, p. 2)







## 方法原理（怎么做的）



## 实验



## 名词解释

###  “任务信念” 

解释：它指的是智能体对当前任务的一种内部表示或推断，包含了完成该任务所需的关键信息。









## 复现

服务器使用的是国内的网络

==pip不行就换源，git不行就转换链接==

requirements.txt里使用代理

> gym==0.17.3
>
> numpy==1.19.5
>
> torch==1.11.0
>
> transformers==4.5.1
>
> mujoco-py==2.1.2.14
>
> \# cython==3.0.0a10
>
> cython==0.29.37
>
> pygame==2.1.0
>
> pytest==6.2.5
>
> matplotlib==3.5.1
>
> \# git+https://github.com/dennisl88/rand_param_envs.git@4d1529d61ca0d65ed4bd9207b108d4a4662a4da0#egg=rand_param_envs
>
> tensorboard==2.13.0

```
pip install xxxxxxx   -i 清华源
git+https://ghproxy.com/https://github.com/dennisl88/rand_param_envs.git@4d1529d61ca0d65ed4bd9207b108d4a4662a4da0#egg=rand_param_envs
```

安装d4rl

```
git clone https://github.com/Farama-Foundation/d4rl.git
cd d4rl
pip install -e .
```

安装mujoco

```
To include mujoco-py in your own package, add it to your requirements like so:

mujoco-py<2.2,>=2.1
```

mujoco-py 编译错误，缺少 `X11/Xlib.h` 头文件。

```
sudo apt-get install libx11-dev libosmesa6-dev 
libgl1-mesa-glx libglfw3 patchelf -y
```

又缺一个头文件：`GL/glew.h`，需要安装 GLEW 开发库。

```
sudo apt-get install libglew-dev -y
```

虚拟屏幕安装参考：[linux安装虚拟屏幕输出-CSDN博客](https://blog.csdn.net/sevendemage/article/details/136606576)

```bash
# 1. 解压数据集到 datasets/ 目录
unzip 你的数据集压缩包.zip -d /home/litong/LizhijunWorkspace/Meta-DT/datasets/

# 2. 解压预训练世界模型到 models/ 或 checkpoints/ 目录
# 项目会保存 context encoder 和 world model 到 ./checkpoints/ 目录
mkdir -p /home/litong/LizhijunWorkspace/Meta-DT/checkpoints
unzip 你的世界模型压缩包.zip -d /home/litong/LizhijunWorkspace/Meta-DT/checkpoints/
```

```bash
unzip saves.zip -d /home/litong/LizhijunWorkspace/Meta-DT/checkpoints/
```

世界模型saves的压缩包解压到Meta-DT/底下，并且重命名为Meta-DT/checkpoints/





```
python get_datasets.py --env_type ant_dir --data_type medium --task_id_start 0 --task_id_end 5 --capacity 20000
```



==Prompt轨迹缺少next_observations字段。修复：==ai写的这段 Python 脚本就是填补了这个坑——从 `dataset_task_X.pkl`（扁平 OrderedDict）中按每 200 步切割成轨迹列表，再取前 3 条作为 prompt。这正是作者在自己机器上干了但没提交到仓库的操作。

```py
python << 'EOF'
import pickle
import numpy as np

traj_len = 200

for task_id in range(5):
    with open(f'datasets/AntDir-v0/medium/dataset_task_{task_id}.pkl', 'rb') as f:
        data = pickle.load(f)
    
    num_trajs = data['observations'].shape[0] // traj_len
    
    trajectories = []
    for i in range(num_trajs):
        s, e = i * traj_len, (i + 1) * traj_len
        trajectories.append({
            'observations': data['observations'][s:e],
            'next_observations': data['next_observations'][s:e],
            'actions': data['actions'][s:e],
            'rewards': data['rewards'][s:e],
        })
    
    prompt = trajectories[:3]
    with open(f'datasets/AntDir-v0/medium/dataset_task_prompt{task_id}.pkl', 'wb') as f:
        pickle.dump(prompt, f)
    
    print(f'Generated dataset_task_prompt{task_id}.pkl ({len(prompt)} trajectories)')

print('Done!')
EOF
```



![image-20260610150158908](Meta-DT-img/image-20260610150158908.png)

==dataset_task_promptX.pkl==从==dataset_task_0.pkl==提取

作者几乎 100% 也是用同样的逻辑切的——因为数据格式是确定的，切割方式也只有一种正确做法。只是他没把这段代码放进 GitHub。



**训练完成后的完整复现路线**

`train_meta_dt.py` 已经内置了训练 + 评估 + TensorBoard 日志，训练完后结果在 `results/` 目录下。

当前你的 AntDi当前你的 AntDir-v0 few-shot 跑完后，接着做：r-v0 few-shot 跑完后，接着做：

### ① Zero-shot Meta-DT

```bash
python train_meta_dt.py --env_type ant_dir --env_name AntDir-v0 --zero_shot True --data_quality medium --num_tasks 5 --num_train_tasks 3
```

当 `--zero_shot True` 时，模型不依赖 prompt 轨迹，直接根据上下文编码器进行 zero-shot 泛化。

### ② 其他环境（完整复现论文需要）

| 环境              | Few-shot 命令                                                |
| ----------------- | ------------------------------------------------------------ |
| HalfCheetahVel    | `python train_meta_dt.py --env_type cheetah_vel --env_name HalfCheetahVel-v0 --zero_shot False --data_quality medium` |
| HalfCheetahDir    | `python train_meta_dt.py --env_type cheetah_dir --env_name HalfCheetahDir-v0 --zero_shot False --data_quality medium` |
| HopperRandParams  | `python train_meta_dt.py --env_type hopper --env_name HopperRandParams-v0 --zero_shot False --data_quality medium` |
| WalkerRandParams  | `python train_meta_dt.py --env_type walker --env_name WalkerRandParams-v0 --zero_shot False --data_quality medium` |
| Reach (MetaWorld) | `python train_meta_dt.py --env_type reach --env_name Reach-v2 --zero_shot False --data_quality medium` |

每个环境也需要先完成数据收集 + 生成数据集，然后各跑一个 few-shot 和 zero-shot。

### ③ 论文图表怎么来的？

==训练脚本的日志目录是 **`runs/`**，不是 `results/`。==

训练过程中 TensorBoard 自动记录到 `results/` 目录。运行：

```bash
tensorboard --logdir runs/ --port 6006 --bind_all
```

如果你在 Windows 上开了代理/VPN

也可能是代理占用了 6006。关闭代理再试，或者干脆换个冷门端口：

```
ssh -L 18888:localhost:6006 litong@9.tcp.vip.cpolar.cn -p 13035
```

浏览器打开 **`http://localhost:18888`**,可以看到：

| 指标                 | 含义                                             |
| -------------------- | ------------------------------------------------ |
| `train/loss`         | 训练损失曲线                                     |
| `return/train tasks` | 训练任务平均回报（对应论文 Table 里的 Train 列） |
| `return/test tasks`  | 测试任务平均回报（对应论文 Table 里的 Test 列）  |

论文里的学习曲线图、Table 数据就是从这些 TensorBoard 日志中提取的。





