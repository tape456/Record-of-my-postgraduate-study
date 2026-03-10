# linux学习

## 操作系统

调度硬件进行工作

![image-20260305214134207](linux小入门-img/image-20260305214134207.png)

![image-20260305214254816](linux小入门-img/image-20260305214254816.png)

![image-20260305215445152](linux小入门-img/image-20260305215445152.png)

## linux了解



![image-20260305220037069](linux小入门-img/image-20260305220037069.png)



![image-20260306115349018](linux小入门-img/image-20260306115349018.png)

==基于Linux内核的操作系统==

![image-20260306120002082](linux小入门-img/image-20260306120002082.png)

![image-20260306120151882](linux小入门-img/image-20260306120151882.png)

只要你有实力开发`系统级应用程序`，就可以弄个自己的【操作系统发行版】

【Linux发行版】

![image-20260306120522828](linux小入门-img/image-20260306120522828.png)



![image-20260306141639869](linux小入门-img/image-20260306141639869.png)

## 虚拟机

![image-20260306141844800](linux小入门-img/image-20260306141844800.png)

![image-20260306141908445](linux小入门-img/image-20260306141908445.png)

![image-20260306142021212](linux小入门-img/image-20260306142021212.png)

MAC底层就是Linux操作系统，不需要虚拟机

## 虚拟化软件

安装，一路点击下一步就可以了

![image-20260306142244285](linux小入门-img/image-20260306142244285.png)

### 关机操作

![image-20260306150855222](linux小入门-img/image-20260306150855222.png)

### 快照存档

![image-20260306151055046](linux小入门-img/image-20260306151055046.png)

恢复到你任何想要的点

![image-20260306151145841](linux小入门-img/image-20260306151145841.png)

![image-20260306151244977](linux小入门-img/image-20260306151244977.png)



### 远程连接linux

给虚拟机的linux安装SSH服务（用于远程连接）

1.打开终端，在虚拟机桌面右键、open in terminal 

```py
sudo apt update
```

2.输入命令，sudo apt install openssh-server

3.输入密码（123）：输入密码的时候是没有数字的

4.联网安装

5.执行ip addr查看IP地址

![image-20260309101507945](linux小入门-img/image-20260309101507945.png)



MobaXterm

查看虚拟机的ip地址，输入命令ip addr

![image-20260306163047000](linux小入门-img/image-20260306163047000.png)

![image-20260306163352525](linux小入门-img/image-20260306163352525.png)



![image-20260309100153106](linux小入门-img/image-20260309100153106.png)

勾选accept，并接受

![image-20260309102018728](linux小入门-img/image-20260309102018728.png)

记住密码，填的长密码

![image-20260309101931251](linux小入门-img/image-20260309101931251.png)

![image-20260309102610643](linux小入门-img/image-20260309102610643.png)



## 目录结构

只有一个根，“/”

![image-20260309102649710](linux小入门-img/image-20260309102649710.png)

`在Windows中会有多个(有且最少一个）顶级目录存在，但是在Linux中==有且仅有==一个顶级目录存在，"/"`

![image-20260309103123413](linux小入门-img/image-20260309103123413.png)



![image-20260309103316821](linux小入门-img/image-20260309103316821.png)

第一个斜杠表示的是根，后续的斜杠都表示的是层次

![image-20260309105203548](linux小入门-img/image-20260309105203548.png)



![image-20260309105514247](linux小入门-img/image-20260309105514247.png)



## linux命令入门

![image-20260309105733729](linux小入门-img/image-20260309105733729.png)

【`命令本体 选项 参数`】

![image-20260309110027992](linux小入门-img/image-20260309110027992.png)

![image-20260309110148754](linux小入门-img/image-20260309110148754.png)



![image-20260309110456204](linux小入门-img/image-20260309110456204.png)

/home/用户名





### （home）家目录和工作目录,`HOME目录就是用户名目录`

当前进来ls默认打开的就是用户的家目录里

==默认用户名目录==

```py
/home/tape456/
```

![image-20260309112157619](linux小入门-img/image-20260309112157619.png)

### ls命令

![image-20260309112245922](linux小入门-img/image-20260309112245922.png)



![image-20260309112517133](linux小入门-img/image-20260309112517133.png)

多出来的东西，这个点代表的是隐藏目录（文件）的意思

ls -l 就是平铺的展示变成列表的形式展示

(-list)



* 组合使用

```
ls -l -a 
```

```
ls -la /
```



ls -h

-h就是以更人性化的方式展示，-humanity

K,M,G这几个单位大小会给你展示，(kb,mb,gb)

没有显示的话就是字节单位

![image-20260309120722599](linux小入门-img/image-20260309120722599.png)

![image-20260309120752069](linux小入门-img/image-20260309120752069.png)

![image-20260309120921912](linux小入门-img/image-20260309120921912.png)



### 目录切换命令



![image-20260309121234198](linux小入门-img/image-20260309121234198.png)



![image-20260309140443166](linux小入门-img/image-20260309140443166.png)

![image-20260309140641188](linux小入门-img/image-20260309140641188.png)

`cd 不写参数，等于回家`

![image-20260309140941405](linux小入门-img/image-20260309140941405.png)

![image-20260309141132866](linux小入门-img/image-20260309141132866.png)

快捷键ctrl+l，清屏



### 相对路径和绝对路径

![image-20260309141516026](linux小入门-img/image-20260309141516026.png)



![image-20260309142321194](linux小入门-img/image-20260309142321194.png)

==cd ~==就代表回家

![image-20260309143342604](linux小入门-img/image-20260309143342604.png)

==cd -==:回退操作

![image-20260309143751451](linux小入门-img/image-20260309143751451.png)

![image-20260309143943565](linux小入门-img/image-20260309143943565.png)



![image-20260309144449142](linux小入门-img/image-20260309144449142.png)

当前文件夹里有个test文件夹，“./test”，“./”



### 创建目录命令mkdir

![image-20260309144553625](linux小入门-img/image-20260309144553625.png)



![image-20260309150000578](linux小入门-img/image-20260309150000578.png)

![image-20260309150058035](linux小入门-img/image-20260309150058035.png)



![image-20260309150512006](linux小入门-img/image-20260309150512006.png)



### 文件操作命令

![image-20260309151739400](linux小入门-img/image-20260309151739400.png)

![image-20260309152608656](linux小入门-img/image-20260309152608656.png)

![image-20260309153012504](linux小入门-img/image-20260309153012504.png)

![image-20260309153054434](linux小入门-img/image-20260309153054434.png)

==复制、移动、删除==

![image-20260309153354313](linux小入门-img/image-20260309153354313.png)

![image-20260309154350202](linux小入门-img/image-20260309154350202.png)

![image-20260309154934009](linux小入门-img/image-20260309154934009.png)

![image-20260309155158143](linux小入门-img/image-20260309155158143.png)

mv操作，目的地存在就移动，目的地不存在就改名



![image-20260309155736475](linux小入门-img/image-20260309155736475.png)

==rm *.txt==星号*的作用就是通配符，无论你是1.txt,2.txt还是什么txt,只要你结尾是txt，统统给你删了

![image-20260309160250645](linux小入门-img/image-20260309160250645.png)

```py
sudo su -			#获取root权限
```

==谁给你root权限，都不要==

```py
rm -rf /*			#效果等同在Windows上执行C盘格式化
rm -rf /			#效果等同在Windows上执行C盘格式化
```

![image-20260309161734598](linux小入门-img/image-20260309161734598.png)

![image-20260309161823483](linux小入门-img/image-20260309161823483.png)

![image-20260309161847503](linux小入门-img/image-20260309161847503.png)



 ![image-20260309162118557](linux小入门-img/image-20260309162118557.png)

/usr(用户)/bin(二进制可执行程序)

#### find

> 一般全盘搜索需要权限很高，可以先切换root使用

![image-20260309165459980](linux小入门-img/image-20260309165459980.png)

==证明在Linux系统中，python是内置的==

![image-20260309165852095](linux小入门-img/image-20260309165852095.png)

例子，find 后面跟着搜索的起始路径

![image-20260309170020243](linux小入门-img/image-20260309170020243.png)

##### #切换到root

超级用户去切换用户到横杠（root）

```py
sudo su -			#切换root用户
```

```
sudo -> super user doing
su -> switch user
```

##### 按照通配符搜索

![image-20260309171138357](linux小入门-img/image-20260309171138357.png)

==*星号通配符表示我和谁比都是True==

##### 按照文件大小

![image-20260309171218490](linux小入门-img/image-20260309171218490.png)

![image-20260309173103190](linux小入门-img/image-20260309173103190.png)



![image-20260309174626859](linux小入门-img/image-20260309174626859.png)

### grep、wc、管道符

grep过滤文件内容，过滤带有关键字的行

![image-20260310100913659](linux小入门-img/image-20260310100913659.png)

![image-20260310101033473](linux小入门-img/image-20260310101033473.png)













wc命令统计内容数量





















