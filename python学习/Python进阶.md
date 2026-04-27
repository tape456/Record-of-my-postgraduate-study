

# Python进阶

![image-20260310110046210](Python进阶-img/image-20260310110046210.png)

## 1.面向对象和面向过程

* 编程思想

  > 就是人们利用计算机来解决问题的思维

* 分类

  * 面向过程

  > 它是一种编程思想，强调的是以步骤（过程）为基础完成各种操作

  * 面向对象

    > **参考思路**：概述，思想特点，举例，总结
    >
    > 它是一种编程思想，强调的是以**对象**为基础完成各种操作，他是基于面向过程的
    >
    > 说到面向对象，不得不提的就是它的三大思想特点：
    >
    > 1. 更符合人们的思考习惯
    > 2. 把复杂的事情简单化
    > 3. 把程序员从执行者变成指挥者
    >
    > 举例：越符合当时的场景越好，例如：买电脑、洗衣服...
    >
    > 总结：万物皆对象

## 2.面向对象的三大特性

面向对象的三大特征：封装、继承、多态 

![image-20260312103043698](Python进阶-img/image-20260312103043698.png)

多态：一象多用（解耦）`高内聚低耦合`

![image-20260312103133510](Python进阶-img/image-20260312103133510.png)

### 封装

隐藏对象的属性和实现细节，仅对外提供公共的访问方式

举例：手机、电脑、函数、类=属性+行为

提高代码的安全性，（私有化）（代码量增加了）

提高代码的复用性，（函数）

![image-20260316102709789](Python进阶-img/image-20260316102709789.png)

### 继承

子类继承父类的成员，例如：属性，行为

![image-20260316102751947](Python进阶-img/image-20260316102751947.png)

![image-20260316103305471](Python进阶-img/image-20260316103305471.png)

### 多态

![image-20260316103435820](Python进阶-img/image-20260316103435820.png)

![image-20260316103559294](Python进阶-img/image-20260316103559294.png)





## self关键词

学生对于人是对象，对于张三是类

![image-20260316210212618](Python进阶-img/image-20260316210212618.png)

只要是我们写到类里面的函数，一定要加一个self

括号是继承的写法，比如BiYaDi（car）



地址值是根据你的内存地址，结合你（对象）的属性和行为算出来的一个int值，`id（内存地址）=地址值`

![image-20260316210231918](Python进阶-img/image-20260316210231918.png)

> self 就是 **代表本类当前对象的引用**

![image-20260316210427892](Python进阶-img/image-20260316210427892.png)

![image-20260316210505773](Python进阶-img/image-20260316210505773.png)

![image-20260316210540602](Python进阶-img/image-20260316210540602.png)

![image-20260316211718211](Python进阶-img/image-20260316211718211.png)

## 类内self调用

self就代表c1这个对象（c1内存地址）

类内之所以可以用self.，本质上还是类内的self等于类外的这个对象，谁调用，self就代表谁

![image-20260316211747624](Python进阶-img/image-20260316211747624.png)



![image-20260316214111184](Python进阶-img/image-20260316214111184.png)

![image-20260316214439230](Python进阶-img/image-20260316214439230.png)



## 添加和获取对象的属性（类外`获取和设置`对象的属性）

`类外设置属性，是只给当前对象设置属性`



![image-20260316214516464](Python进阶-img/image-20260316214516464.png)

![image-20260316214556864](Python进阶-img/image-20260316214556864.png)

属性是名词

![image-20260316214724144](Python进阶-img/image-20260316214724144.png)



只有python可以【在类外，只给当前`一个对象`添加属性】

![image-20260316221241279](Python进阶-img/image-20260316221241279.png)



## 类内部获取对象属性(类内`只能获取`对象的属性)

**类内** **设置** 对象属性要用到魔法方法

![image-20260316221545189](Python进阶-img/image-20260316221545189.png)



![image-20260316223426957](Python进阶-img/image-20260316223426957.png)

--day1上午--





## 魔法方法

因为这个类我们以后太常用了，所以他里边有默认的手段和方式可以让我们来用，那这个我们把它称之为魔法方法（就是在特定场景下，自动被调用的功能，无需你自个来写，只要满足条件，自动触发）

\__init___

_\__str__
\__del__

![image-20260319205817221](Python进阶-img/image-20260319205817221.png)

```py
# 如果是只有前面是下划线的__init,这就叫做私有方法,一般不让用
# 私有方法是只能在定义它的类内部访问和调用的方法，外部或其他类不能直接访问。通常用于封装类的内部实现细节，避免外部代码的干扰。
```



> 所有的魔法方法只能是在特定场景下自动调用

### init方法

![image-20260319205838845](Python进阶-img/image-20260319205838845.png)

```py
# 在（每次）创建对象的时候，会自动触发该类的_init_函数

```



> 抽象方法是什么?
>
> 简单来说，**抽象方法是一种 “只定义规则、不实现具体逻辑” 的方法**—— 它只告诉你 “需要做什么”，但不告诉你 “具体怎么做”，必须由继承它的子类来实现具体逻辑。抽象方法通常存在于 “抽象类” 中，是面向对象编程里规范子类行为的核心手段。
>
> 你可以把抽象方法理解成：老师给全班同学布置了一道 “作文题”（抽象方法），题目要求是 “写一篇关于春天的作文”（定义规则），但每个同学要自己写具体的内容（子类实现），不写的话就 “不合格”（代码报错）。
>
> #### 先理清两个关联概念
>
> 1. **抽象类**：包含抽象方法的类，本身不能直接实例化（不能创建对象），只能作为父类被继承。
> 2. **抽象方法**：在抽象类中声明，但没有具体实现（只有方法名和参数，没有方法体），子类必须重写（实现）这个方法才能实例化。



```python
class Car():
    # 无参的__init__方法,就相当于没人光顾石膏娃娃店,老板闲的没事就会先上好底色(石膏娃娃),如果要修改属性值,就要重新覆盖
    # def __init__(self):
    #     self.color="黑色"
    #     self.number=4

    # 有参的__init__方法,就相当于有人光顾石膏娃娃店,石膏娃娃就是新的没有颜色,颜色就是自己给的(创建(类的)对象的时候必须要给参数)
    def __init__(self,color,number):
        self.color=color
        self.number=number

    # def __str__(self):
        # return f"self.color:{self.color},self.number:{self.number}"

    # def __del__(self):
        # print(f"{self}对象被删除")


c1=Car("绿色",6)      # 创建(类的)对象:     对象名=类()
print(c1)       # 如果__str__方法没有定义,那么打印对象时,会打印对象的地址
print(c1.color)     #类外调用属性值 :    对象名.属性名
c1.color="蓝色"
print(c1.color)     # 类外修改属性值 :    对象名.属性名 = 属性值
print(c1.number)

```







![image-20260319210747684](Python进阶-img/image-20260319210747684.png)



![image-20260319212232676](Python进阶-img/image-20260319212232676.png)



![image-20260319212254378](Python进阶-img/image-20260319212254378.png)



![image-20260319212310748](Python进阶-img/image-20260319212310748.png)











### str方法

```

```



![image-20260319212405683](Python进阶-img/image-20260319212405683.png)

### del方法

释放类的对象资源的时候，自动调用del



![image-20260319212512611](Python进阶-img/image-20260319212512611.png)



![image-20260319212704714](Python进阶-img/image-20260319212704714.png)





![image-20260319205614752](Python进阶-img/image-20260319205614752.png)





## 魔法方法综合案例

### 减肥案例

![image-20260421115233173](Python进阶-img/image-20260421115233173.png)

```py
"""
例如，小明同学当前体重是100kg。每当他跑步一次时，则会减少0.5kg；
每当他大吃大喝一次时，则会增加2kg。请试着采用面向对象方式完成案例。

分析:
    类名:           Student
    对象名:         xm
    属性(名词):     当前体重,current_weight
    行为(动词):     跑步,吃饭
"""
# 1.定义学生类
class Student:
    # 2.在魔法方法init中，完成：对象的属性的初始化
    def __init__(self):
        self.current_weight = 100

    # 3.每当他跑步一次时，则会减少0.5kg
    def run(self):
        print("疯狂跑步..减少0.5")
        self.current_weight-=0.5    # 体重减小

    # 4.大吃大喝
    def eat(self):
        print("大吃大喝...增加2")
        self.current_weight+=2

    # 5.重写魔法方法str,打印属性值,即:当前体重
    def __str__(self):
        # return "当前体重:%s" % self.current_weight
        return f"当前体重:{self.current_weight}kg!"

# 6.测试
# 如果未来你的这个模块要被别人调,那你是不是要把测试代码 写到main里边
if __name__ == '__main__':
    # 6.1 创建对象
    xm = Student()

    # 6.2 跑步
    xm.run()
    xm.run()
    # 6.3吃喝
    xm.eat()

    # 6.4当前体重
    print(xm)
```

### 烤地瓜案例

> 分析类
>
> 属性和行为

<img src="Python进阶-img/image-20260421171153826.png" alt="image-20260421171153826" style="zoom:67%;" />



<img src="Python进阶-img/image-20260421171239175.png" alt="image-20260421171239175" style="zoom:67%;" />



<img src="Python进阶-img/image-20260421171308353.png" alt="image-20260421171308353" style="zoom:67%;" />



![image-20260421174607231](Python进阶-img/image-20260421174607231.png)

```py
"""
案例:烤地瓜

需求:
    1.定义地瓜类 -> SweetPotato
    2.属性:被烤时间cook_time,烘焙状态cook_state,调料 condiments
    3.行为:烘烤cook(),添加调料 add_condiment()
    4.魔法方法:init() -> 初始化属性, str() -> 打印地瓜信息
    5.规则:
        烘烤时间        地瓜状态
        [0,3)           生的          包左不包右,前闭后开
        [3,7)           半生不熟
        [7,12)          熟了
        [12,∞]            糊了
"""
# 1.定义地瓜类 -> SweetPotato
class SweetPotato:
    # 2.在魔法方法__init__()中,初始化地瓜的属性
    # 那如果是从别的炉子拿过来呢，有参也行吧，设置一个默认值就行
    def __init__(self):
        self.cook_time = 0
        self.cook_state = "生的"
        self.condiments = []

    # 3.具体的烘烤动作
    def cook(self,time):
        # 3.1根据烘烤时间,判断地瓜的 烘烤状态
        if time<0:
            print("无效值")
        else:
            # 3.2修改地瓜的 烘烤时间
            self.cook_time += time
            # 3.3根据烘烤时间,判断地瓜的 烘烤状态
            if 0<=self.cook_time<3:
                self.cook_state = "生的"
            elif 3<=self.cook_time<7:
                self.cook_state = "半生不熟"
            elif 7<=self.cook_time<12:
                self.cook_state = "熟了"
            else:
                self.cook_state = "糊了"
    # 4.添加调料 add_condiment()
    def add_condiment(self,condiment):
        self.condiments.append(condiment)

    # 5.重写str()方法,打印地瓜信息
    def __str__(self):
        return f"烘烤时间:{self.cook_time},烘烤状态:{self.cook_state},调料:{self.condiments}"

# 6.测试
if __name__ == '__main__':
    # 7.创建地瓜对象
    dg=SweetPotato()

    # 8.具体的烘烤动作
    # dg.cook(-3)
    dg.cook(3)
    dg.cook(5)
    dg.cook(7)

    # 9.添加调料
    dg.add_condiment("芥末/辣根")
    dg.add_condiment("鱼腥草,折耳根")
    dg.add_condiment("豆汁")
    dg.add_condiment("鲱鱼罐头")

    # 10.打印地瓜状态
    print(dg)
```





## 定义类的三种格式p19

多层继承

```py
# 第一种(常用)
class 类名：
	pass
# 第二种
class 类名():
    pass
# 第三种(常用)
class 类名(父类名):
	pass
```



![image-20260323100531578](Python进阶-img/image-20260323100531578.png)

> 定义成私有方法就不会被继承了?
>
> 定义成私有也会继承下来，只能被名称修饰了，你调错了。

![image-20260323100713164](Python进阶-img/image-20260323100713164.png)

## 继承入门p20、单继承p21

![image-20260323100801283](Python进阶-img/image-20260323100801283.png)



![image-20260326213613985](Python进阶-img/image-20260326213613985.png)









![fbeb6b5d0e5033ead1532725531dce38](Python进阶-img/fbeb6b5d0e5033ead1532725531dce38.jpg)





![image-20260323100841276](Python进阶-img/image-20260323100841276.png)

![image-20260326214754572](Python进阶-img/image-20260326214754572.png)



> 父类的私有属性和私有方法是不能继承的?
>
> 可以继承，Python中的私有是约定式的





## 多继承p22

>  从左往右就近原则

![image-20260323100942168](Python进阶-img/image-20260323100942168.png)



![image-20260323101023567](Python进阶-img/image-20260323101023567.png)

当一个类有多个父类时，默认使用**第一个父类**的**同名属性和方法**

## 多继承中的继承顺序p23

> 扩展mro机制

![image-20260326215304747](Python进阶-img/image-20260326215304747.png)



![image-20260323101129471](Python进阶-img/image-20260323101129471.png)

> 查看(类的)引用顺序的两种途径,注意是:
>
> **类名**.属性名		# Prentice.\__mro__
>
> **类名**.方法名()	     # Prentice.mro()
>
> 注意是类名点出来的,不是对象名!!

```py
class Master:
    def __init__(self):
        self.kongfu= '古法配方'

    def make_cake(self):
        print(f"运用{self.kongfu}制作煎饼果子")

class School:
    def __init__(self):
        self.kongfu="黑马配方"

    def make_cake(self):
        print(f"运用{self.kongfu}制作煎饼果子")

class Prentice(School,Master):
    pass

xm=Prentice()
# print(xm.kongfu)    # 访问属性：对象名.属性名
xm.make_cake()          # 运用黑马配方制作煎饼果子

class Master:
    def __init__(self):
        self.kongfu= '古法配方'

    def make_cake(self):
        print(f"运用{self.kongfu}制作煎饼果子")

class School:
    def __init__(self):
        self.kongfu="黑马配方"

    def make_cake(self):
        print(f"运用{self.kongfu}制作煎饼果子")

class Prentice(School,Master):
    pass

xm=Prentice()
# print(xm.kongfu)    # 访问属性：对象名.属性名
xm.make_cake()          # 运用黑马配方制作煎饼果子

print(Prentice.__mro__) # (<class '__main__.Prentice'>, <class '__main__.School'>, <class '__main__.Master'>, <class 'object'>)
print(Prentice.mro())   # (<class '__main__.Prentice'>, <class '__main__.School'>, <class '__main__.Master'>, <class 'object'>)

```

> 徒弟类里没有konhfu和makecake，使用的话遵循就近原则

![](Python进阶-img/image-20260323103327211.png)

![image-20260323103516509](Python进阶-img/image-20260323103516509.png)







## 子类重写父类功能(第二章p1)

![image-20260326215755563](Python进阶-img/image-20260326215755563.png)

> 和java不一样,java不能重写属性,python可以重写属性

![image-20260323203226454](Python进阶-img/image-20260323203226454.png)

> self指的是对象，而调用的master方法，里面的self调到徒弟里面去了归徒弟管，所以要调父类的话,要构造方法把值改了，改成master的值

![image-20260326215434777](Python进阶-img/image-20260326215434777.png)

> 使用变量遵循就近原则，我自个类有，就拿来用，没有的话找近的父类，近的父类没有就往下继续找

![image-20260326210223229](Python进阶-img/image-20260326210223229.png)

>  那老师为啥报警告?
>
> 原因是因为:他告诉你,在父类中已经有对应的属性了,你的子类是不是还要去做这个事情啊,那就有点多此一举
>
> 警告归警告,但是执行依然没报错





## 子类访问父类成员_方式1(p2)

> 1. 父类名.父类方法名(self)	# 精准访问，想找哪个父类，就调哪个父类

![image-20260326210541930](Python进阶-img/image-20260326210541930.png)



















![image-20260323204109845](Python进阶-img/image-20260323204109845.png)

> 因为self本类当前对象的引用还是Prentice的init里的所以这里打印的是独创煎饼果子



![image-20260323204237746](Python进阶-img/image-20260323204237746.png)

> 就看self是谁，因为已经执行了一次init换成了master属性了

self像指针，按指针理解简简单单

其实就是 如果不加 Master.\__init__(self)， 用的就是子类自己的 init,

> self一直没变过,只不过是调用了父类的方法,**父类的属性覆盖了自己的属性**



![image-20260326211309271](Python进阶-img/image-20260326211309271.png)

>  说的那么复杂，直接说**父类的初始值覆盖掉子类的初始值**就好了

![image-20260326212531979](Python进阶-img/image-20260326212531979.png)



![image-20260326212652515](Python进阶-img/image-20260326212652515.png)



## 子类访问父类成员_方式2(p3)

```py
# 思路:
#    1.父类名.父类函数名(self)   精准访问，想找哪个父类，就调哪个父类.
#    2.super().父类函数名()    只能访问最近的那个父类，有就用，没有就往后继续查找
```

>  2.super().父类方法名()     # 只能访问最近的那个父类，没有就往后一直找方法

![image-20260326212857829](Python进阶-img/image-20260326212857829.png)









![93807e6867c45e2f7692619bb2f702dd](Python进阶-img/93807e6867c45e2f7692619bb2f702dd.jpg)





![image-20260326220744402](Python进阶-img/image-20260326220744402.png)

![image-20260326220814141](Python进阶-img/image-20260326220814141.png)

>  我就想通过super小括号的方式,直接访问第二个或者第三个父类的成员,这个能不能做到?
>
> 做不到!
>
> super()它只能从前往后去初始化,前面没有才会往后找,前面有的情况下,不会找master



![image-20260326221024234](Python进阶-img/image-20260326221024234.png)





## 多层继承p4

![image-20260326221349406](Python进阶-img/image-20260326221349406.png)



![image-20260326221454180](Python进阶-img/image-20260326221454180.png)



> self是本类当前对象的引用
>
> super代表父类





## 封装





![10caeb09a45fac8c90d266b4430f52b0](Python进阶-img/10caeb09a45fac8c90d266b4430f52b0.jpg)





![34602ee7d5e62d3bdf69c3c5022e49f8](Python进阶-img/34602ee7d5e62d3bdf69c3c5022e49f8.jpg)





![image-20260326221809918](Python进阶-img/image-20260326221809918.png)

### 定义和获取私有属性

![ca50741430d72f44a1a02deaa44a0015](Python进阶-img/ca50741430d72f44a1a02deaa44a0015.jpg)

```py
class Master:
    def __init__(self):
        self.kongfu="古法配方"

    def make_cake(self):
        print(f"使用{self.kongfu}制作煎饼果子")


class School:
    def __init__(self):
        self.kongfu="黑马配方"

    def make_cake(self):
        print(f"运用{self.kongfu}制作煎饼果子")


class Prentice(School,Master):
    def __init__(self):
        self.kongfu="独创配方"
        self.__money=20000

    def make_cake(self):
        print(f"使用{self.kongfu}制作煎饼果子")

    def get_money(self):
        return self.__money

    def set_money(self,money):
        self.__money = money

class Tusun(Prentice):
    pass

ts=Tusun()
# print(ts.__money)       # 报错
print(ts.get_money())       # 获取私有属性 20000
ts.set_money(100)           # 设置私有属性
print(ts.get_money())       # 获取更新后的私有属性 100
```

> **在类内写获取属性,设置属性值的**(留给外面访问的)**接口** 
>
> get_属性值(名)
>
> **在类内，私有属性和私有方法想怎么用就怎么用**

![image-20260326222245315](Python进阶-img/image-20260326222245315.png)



![7e2dbfcc76a54f5c4e60378e63c8764d](Python进阶-img/7e2dbfcc76a54f5c4e60378e63c8764d.jpg)

```py
class Master:
    def __init__(self):
        self.kongfu="古法配方"

    def make_cake(self):
        print(f"使用{self.kongfu}制作煎饼果子")


class School:
    def __init__(self):
        self.kongfu="黑马配方"

    def make_cake(self):
        print(f"运用{self.kongfu}制作煎饼果子")


class Prentice(School,Master):
    def __init__(self):
        self.kongfu="独创配方"

    # 定义私有方法
    def __make_cake(self):
        print(f"使用{self.kongfu}制作煎饼果子")

    def make(self):     # 类内,访问私有方法的接口
        self.__make_cake()

class Tusun(Prentice):
    pass

ts=Tusun()
ts.make()   # 使用独创配方制作煎饼果子
```





## 多态

### 定义

> 同样的函数,传入不同的对象,得到不同的状态

![image-20260405140658995](Python进阶-img/image-20260405140658995.png)

> 你这car是自己写了个speak方法，执行外面函数不就还是Car().speak调用的嘛，两个完全没有关系的东西怎么多态？也就是说你的Car类既没有重写、继承，又没有指向，就是个普通类，哪来的继承？
>
> 类型注解

![image-20260405141753403](Python进阶-img/image-20260405141753403.png)

![image-20260405141850812](Python进阶-img/image-20260405141850812.png)

> 这句话的意思就是你将来调我这个函数，你必须是我animal的子类

我感觉是python没有变量定义造成的。

> Python做不到真正意义上的多态

![image-20260405141959536](Python进阶-img/image-20260405141959536.png)



![image-20260405144758247](Python进阶-img/image-20260405144758247.png)

> 这个地方的多态,他无法精准地限定类型

![image-20260405144846165](Python进阶-img/image-20260405144846165.png)



![image-20260405144921692](Python进阶-img/image-20260405144921692.png)



![image-20260405144954671](Python进阶-img/image-20260405144954671.png)

> java抽象类要全部实现

![image-20260405145048289](Python进阶-img/image-20260405145048289.png)

> Python里子类对于父类的抽象方法不需要全部实现

继承 重写 **父类引用指向子类对象**

![image-20260405145135888](Python进阶-img/image-20260405145135888.png)



![image-20260405145443341](Python进阶-img/image-20260405145443341.png)

### 属性、类属性、类方法、静态方法

![image-20260405145633145](Python进阶-img/image-20260405145633145.png)



![image-20260405145730621](Python进阶-img/image-20260405145730621.png)



![image-20260405145948114](Python进阶-img/image-20260405145948114.png)



![image-20260405150829208](Python进阶-img/image-20260405150829208.png)



![image-20260405150952041](Python进阶-img/image-20260405150952041.png)



![image-20260405151105626](Python进阶-img/image-20260405151105626.png)

> 如果要修改**类变量**的值，只能通过 **类名.** 的方式实现

> 对象属性，他的访问和设置都只能通过 对象名点
> 但是类属性如果你要访问，对象名点也行，类名点也行，但是你想修改只能通过类名点

> 定义到函数外，但是在类中的叫类属性
>
> 写到init里面的叫对象属性

![image-20260405151420035](Python进阶-img/image-20260405151420035.png)



![image-20260405151537172](Python进阶-img/image-20260405151537172.png)

### 类方法,静态方法

> 1.类方法,就是属于类本身,不属于某个对象的方法,不用创建对象,直接用类就能调用
>
> 2.类方法,操作类属性,不操作实例.类属性是所有对象共享的,类方法可以安全修改,读取这类的全局属性

![image-20260405152938782](Python进阶-img/image-20260405152938782.png)

> 类方法要求第一个参数必须是类对象

类方法可以访问类属性，不能访问实例属性；而静态方法两个属性都不能访问

类方法和静态方法的区别只在于访问类属性时，类方法简便一点cls.类属性，而静态方法复杂一点，要类名.类属性

区别就只在于第一个参数表示类对象

静态方法常用，用类名点类属性就能用了

【当然有区别，这两种方法不能直接访问和修改实例属性，他们访问的是类的属性

> self是表示对象的引用，指向实例对象，cls表示类的引用，指向类

![image-20260405153907127](Python进阶-img/image-20260405153907127.png)

如果要往静态方法加定义参数，也是可以的



## 学生管理系统

> 名词提取法,提取名词作为类
>
> CMS(Content Management System)

<img src="Python进阶-img/image-20260421194214983.png" alt="image-20260421194214983" style="zoom:50%;" />

![image-20260405153931589](Python进阶-img/image-20260405153931589.png)

> 3个py文件

![image-20260421193330903](Python进阶-img/image-20260421193330903.png)

> 

![image-20260408113833901](Python进阶-img/image-20260408113833901.png)

> 

![image-20260408115017494](Python进阶-img/image-20260408115017494.png)

> 

![image-20260408115042104](Python进阶-img/image-20260408115042104.png)

> 学生管理系统面向对象版思路分析

### 学生管理系统实践

<img src="Python进阶-img/image-20260421194245894.png" alt="image-20260421194245894" style="zoom:67%;" />

> 

![image-20260421194350594](Python进阶-img/image-20260421194350594.png)

```py
"""
该文件用于记录 学生类,学生的属性信息为:姓名,性别,年龄,手机号,描述信息

"""
# 1.定义学生类.
class Student:
    # 2.定义魔法方法,初始化属性信息
    def __init__(self,name,gender,age,phone,desc):  # describe = desc描述信息
        """
        该魔法方法,用于初始化 属性信息
        :param name:        学生姓名
        :param gender:      性别
        :param age:         年龄
        :param phone:       手机号
        :param desc:        描述信息
        """
        self.name= name
        self.gender = gender
        self.age = age
        self.phone = phone
        self.desc = desc

    # 如果未来我想快速的打印这个对象的信息,还需要__str__
    # 3.定义魔法方法,用于打印学生信息
    def __str__(self):
        """
        该魔法方法,用于打印学生信息
        :return:
        """
        return f"姓名: {self.name},性别: {self.gender},年龄: {self.age},手机号: {self.phone},描述信息: {self.desc}"

# 4.测试(手机号不需要涉及到算数运算,所以就用字符串类型)
# 在调用者中,不执行被调用者的测试代码
if __name__ == '__main__':
    s=Student('乔峰','男',18,'13112345678','丐帮帮主')
    print(s)
```



![image-20260421200834796](Python进阶-img/image-20260421200834796.png)

> 有个属性记录学生列表

![image-20260421200921295](Python进阶-img/image-20260421200921295.png)



![image-20260421200938741](Python进阶-img/image-20260421200938741.png)





![image-20260421201003486](Python进阶-img/image-20260421201003486.png)



![image-20260421201018144](Python进阶-img/image-20260421201018144.png)



![image-20260421201034666](Python进阶-img/image-20260421201034666.png)



![image-20260421203857479](Python进阶-img/image-20260421203857479.png)

> 接下来把这好几个函数补齐就行了
>
> 那我刚才做的这个事，在公司中一般就是公司的架构师（项目经理），就是把整个项目的架构快速搭起来，然后就由程序员往里边摞代码

![image-20260421204126344](Python进阶-img/image-20260421204126344.png)

> 我们应该把你的测试代码,是不是应该放到另外一个文件,叫做main.py才合适



==原来如此==

<img src="Python进阶-img/image-20260421205211919.png" alt="image-20260421205211919" style="zoom:67%;" />

> 你看你的学生这个对象,将来在管理里边被访问,管理里边他写的功能将来在主入口里边去访问,对于外界的用户来讲,他将来干的事情就是直接去访问你的main文件,那这样的话是不是作为程序的入口,去调你的管理文件,去调你的学生对象
>
> 所以呢我们将来的代码要写到main里边

<img src="Python进阶-img/image-20260421205249502.png" alt="image-20260421205249502" style="zoom:50%;" />

> 虽然main文件的流程和刚刚每个子模块的测试代码差不多相同,但是在实际开发中,你要单独的把它写到一个文件中才可以

学生管理系统_入口文件

如下的代码是写到**main.py**文件中的

```py
"""
该文件 用作程序的入口文件.
"""
from studentcms import StudentCMS

# 程序的主入口
if __name__ == '__main__':
    # 1.创建学生管理系统对象
    stu_cms=StudentCMS()
    # 2.启动程序即可
    stu_cms.start()
```



### 13.学生管理系统_功能实现

* 添加学生

<img src="Python进阶-img/image-20260421210107159.png" alt="image-20260421210107159" style="zoom: 50%;" />



让用户录入信息，我们接收封装往里边塞，就可以了

```py
# 4.定义函数,实现添加学生信息功能
def add_student(self):
    # 4.1提示用户输入学生信息,并接收
    name = input("请输入学生姓名:")
    gender = input("请输入学生性别:")
    age = int(input("请输入学生年龄:"))    # 学生年龄是一个整数
    phone = input("请输入学生手机号:")
    desc=input("请输入学生描述信息:")
    # 4.2把上述的信息封装成学生对象
    stu=Student(name,gender,age,phone,desc)
    # 4.3学生对象添加到列表中
    self.stu_list.append(stu)
    # 4.4提示
    print(f'添加{name}学生信息成功!\n')
```

* 查看所有学生信息

<img src="Python进阶-img/image-20260421212703279.png" alt="image-20260421212703279" style="zoom:50%;" />

> 重写__str__,就可以直接打印,打印类对象就打印了我们重写好的那一堆类对象的属性

```py
# 8.定义函数,实现查询所有学生信息功能
def search_all_student(self):
    # 8.1判断列表长度是否为0，如果为0,提示用户暂无学生信息，请添加后查询
    if len(self.stu_list)==0:
        print("暂无学生信息，请添加后查询\n")
    else:
        # 8.2如果长度不为0 遍历列表，打印出所有的学生信息
        for stu in self.stu_list:
            print(stu)
        print()     # 为了格式好看,在星星行上面加一行空行
```

* 删除学生的信息

![image-20260421214526038](Python进阶-img/image-20260421214526038.png)

```py
# 5. 定义函数,实现删除学生信息功能
def del_student(self):
    # 5.1提示用户输入要删除的学生的姓名,并接收
    del_name = input("请输入要删除的学生姓名:")
    # 5.2遍历列表,找到要删除的学生
    for stu in self.stu_list[:]:
        # 5.3如果当前的学生的姓名 和 要删除的学生相同,则删除该学生
        if del_name == stu.name:
            self.stu_list.remove(stu)
            print(f"学员{del_name} 删除成功!\n")
            break
    else:
        # 走到这里,说明没有走break,即:没有找到这个学生
        print(f"没有找到学员{del_name},请检查后重新删除!\n")
```



### 14.修改学生信息

```py
# 6. 定义函数,实现修改学生信息功能
    def update_student(self):
        # 6.1提示用户输入要修改的学生的姓名,并接收
        upd_name = input("请输入要修改的学生姓名:")
        # 6.2遍历列表,找到要修改的学生,并修改
        for stu in self.stu_list[:]:
            # 6.3如果当前的学生的姓名 和 要修改的学生相同,则修改该学生
            if upd_name == stu.name:
                # 6.4提示用户录入该学员新的信息
                stu.gender=input("请录入修改后的性别:")
                stu.age=int(input("请录入修改后的年龄:"))
                stu.phone=input("请录入修改后的手机号:")
                stu.desc=input("请录入修改后的描述信息:")

                print(f"学员 {upd_name} 修改成功!\n")
                break
        else:
            # 走到这里,说明没有走break,即:没有找到这个学生
            print(f"没有找到学员{upd_name},请检查后重新修改!\n")
```



### 15.查询单个学生信息

```py
# 7.定义函数,实现查询单个学生信息功能
    def search_one_student(self):
        # 7.1提示用户输入要查找的学生的姓名,并接收
        search_name = input("请输入要查找的学生姓名:")
        # 7.2遍历列表,找到要查找的学生,并打印出该学生信息
        for stu in self.stu_list[:]:
            # 7.3如果当前的学生的姓名 和 要查找的学生相同,则查找该学生(其实就打印)
            if search_name == stu.name:
                print(stu,end='\n\n')
                break
        else:
            # 走到这里,说明没有走break,即:没有找到这个学生
            print(f"没有找到学员{search_name},请检查后重新查找!\n")
```

### 16.扩展\__dict__

> 往文件里写学生信息还好写,但一会你从文件里边是不是还得能读出来才可以啊,
>
> 所以说扩展一个内容,\__dict__

![image-20260422153504884](Python进阶-img/image-20260422153504884.png)

```py
class A(object):
    a=0
    def __init__(self):
        self.b=1
aa=A()
# 返回类内 所有属性和方法对应的字典
print(A.__dict__)
# {'__module__': '__main__',
# 'a': 0,
# '__init__': <function A.__init__ at 0x000001D08CD745E0>,
# '__dict__': <attribute '__dict__' of 'A' objects>,
# '__weakref__': <attribute '__weakref__' of 'A' objects>,
# '__doc__': None}

# 返回实例 属性和值组成的字典
print(aa.__dict__)
# {'b': 1}
```

![image-20260422155231352](Python进阶-img/image-20260422155231352.png)

> 可以把这玩意往文件里写,但是一会加载的时候你就识别不了了,因为我们一会读出来的数据,还是要转成信息
>
> 读的时候,把字典转成对象



![image-20260422160746916](Python进阶-img/image-20260422160746916.png)

> 如果是学生对象转字典,调dict这个属性

![image-20260422160826715](Python进阶-img/image-20260422160826715.png)

>  如果是你的字典转学生对象,**字典就行了





### 17.保存学生信息

![image-20260422161413292](Python进阶-img/image-20260422161413292.png)

```py
# 9.定义函数,实现保存学生信息功能
def save_student(self):
    # 关联 学生信息文件
    # ./代表的是项目的路径,它可不是你在的路径
    with open('./stu_data.txt','w',encoding='utf-8') as dest_f:
        # 9.2 把 列表套对象 转成 列表套字典
        # 9.2 把 [学生对象,学生对象.学生对象] -> [字典,字典,字典]
        stu_dict=[stu.__dict__ for stu in self.stu_list]
        # 9.3把字典列表,持久化到文件中.
        dest_f.write(str(stu_dict)) # 记得把字典转成字符串再写入
```



### 18.加载学生信息

<img src="Python进阶-img/image-20260422172235628.png" alt="image-20260422172235628" style="zoom: 50%;" />

```py
# 10.定义函数,实现加载学生信息
    def load_student(self):
        # 10.1
        # 10.2 关联学生信息文件
        with open('./stu_data.txt','r',encoding='utf-8') as src_f:
            # 10.3一次性读取所有的数据
            stu_data=src_f.read()       # '[字典,字典...]' 字符串形式下的列表套字典
            # 10.4把上述的字符串,转换为列表套字典
            stu_list=eval(stu_data)     # ''
            # 10.5判断如果列表为空,就赋予空列表
            if len(stu_list)==0:
                stu_list=[]
            # 10.6走到这里说明列表不为空,则把stu_list(列表套字典),转成 [学生对象,学生对象,学生对象],并赋值给self.stu_list
            self.stu_list=[Student(**stu_dict) for stu_dict in stu_list]
```



> 少写一个 self，多写一串 @staticmethod......

> 字典:
> {=="变量名"==`:`=="变量值"==}





## 闭包

> 不改变函数代码对功能做增强

![image-20260408115329539](Python进阶-img/image-20260408115329539.png)



![image-20260408115407217](Python进阶-img/image-20260408115407217.png)

> 浅拷贝拷贝的少,深拷贝拷贝的多

![image-20260408115537104](Python进阶-img/image-20260408115537104.png)



![image-20260408115610995](Python进阶-img/image-20260408115610995.png)

注意单独加法和累加的区别

![image-20260408115708026](Python进阶-img/image-20260408115708026.png)

> 使用外部函数变量的内部函数,叫做闭包

![image-20260408115826703](Python进阶-img/image-20260408115826703.png)

> 1.有嵌套
>
> 2.有引用
>
> 3.有返回

![image-20260408115900998](Python进阶-img/image-20260408115900998.png)



![image-20260408120509940](Python进阶-img/image-20260408120509940.png)

> 外部函数的变量包括: 外部函数的 形参 和 局参

![image-20260408120638278](Python进阶-img/image-20260408120638278.png)

> 看到这个尖括号,要弄清楚: **函数名** 和 **函数名括号**是两个概念,前者表示 **函数对象**,后者表示 **调用函数获取的返回值**

![image-20260408120949468](Python进阶-img/image-20260408120949468.png)

> 函数名可以赋值给变量,这个变量就是:函数对象

![image-20260408121033356](Python进阶-img/image-20260408121033356.png)

> 就是返回函数对象被呗，然后内部函数捕获了外部函数变量，最后当外部函数终止的时候，内部函数依旧可以使用外部函数变量
>
> 把内部函数当做对象，作为外部函数的返回值进行返回

![image-20260408121121912](Python进阶-img/image-20260408121121912.png)



![image-20260408121142251](Python进阶-img/image-20260408121142251.png)

> 前面的不能这么理解，内层返回的是对象，而不是内层函数，而是你在调用外部函数时，拿到了内部函数，刚好可以配对上

![image-20260408121208836](Python进阶-img/image-20260408121208836.png)



![image-20260408121221675](Python进阶-img/image-20260408121221675.png)

> 没改变num1
>
> 相当于是把内层 函数对象返回了给fn_inner然后在接收num2然后输出加和结果



### 闭包入门图解

![image-20260408121303885](Python进阶-img/image-20260408121303885.png)

### nonlocal关键字

不是全局哦,相当于在函数内部的全局

![image-20260408154124667](Python进阶-img/image-20260408154124667.png)



![image-20260408154256170](Python进阶-img/image-20260408154256170.png)

> 调用完外部函数a不是已经没了吗，为啥还能输出a = 100 ?
>
> 内部函数中引用了a变量,fn_inner=fn_outer()时就已经给了内部函数a的值,再调用内部函数就可以用a了
>
> 内部函数使用了外部函数的变量，这就叫做有引用

![image-20260408154359996](Python进阶-img/image-20260408154359996.png)

> 你会发现你改的不是外部函数的a，而是去重新声明了一个101

> 闭包只是让你去获取外部函数的变量，没让你去改，而nonlocal就是让你可以在闭包里改外部的变量
>
> 但是弹栈后还能访问外部函数变量，但是不能修改了
>
> nonlocal 是函数内部的全局，小全局
>
> 就算是做嵌套，但是在实际中大部分也是在类里面操作吧
>
> 因为使用nonelocal声明了a为非局部变量，那么在整个程序执行完之前，a没有被销毁，所以a的值会一直累加，直到整个程序完全执行完毕

![image-20260408154755037](Python进阶-img/image-20260408154755037.png)

有点像lamda表达式，当时在学Java函数式编程就是把方法包一个对象提供返回这个方法

> 调用的名字怎么起得和内部函数一样？应该换一个观感好点
>
> 他是为了给后面装饰器作铺垫，变量名仍然使用内部函数的

![image-20260408154933070](Python进阶-img/image-20260408154933070.png)

你调外部函数的主观目的实际上就是为了调内部函数

![image-20260408155011320](Python进阶-img/image-20260408155011320.png)

> 你能用，但是你不能改

这里并不是内部函数里不能修改外部变量，而是内部函数把a=a+1视作内部变量a代替了外部变量a，而内部变量a没有值，当然a=a+1不成立

既然内部都可以打印a了，为什么说内部变量a没有值？

![image-20260408155131249](Python进阶-img/image-20260408155131249.png)

> nonlocal其实就是声明该变量不是我们内部定义的，是其他地方来的
>
> 老师说的是对的，就是内部变量没有提前定义，操作不了
>
> 就是告诉python，当前的a是 外部函数的变量，而不是当前内部函数的还未定义的变量‘

![image-20260408155229993](Python进阶-img/image-20260408155229993.png)

```py
# 闭包入门.py     			(延长 外部函数局部变量 的生命周期)
# 1.定义外部函数
def fn_outer(num1):
    # 2.定义内部函数
    def fn_inner(num2):     # 有嵌套
        # 3.求和
        sum=num1+num2       # 有引用
        print(f"求和结果：{sum}")
    return fn_inner         # 有返回

# 4.调用上述函数
fn_inner=fn_outer(10)
fn_inner(1)     # 11
fn_inner(1)     # 11
fn_inner(1)     # 11
```



```py
# 在闭包里nonlocal			(修改 外部函数局部变量 的值)
def fn_outer():
    a=100
    def fn_inner():
        nonlocal a
        a=a+1
        print(f"a:{a}")

    return fn_inner

if __name__ == '__main__':
    fn_inner=fn_outer()
    fn_inner()  # 101
    fn_inner()  # 102
    fn_inner()  # 103
```

![image-20260408153420989](Python进阶-img/image-20260408153420989.png)

![image-20260408153429903](Python进阶-img/image-20260408153429903.png)

> 闭包真正的应用场景:装饰器



## 装饰器

> 语法糖(语法格式的简化版)方式用的更多!

![image-20260408161514222](Python进阶-img/image-20260408161514222.png)

![image-20260408161620193](Python进阶-img/image-20260408161620193.png)

```bash
#  闭包(1.有嵌套2.有引用3.有返回) + 4.有额外功能 = 装饰器
```

> 装饰器的本质:在不改变原有函数功能的基础上,对原有函数的功能做升级!
>
> 一个毛胚房,找个装修队(装饰器)过来,田园风,现代风...
>
> 不改变功能的基础上,对功能做增强(一定要加功能,否则就是闭包)

闭包是私有化全局变量！！！

![image-20260408162348647](Python进阶-img/image-20260408162348647.png)



![image-20260408162447397](Python进阶-img/image-20260408162447397.png)

> 其实就是通过外部方法获取到内部方法对象，但是外部要传一个需要被增强的方法作为参数给内部方法去调用，但是内部调用之前对原方法做了增强，就这么简单，感觉讲的好绕啊，绕了半天

![image-20260408165657485](Python进阶-img/image-20260408165657485.png)

> 感觉就是写了个新函数，然后新函数调用原函数进行增强。
>
> 对 所以叫做语法糖 就是一种语法的运用
>
> 其实你把试学班学的内容就是全部python了 剩下现在教的就全是语法糖了

### 方式2：语法糖

![image-20260408173409643](Python进阶-img/image-20260408173409643.png)

```py
"""
装饰器介绍：
    概述/作用：
        它的本质是1 个闭包函数，目的是 在不改变原有函数的基础上，对其功能做增强
        大白话： 装修队 在不改变房屋结构的情况下，对房屋做装饰(功能增强)
    前提条件:
        1.有嵌套
        2.有引用
        3.有返回
        4.有额外功能
    装饰器的用法:
        格式1:传统写法
            装饰后的函数名=装饰器名(被装饰的原函数名)
            装饰后的函数名()

        格式2:语法糖
            在要被装饰的原函数上,直接写 @装饰器名,之后直接调用原函数即可
"""
# 在发表评论前,都需要登录

# 1.定义外部函数,形参列表接收 要被装饰的函数名(对象)
def check_login(fn_name):       # fn_name: 要被装饰的函数名(对象)
    # 1.1 定义内部函数
    def fn_inner():             # 有嵌套
        # 1.2 额外功能
        print("校验登录..登陆成功!")        # 这个是 额外功能
        # 1.3 访问原函数 ,即:外部函数的引用
        fn_name()               # 有引用
    # 1.4 返回内部函数对象
    return fn_inner             # 有返回

# 2.定义函数,表示 发表评论
def comment():
    print("发表评论")


@check_login        # 底层其实是: payment=check_login(payment)
def payment():
    print("充值中...")

# 3.测试
# 3.1 传统方式
hg=check_login(comment)
hg()            # 没诉求
print('-'*32)
comment()       # 有诉求用之前的原函数
print('-'*32)

# 3.2语法糖
# payment=check_login(payment)
# payment()
payment()
```

![image-20260408173528737](Python进阶-img/image-20260408173528737.png)

### 装饰器的使用

三层装饰器其实就是给装饰器传参

![image-20260408173544269](Python进阶-img/image-20260408173544269.png)



![image-20260408173557685](Python进阶-img/image-20260408173557685.png)





![image-20260408173629536](Python进阶-img/image-20260408173629536.png)

> ```py
> # 装饰器的内部函数格式 要和 被装饰的原函数 保持一致
> ```

![image-20260408174149305](Python进阶-img/image-20260408174149305.png)



![image-20260408175409620](Python进阶-img/image-20260408175409620.png)



![image-20260408175520485](Python进阶-img/image-20260408175520485.png)



![image-20260408175600203](Python进阶-img/image-20260408175600203.png)



### 有参数无返回

![image-20260408180455017](Python进阶-img/image-20260408180455017.png)

>  我认为： getsum 函数地址指向inner 换句话说这两个就是一个函数 所以都有参数



![image-20260408193904602](Python进阶-img/image-20260408193904602.png)

>  有了闭包后，即使外部函数执行完毕，内部函数依旧可以使用外部函数的变量.
>
> 装饰器:闭包的一种写法



### 无参有返回

装饰器的内部函数格式 要和 被装饰的原函数格式 一致

![image-20260408193939280](Python进阶-img/image-20260408193939280.png)



![image-20260408195247130](Python进阶-img/image-20260408195247130.png)

![image-20260408195511975](Python进阶-img/image-20260408195511975.png)



### 有参有返回

![image-20260408195634251](Python进阶-img/image-20260408195634251.png)

![image-20260408200245763](Python进阶-img/image-20260408200245763.png)



### 可变参

![image-20260408200739284](Python进阶-img/image-20260408200739284.png)

![image-20260408205024923](Python进阶-img/image-20260408205024923.png)

> 其实这里的传参可以这样来理解：fn_inner把外来的参数先进行打包，然后在内部函数引用fn_name时进行解包，然后调用fn_name时又打包起来进行后续计算



### 多个装饰器装饰一个原函数

> 由内向外去装饰

![image-20260408205142382](Python进阶-img/image-20260408205142382.png)

> 这里我懂了，这里comment第一次被修饰就是验证码，第二次被修饰就是加一个校验登录，变量名一直是comment，指向的已经变了

> 很简单因为是一层一层返回，使用@属于是做设计符合使用习惯

![image-20260408211749911](Python进阶-img/image-20260408211749911.png)





### 一个装饰器装饰多个原函数

带有参数的装饰器

![image-20260408212008046](Python进阶-img/image-20260408212008046.png)



![image-20260408212216655](Python进阶-img/image-20260408212216655.png)



![image-20260408212401896](Python进阶-img/image-20260408212401896.png)



![image-20260408214045354](Python进阶-img/image-20260408214045354.png)



![image-20260408214309291](Python进阶-img/image-20260408214309291.png)

> 别人调你装饰器就只能使用固定的名字了，当然一般也不自己设置装饰器

![image-20260408215319029](Python进阶-img/image-20260408215319029.png)

![image-20260408220016555](Python进阶-img/image-20260408220016555.png)



## 深浅拷贝

==普通赋值就是不拷贝,不拷贝就是不变地址==

==拷贝就是变地址==

> ```py
> # 深浅拷贝主要是针对于可变类型来讲的, 深拷贝拷贝所有层(可变), 浅拷贝只拷贝第1层(可变)
> #    如果是针对于不可变类型, 则用法和 普通赋值一样, 并无区别.
> ```

> 可变(列表,集合,字典)与不可变(元组,字符串,数值类型)类型:
>
> **在不改变地址值的情况下,他里边的内容能不能改**
>
> 不可变类型：同样的数据在内存地址是相同的(只有一个)

![image-20260408220251920](Python进阶-img/image-20260408220251920.png)



> 创建变量a,创建一个对象,分配一块空间,把这块空间的地址给到a

![image-20260408220511221](Python进阶-img/image-20260408220511221.png)



![image-20260408220639244](Python进阶-img/image-20260408220639244.png)



![image-20260408220821998](Python进阶-img/image-20260408220821998.png)

```py
# a=10
# b=a
# c=10
# 问：内存中有几个10？
Python 在内存中创建一个整数对象 10
变量 a 指向这个对象
# Python 对 -5 ~ 256 之间的小整数做了全局缓存：
# 这些数字使用频率极高
# 系统提前创建好，重复使用，不重复开辟内存
# 总结
# a=10 → 内存创建 1 个 10
# b=a → 复用同一个 10
# c=10 → 还是复用同一个 10
# 最终答案：内存里只有 1 个 10。
```

> c语言的变量是地址的别名，而python是对象的引用

### 普通赋值，不可变类型（普通拷贝就是不拷贝，不复制，跟着变）



![image-20260408221927370](Python进阶-img/image-20260408221927370.png)

### 普通赋值，可变类型（普通拷贝就是不拷贝，不复制，第一层地址不变）

![image-20260408221900362](Python进阶-img/image-20260408221900362.png)

### 浅拷贝可变类型（浅拷贝，就是拷贝第一层，复制第一层，第一层地址变）

浅拷贝操作可变类型，可变元素变了，浅拷贝里的可变元素就跟着变

![image-20260409100201460](Python进阶-img/image-20260409100201460.png)

### 浅拷贝不可变类型(不可变浅拷贝,就是不拷贝，不复制，第一层地址不变）

> 如果是不可变类型，和普通赋值一样，都是直接指向就可以了，因为不可变，你不可变，就意味着我没法去复制你开辟空间，那大家就必须得用同一份
>
> **不可变** 意味着没法开辟空间

![image-20260409101442483](Python进阶-img/image-20260409101442483.png)

### 深拷贝可变类型(可变深拷贝,就是全拷贝,全复制,所有层地址都变)

![image-20260409103135373](Python进阶-img/image-20260409103135373.png)

### 深拷贝不可变类型(不可变深拷贝,就是不拷贝,不复制,地址值不变)

==只要有(可变的)层,就拷贝,就复制,地址值就变==

![image-20260409103352419](Python进阶-img/image-20260409103352419.png)

> 可变不共享地址值变，不可变共享地址值不变





## 网络编程,进程,线程

![image-20260409111751807](Python进阶-img/image-20260409111751807.png)

### 网络编程

就是用来实现网络互联的 不同计算机上 运行的程序间 可以进行数据交互



三要素

IP地址:设备在网络中的唯一标识

![image-20260409115713437](Python进阶-img/image-20260409115713437.png)

端口号:程序在设备中的唯一标识

![image-20260409115744184](Python进阶-img/image-20260409115744184.png)

协议:传输规则

![image-20260409120018305](Python进阶-img/image-20260409120018305.png)

![image-20260409113327014](Python进阶-img/image-20260409113327014.png)



![image-20260409113408502](Python进阶-img/image-20260409113408502.png)

> 电脑上的每一个软件的端口号是唯一的

> 协议:就像你快递黄金对黄金进行包裹,加密

![image-20260409113944947](Python进阶-img/image-20260409113944947.png)

![image-20260409114027648](Python进阶-img/image-20260409114027648.png)



![image-20260409114039875](Python进阶-img/image-20260409114039875.png)



![image-20260409114205859](Python进阶-img/image-20260409114205859.png)

> IPV4采用的是4字节,十进制
>
> 每个单位,一个byte的范围有符号:-128~127
>
> ​		     无符号:0 ~ 255
>
> IPV4全球IP总数,256的4次方(不够用)
>
> IPV6八字节16进制

![image-20260409114639448](Python进阶-img/image-20260409114639448.png)



![image-20260409115035592](Python进阶-img/image-20260409115035592.png)

>  每个软件都有自己的端口

![image-20260409115123113](Python进阶-img/image-20260409115123113.png)



![image-20260409115159124](Python进阶-img/image-20260409115159124.png)

> 0~1023端口号被系统占用了,不要用

![image-20260409115310517](Python进阶-img/image-20260409115310517.png)



![image-20260409115335094](Python进阶-img/image-20260409115335094.png)



#### TCP

TCP：打电话

客户端向服务器端

服务器端给回值

客户端再找服务器端

UDP：群聊

只管发，不管接收，每个包64kb

![image-20260409140337537](Python进阶-img/image-20260409140337537.png)



![image-20260409140752116](Python进阶-img/image-20260409140752116.png)



双向，每个两次

![image-20260409140937992](Python进阶-img/image-20260409140937992.png)



![image-20260409141049813](Python进阶-img/image-20260409141049813.png)

![image-20260409141150384](Python进阶-img/image-20260409141150384.png)

> 谈到缺点就说 **相对**较低,优点是高,就说高

> 区分拨号方

![image-20260409141809744](Python进阶-img/image-20260409141809744.png)

![image-20260409141829969](Python进阶-img/image-20260409141829969.png)

![image-20260409141845280](Python进阶-img/image-20260409141845280.png)



### Socket套接字

![image-20260409141946021](Python进阶-img/image-20260409141946021.png)

![image-20260409142012333](Python进阶-img/image-20260409142012333.png)

> 客户端的手机和服务器端的手机,数据通过两个手机进行传输

![image-20260409142101569](Python进阶-img/image-20260409142101569.png)



![image-20260409142129742](Python进阶-img/image-20260409142129742.png)



![image-20260409142158729](Python进阶-img/image-20260409142158729.png)

字节流,TCP协议

![image-20260409142223558](Python进阶-img/image-20260409142223558.png)

```py
"""
网络编程介绍:
    概述:
        网络编程也叫网络通信,Socket通信,即:通信双方都独有自己的Socket对象,
        数据在Socket之间通过 数据报包(UDP协议) 或者 字节流(TCP协议) 的形式进行传输
    大白话举例:
        你和你遥远的朋友在聊天,看看这你们两个人在交互，其实是通过 两部手机(双方各自的手机)来交互的.
"""
import socket

# 创建socket对象
# 参1:Address Family,地址族,即:IPV4 还是 IPV6,默认值: AF_INET(ipv4)   AF_INET6(ipv6)
# 参2:Socket Type,套接字类型,即:TCP 还是 UDP,默认值: SOCK_STREAM(TCP)   SOCK_DGRAM(UDP)
socket_obj=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
print(socket_obj)
```



### TCP程序开发流程

![image-20260409143120210](Python进阶-img/image-20260409143120210.png)



![image-20260409144346186](Python进阶-img/image-20260409144346186.png)



![image-20260409144448779](Python进阶-img/image-20260409144448779.png)



![image-20260409144706823](Python进阶-img/image-20260409144706823.png)

![image-20260409150641767](Python进阶-img/image-20260409150641767.png)



### 一句话交情

#### 服务器端代码

![image-20260409150530035](Python进阶-img/image-20260409150530035.png)

> 加个b的意思是把这个字符串转成二进制,针对于没有中文的字符串

```py
"""
网编入门案例,服务器端给客户端发送消息,客户端给出回执信息

服务器端开发流程:
    1. 创建服务器端Socket对象
    2. 绑定IP地址和端口号
    3. 设置最大监听数
    4. 等待客户端申请建立连接
    5. 给客户端发送消息
    6. 接收客户端的信息并打印
    7. 释放资源

细节:
    客户端和服务器端是通过 字节流(bytes) 的形式实现的
"""
import socket

from IPython.terminal.shortcuts.auto_suggest import accept

# 1. 创建服务器端Socket对象,ipv4,字节流(TCP)
server_socket=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
# 2. 绑定IP地址和端口号
server_socket.bind(('127.0.0.1',10086))
# 3. 设置最大监听数
server_socket.listen(5)
# 4. 等待客户端申请建立连接
print(1)
accept_socket,client_info=server_socket.accept()
print(2)
# 5. 给客户端发送消息
accept_socket.send(b'Welcome To Socket!')
# 6. 接收客户端的信息并打印 (单位字节,单次会话上限)
data=accept_socket.recv(1024).decode('utf-8')
print(f"服务器端收到 来自{client_info} 的信息:{data}")
# 7. 释放资源
accept_socket.close()
# server_socket.close()     # 服务器端一般不关闭
```

#### 客户端代码

![image-20260409151727409](Python进阶-img/image-20260409151727409.png)



![image-20260409151900344](Python进阶-img/image-20260409151900344.png)

```py
"""
网编入门案例,服务器端给客户端发送消息,客户端给出回执信息

客户端开发流程:
    1. 创建客户端Socket对象
    2. 连接服务器端，指定：服务器端IP，端口号
    3. 接收服务器端的信息并打印
    4. 给服务器端发送消息
    5. 释放资源

细节:
    客户端和服务器端是通过 字节流(bytes) 的形式实现的
"""
import socket

# 1.创建客户端Socket对象,ipv4,TCP协议
client_socket=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
# 2.连接服务器端，指定：服务器端IP，端口号
client_socket.connect(('192.168.96.130',10086))
# 3.接收服务器端的信息并打印
data=client_socket.recv(1024).decode('utf-8')
print(f"客户端收到:{data}")
# 4.给服务器端发送消息
client_socket.send("Socket很好玩,很有趣,我很喜欢".encode('utf-8'))
# 5.释放资源
client_socket.close()
```

![image-20260409152821871](Python进阶-img/image-20260409152821871.png)

#### 扩展编解码

![image-20260409152919356](Python进阶-img/image-20260409152919356.png)

![image-20260409153827257](Python进阶-img/image-20260409153827257.png)

![image-20260409153928885](Python进阶-img/image-20260409153928885.png)

> bytes,bys,字节数组





![image-20260409154513031](Python进阶-img/image-20260409154513031.png)



![image-20260409154528004](Python进阶-img/image-20260409154528004.png)



![image-20260409155017249](Python进阶-img/image-20260409155017249.png)



![image-20260409155701622](Python进阶-img/image-20260409155701622.png)





### 文件上传

![image-20260409162610901](Python进阶-img/image-20260409162610901.png)

<img src="Python进阶-img/image-20260409170519671.png" alt="image-20260409170519671" style="zoom:25%;" />

<img src="Python进阶-img/image-20260409171910660.png" alt="image-20260409171910660" style="zoom:50%;" />

### 扩展_模拟多任务版文件上传服务器端







### 内容回顾

==ipv6是16字节，十六进制==

![image-20260409172002327](Python进阶-img/image-20260409172002327.png)

> 数据报包，每个包不超过64kb（一组kb）

<img src="Python进阶-img/image-20260409172225201.png" alt="image-20260409172225201" style="zoom:67%;" />

> 端口号复用:socket.setsockopt()

![image-20260409172447451](Python进阶-img/image-20260409172447451.png)



## 进程

进程间数据隔离,线程数据共享

### 多任务



<img src="Python进阶-img/image-20260409173028453.png" alt="image-20260409173028453" style="zoom:50%;" />

<img src="Python进阶-img/image-20260409173233323.png" alt="image-20260409173233323" style="zoom:50%;" />

> 并发:感觉是多任务(交替执行,**CPU快速切换**),
>
> 并行:真正是多任务
>
> 对于多个任务来讲是并发,对单个任务是并发

<img src="Python进阶-img/image-20260409173406049.png" alt="image-20260409173406049" style="zoom:50%;" />

> CPU切不过来了,就把你的游戏给干掉了

<img src="Python进阶-img/image-20260409173858656.png" alt="image-20260409173858656" style="zoom:67%;" />

> 单个CPU只能是并发
>
> 多核可以并行

![image-20260409174038981](Python进阶-img/image-20260409174038981.png)



![image-20260409174219570](Python进阶-img/image-20260409174219570.png)

分配资源，进程

调度资源，线程

> 进程是分配资源的基本单位，线程是调度资源的基本单位
>
> 前面说错了，线程是cpu调度的最小单位

![image-20260409175247049](Python进阶-img/image-20260409175247049.png)

### 多进程

<img src="Python进阶-img/image-20260409175345795.png" alt="image-20260409175345795" style="zoom:50%;" />



<img src="Python进阶-img/image-20260409175605444.png" alt="image-20260409175605444" style="zoom: 50%;" />



![image-20260409175653480](Python进阶-img/image-20260409175653480.png)



<img src="Python进阶-img/image-20260409175711642.png" alt="image-20260409175711642" style="zoom:50%;" />

<img src="Python进阶-img/image-20260409180155027.png" alt="image-20260409180155027" style="zoom:50%;" />





#### 多进程完成多任务

<img src="Python进阶-img/image-20260409180232150.png" alt="image-20260409180232150" style="zoom:33%;" />

<img src="Python进阶-img/image-20260409180304177.png" alt="image-20260409180304177" style="zoom: 50%;" />



![image-20260409180438063](Python进阶-img/image-20260409180438063.png)



<img src="Python进阶-img/image-20260409180451647.png" alt="image-20260409180451647" style="zoom:50%;" />

> window中创建进程只能通过主模块进程创建，即使是主模块而非导入也需要加入if __name__进行判断

![image-20260409182458821](Python进阶-img/image-20260409182458821.png)

![image-20260409182517776](Python进阶-img/image-20260409182517776.png)



> 谁是第一个都有可能,只是大概率是p1先开始



#### 进程带参数的任务

![image-20260409202538151](Python进阶-img/image-20260409202538151.png)

![image-20260409203356775](Python进阶-img/image-20260409203356775.png)

>  导包可以直接在后面写time
>
> 主板的BIOS来设置，进程的资源分配

![image-20260409203417385](Python进阶-img/image-20260409203417385.png)

> 1，导包
> 2，创建进程对象，关联目标函数，如果目标函数需要传参，就传个参
> 3，启动
>
> 1.导包，2.编写目标函数，3.创建主进程和子进程，4.启动子进程

![image-20260409203525922](Python进阶-img/image-20260409203525922.png)

#### 获取进程的父进程的编号有一种方式

![image-20260409203655683](Python进阶-img/image-20260409203655683.png)



![image-20260409203730121](Python进阶-img/image-20260409203730121.png)

> 进程编号的作用：找子进程和父进程之间关系的

<img src="Python进阶-img/image-20260409203830453.png" alt="image-20260409203830453" style="zoom: 67%;" />

> 获取父进程的编号getparentpid -> os.getppid()

![image-20260409203945427](Python进阶-img/image-20260409203945427.png)

![image-20260409204121952](Python进阶-img/image-20260409204121952.png)



![image-20260409204155868](Python进阶-img/image-20260409204155868.png)

> main函数不需要启动
>
> 因为一开始就启动了就进栈了
>
> main的父进程是 pycharm(pycharm的进程)

> 结束pycharm的进程的时候，那你刚刚还在运行的代码不会运行完，会立马终止

![image-20260409204314052](Python进阶-img/image-20260409204314052.png)

> 23060是不是说明它的父进程都是main进程

> 获取当前进程，两种方式  os.getpid()    multiprocessing.current_process().pid
> 获取父进程，就一种方式 os.getppid()

#### 进程的注意点

![image-20260409204554051](Python进阶-img/image-20260409204554051.png)

> 不懂，我们需要了解电脑cpu的进程线程吗，我们了解这些的作用是什么？
>
> 不了解进程线程 如何编程开发？

<img src="Python进阶-img/image-20260409204629353.png" alt="image-20260409204629353" style="zoom:67%;" />



<img src="Python进阶-img/image-20260409204656664.png" alt="image-20260409204656664" style="zoom:50%;" />

![image-20260409204713217](Python进阶-img/image-20260409204713217.png)

> 相当于在父进程的进程表里
>
> 因为进程是资源分配的基本单位 所以每个进程的资源是独立的

![image-20260409204743405](Python进阶-img/image-20260409204743405.png)



![image-20260409204812804](Python进阶-img/image-20260409204812804.png)



![image-20260409204839833](Python进阶-img/image-20260409204839833.png)



![image-20260409204901376](Python进阶-img/image-20260409204901376.png)

> 说明数据是相互隔离的

> 创建进程开始是会重新加载一次main外文件，所以print多打印了两次

![image-20260409204943952](Python进阶-img/image-20260409204943952.png)

> 全部再拷贝一份

除了变量算资源，那方法函数算资源吗

![image-20260409205041124](Python进阶-img/image-20260409205041124.png)

> \# 全局代码！每个进程都会跑
>
> print(f"我是main外资源，看我执行了几次")

三、怎么验证？

给 print 加个进程名，一眼看懂：

```py
import multiprocessing
import time

# 全局代码！每个进程都会跑
print(f"【{multiprocessing.current_process().name}】执行了全局代码")

my_list = []

def write_data():
    for i in range(1, 6):
        my_list.append(i)
    print(f'write_data: {my_list}')

def read_data():
    time.sleep(3)
    print(f'read_data: {my_list}')

if __name__ == '__main__':
    p1 = multiprocessing.Process(target=write_data, name="写进程")
    p2 = multiprocessing.Process(target=read_data, name="读进程")
    p1.start()
    p2.start()
```

运行结果你会看到：

```py
【MainProcess】执行了全局代码
【写进程】执行了全局代码
【读进程】执行了全局代码
```

**完美对应 3 次！**

------

四、怎么让它只执行 1 次？

把**全局代码放进 `if __name__ == '__main__':` 里面**！

```py
import multiprocessing
import time

my_list = []

def write_data():
    for i in range(1, 6):
        my_list.append(i)
    print(f'write_data: {my_list}')

def read_data():
    time.sleep(3)
    print(f'read_data: {my_list}')

# 只有主进程会进这里
if __name__ == '__main__':
    print('我是main内资源, 只执行1次')  # 现在只打印1次！

    p1 = multiprocessing.Process(target=write_data)
    p2 = multiprocessing.Process(target=read_data)
    p1.start()
    p2.start()
```



![image-20260409210036470](Python进阶-img/image-20260409210036470.png)



<img src="Python进阶-img/image-20260409210147882.png" alt="image-20260409210147882" style="zoom:67%;" />



<img src="Python进阶-img/image-20260409210842290.png" alt="image-20260409210842290" style="zoom:67%;" />



![image-20260409211250353](Python进阶-img/image-20260409211250353.png)



![image-20260409211314995](Python进阶-img/image-20260409211314995.png)



> 举个例子，下课铃响了，老师还要挣扎一下，拖拖堂

==daemon 守护==

> 水晶爆了,
>
> 非守护进程嘎的时候,他的所有守护进程都得嘎

![image-20260409211942281](Python进阶-img/image-20260409211942281.png)

![image-20260409211958256](Python进阶-img/image-20260409211958256.png)

![image-20260409212115601](Python进阶-img/image-20260409212115601.png)

> 会在后面随机的一个时间,才会回收

![image-20260409212931246](Python进阶-img/image-20260409212931246.png)

![image-20260409212806131](Python进阶-img/image-20260409212806131.png)

默认情况下,主进程

> terminate的使用场景在哪? 
>
> 子进程卡死了或者不需要子进程陪着主进程到最后

<img src="Python进阶-img/image-20260409213422817.png" alt="image-20260409213422817" style="zoom:50%;" />

```py
正在努力工作中...  ← 子进程在跑
正在努力工作中...
正在努力工作中...
main进程结束       ← 【主进程代码跑完了，但主进程没退出！它在等子进程！】
正在努力工作中...  ← 子进程继续跑
正在努力工作中...
正在努力工作中...
正在努力工作中...
正在努力工作中...
正在努力工作中...
正在努力工作中...

进程已结束，退出代码为 0  ← 【子进程全部跑完 → 主进程才真正退出】
```

`print ('main 进程结束 ') ≠ 主进程退出！`

- 主进程只是**把自己的代码执行完了**
- 但它**会停在那里，一直等子进程**
- 直到子进程把 10 次全部打印完，主进程才会真正结束

这就是教材说的：

**默认情况下，主进程会等待子进程执行结束再结束！**





### 多线程

<img src="Python进阶-img/image-20260409213556382.png" alt="image-20260409213556382" style="zoom:50%;" />



![image-20260409213646809](Python进阶-img/image-20260409213646809.png)

> 每个进程都有一个 主线程栈

![image-20260409214007011](Python进阶-img/image-20260409214007011.png)

![image-20260409213950508](Python进阶-img/image-20260409213950508.png)

![image-20260409214020778](Python进阶-img/image-20260409214020778.png)

<img src="Python进阶-img/image-20260409214036169.png" alt="image-20260409214036169" style="zoom:67%;" />

![image-20260409214026377](Python进阶-img/image-20260409214026377.png)



![image-20260409214104249](Python进阶-img/image-20260409214104249.png)

![image-20260409214141021](Python进阶-img/image-20260409214141021.png)

![image-20260409214314427](Python进阶-img/image-20260409214314427.png)

![image-20260409214450150](Python进阶-img/image-20260409214450150.png)

>  你的线程只能去抢进程分配给你的这些资源诶





#### 多线程完成任务

![image-20260409214519044](Python进阶-img/image-20260409214519044.png)

![image-20260409214557523](Python进阶-img/image-20260409214557523.png)

![image-20260409214615810](Python进阶-img/image-20260409214615810.png)

![image-20260409214628930](Python进阶-img/image-20260409214628930.png)

> 一个开辟通道，一个干活的



<img src="Python进阶-img/image-20260409215128060.png" alt="image-20260409215128060" style="zoom:50%;" />

<img src="Python进阶-img/image-20260409215607283.png" alt="image-20260409215607283" style="zoom:67%;" />



![image-20260409215925463](Python进阶-img/image-20260409215925463.png)

![image-20260409215851846](Python进阶-img/image-20260409215851846.png)

<img src="Python进阶-img/image-20260409220604191.png" alt="image-20260409220604191" style="zoom: 50%;" />

![image-20260409220639618](Python进阶-img/image-20260409220639618.png)





## 生成器扩展题

> 其实就是创造出一个新的列表，然后遍历新列表，再对原来的列表进行修改。

> 和java一样去掉元素后，元素向前移位了

![image-20260414201016709](Python进阶-img/image-20260414201016709.png)

![image-20260414200220069](Python进阶-img/image-20260414200220069.png)

>  remove作用在旧的列表上,==s下标指代的是新列表的下标索引==,是不会随着删除元素而改变它里面的元素的

> 💡 关键问题：**删除元素会导致列表长度变短，后续元素左移，而循环索引会继续向后走，直接跳过了被左移的元素**，最终导致漏删。

为什么`my_list[:]`切片能解决问题？

`my_list[:]` 是 Python 的**列表切片语法**，作用是**创建原列表的一个完整浅拷贝（副本）**。

此时循环的逻辑变成：

- 循环遍历的是**副本列表**：`['aa', 'bb', 'cc', 'bb', 'bb', 'bb', 'dd']`
- ==真正修改（删除）的是**原列表`my_list`**==

![image-20260414195739728](Python进阶-img/image-20260414195739728.png)

> .remove(x)是删除列表对象里第一个等于x的元素

### 第二步：牢记两个核心规则

1. **`for` 循环遍历列表**：是**按索引顺序依次取元素**（0→1→2→3→…），索引计数器只会**往后加**，不会往回退；

2. **`list.remove(元素)`**：删除**列表中第一个匹配的元素**，删除后，**后面的所有元素会自动往前挪一位**（索引全部 - 1）；

3. 初始列表（索引 + 元素）：

   ```
   [0:'aa', 1:'bb', 2:'cc', 3:'bb', 4:'bb', 5:'bb', 6:'dd']
   ```

------

第三步：逐次执行循环（最关键！）

我们跟着 Python 的执行逻辑，**一步一步走**：

第 1 次循环：取索引 0 的元素

- `s = 'aa'` → 不等于 `'bb'`
- 不删除，列表无变化
- 循环索引计数器 → 准备取 **索引 1**

第 2 次循环：取索引 1 的元素

- `s = 'bb'` → 匹配，执行 `my_list.remove('bb')`

- ✂️ 删除第一个`bb`（原索引 1），列表瞬间变成：

  ```
  [0:'aa', 1:'cc', 2:'bb', 3:'bb', 4:'bb', 5:'dd']
  ```

- 后面的元素全部**往前挪了 1 位**！

- 循环索引计数器 → 准备取 **索引 2**

第 3 次循环：取索引 2 的元素

- 此时列表索引 2 的元素是 `'bb'` → 匹配，执行 `remove('bb')`

- ✂️ 删除第一个

  ```
  bb
  ```

  （现在索引 2），列表变成：

  ```
  [0:'aa', 1:'cc', 2:'bb', 3:'bb', 4:'dd']
  ```

- 元素又往前挪了！

- 循环索引计数器 → 准备取 **索引 3**

第 4 次循环：取索引 3 的元素

- 此时列表索引 3 的元素是 `'bb'` → 匹配，执行 `remove('bb')`

- ✂️ 删除第一个

  ```
  bb
  ```

  （现在索引 2），列表变成：

  ```
  [0:'aa', 1:'cc', 2:'bb', 3:'dd']
  ```

- 循环索引计数器 → 准备取 **索引 4**

第 5 次循环：取索引 4 的元素

- 现在列表**只有 4 个元素（索引 0-3）**，索引 4 根本不存在！
- 🚫 循环直接结束！

------

第四步：最终结果

去掉 `[:]` 后，运行代码的结果是：

```
['aa', 'cc', 'bb', 'dd']
```

**还剩一个`bb`没删掉！**

------

为什么加 `[:]` 就能删干净？

`my_list[:]` 是**切片浅拷贝**，会生成一个**和原列表一模一样的新列表**：

```
['aa','bb','cc','bb','bb','bb','dd']
```

循环遍历的是**这个新列表**，原列表怎么删、怎么变，都不会影响遍历的新列表，所以能完整遍历所有元素，把所有`bb`都删掉。

------

总结

1. **不加`[:]`**：遍历**原列表**，删元素→元素前移→循环索引递增→**跳过元素**→删不干净；
2. **加`[:]`**：遍历**拷贝的新列表**，原列表修改不影响遍历→**完整遍历所有元素**→删干净。





## 线程的注意点

随机性:CPU做着高效的切换

线程之间共享全局变量

<img src="Python进阶-img/image-20260414203300819.png" alt="image-20260414203300819" style="zoom:50%;" />



<img src="Python进阶-img/image-20260414204257538.png" alt="image-20260414204257538" style="zoom:67%;" />



![image-20260414204346009](Python进阶-img/image-20260414204346009.png)







### 线程的特点之主线程会等待子线程的结束再结束

daemon

所以里边有个work这个函数,是目标函数，他的执行时间长，而main里面执行时间短，你会发现主线程结束了，但是子线程还在走，那这种情况下呢可能就不太好（这种情况就是之前说到的，我关闭了微信，但是他里面的聊天功能还在运行，这件事情就很可怕了），那如果我想让他结束，那你就可以设置在这个地方设置你的子线程为守护线程就可以了

怎么设置呢？

第一种就是在定义的时候直接传参

第二种就是通过一个setDaemon

> 注意下面!!

![image-20260414211636738](Python进阶-img/image-20260414211636738.png)

> 在这个函数身上有一道黑色的横线,这种函数你调用还是能调用的,这种函数叫已过时,在新的API里面,已经不支持这种写法了,不建议用(3.8python还能用)
>
> (anaconda的3.12python里不推荐用)

<img src="Python进阶-img/image-20260414213406810.png" alt="image-20260414213406810" style="zoom:50%;" />

![image-20260414213618177](Python进阶-img/image-20260414213618177.png)

### 线程特点之共享全局变量

> 一个函数往列表里面加,一个函数从列表里面读,看看最终的效果

<img src="Python进阶-img/image-20260414220140954.png" alt="image-20260414220140954" style="zoom:50%;" />



<img src="Python进阶-img/image-20260414215853280.png" alt="image-20260414215853280" style="zoom: 50%;" />







> 共享全局变量也不意味着一定就好,所以就引出了互斥锁

### 线程特点之共享全局变量数据出现错误问题

![image-20260414220452541](Python进阶-img/image-20260414220452541.png)

> 3.12的特性,总能保证有一个正确结果是2000000
>
> anaconda的版本
>
> 3.8就没有互斥锁的效果

<img src="Python进阶-img/image-20260415111109533.png" alt="image-20260415111109533" style="zoom:50%;" />

> 线程1还没有来记得执行完(一个完整的动作)前，被线程2抢走了资源，就可能出问题.

![image-20260415112114030](Python进阶-img/image-20260415112114030.png)

> 左边一次,右边一次,加了两次,但是你的值增加了1,就缺了一个1,那这样的动作如果缺的多了,那刚才那个140w这个现象他就有了[信息不同步]

> 解决方法:你俩谁抢到了资源,另一个就进不去

<img src="Python进阶-img/image-20260415112256547.png" alt="image-20260415112256547" style="zoom:50%;" />

可以共享资源啊 和多进程还是有区别的

![image-20260415112421614](Python进阶-img/image-20260415112421614.png)

![image-20260415112650411](Python进阶-img/image-20260415112650411.png)



### 互斥锁

> 互斥锁会出现两种问题:死锁和锁不住

> 啊?为什么不是真正的多线程?如果不是为什么会出现抢占式调度资源的情况?我倒是知道python的多态是伪多态,但没看到课上说线程也是伪线程啊?

![image-20260415113352123](Python进阶-img/image-20260415113352123.png)



<img src="Python进阶-img/image-20260415113628071.png" alt="image-20260415113628071" style="zoom:67%;" />



![image-20260415113655279](Python进阶-img/image-20260415113655279.png)



![image-20260415113713269](Python进阶-img/image-20260415113713269.png)

> 那和同步阻塞有什么区别，干嘛还要多线程

![image-20260415113826622](Python进阶-img/image-20260415113826622.png)



![image-20260415114133959](Python进阶-img/image-20260415114133959.png)

这是在混合类型中的运用（在大型多线程项目中，针对特定线程序列），单独拎出来就不能理解了？眼光别太有局限性



> 一个线程一直等待对方释放锁的动作就叫:死锁
>
> 锁不住,就是两把钥匙,它里面正操作呢,你这边拿钥匙开门了

![image-20260415115001567](Python进阶-img/image-20260415115001567.png)



![image-20260415115447613](Python进阶-img/image-20260415115447613.png)

![image-20260415115502707](Python进阶-img/image-20260415115502707.png)



### 进程和线程的对比

<img src="Python进阶-img/image-20260415115651234.png" alt="image-20260415115651234" style="zoom:50%;" />



<img src="Python进阶-img/image-20260415115738882.png" alt="image-20260415115738882" style="zoom:50%;" />



![image-20260415115814868](Python进阶-img/image-20260415115814868.png)



![image-20260415120101702](Python进阶-img/image-20260415120101702.png)

> python多进程可以实现并行，而后者无法实现并行，只能并发
>
> 因为资源多，所以更稳定?

<img src="Python进阶-img/image-20260415120153594.png" alt="image-20260415120153594" style="zoom:50%;" />



![image-20260415120215492](Python进阶-img/image-20260415120215492.png)



> 因为多线程只能去操作共享数据,要加锁了

![image-20260415120355724](Python进阶-img/image-20260415120355724.png)





## python高级与正则表达式

`生成器`，`迭代器`，`property属性`

<img src="Python进阶-img/image-20260415173422838.png" alt="image-20260415173422838" style="zoom:33%;" />

### 迭代器

<img src="Python进阶-img/image-20260415173459093.png" alt="image-20260415173459093" style="zoom:33%;" />



<img src="Python进阶-img/image-20260415173545725.png" alt="image-20260415173545725" style="zoom: 67%;" />

> 包括有些函数传参,它上边是不是有一个参数叫它必须传一个iterable 类型,可迭代类型

<img src="Python进阶-img/image-20260415173738146.png" alt="image-20260415173738146" style="zoom:67%;" />

>  range是一次性加载到内存还是next
>
>  是后者
>
>  ==range（）就是一个迭代器==

![image-20260415191651348](Python进阶-img/image-20260415191651348.png)

> ==显式的实现俩方法==，说白了就是重写

<img src="Python进阶-img/image-20260415192056369.png" alt="image-20260415192056369" style="zoom: 50%;" />

> raise理解为抛出异常,异常信息往控制台一打然后终止,有点像return,返回一个值,然后结束函数
>
> raise就是先返回给你一个异常,再把你的程序终止了,类似与java里面的throws(声明抛出异常)

```py
# __next__是用来获取下一个元素的
```

迭代器就是数据容器吗（迭代器就是range（））

![image-20260415193105826](Python进阶-img/image-20260415193105826.png)

```py
"""
演示自定义迭代器

迭代器介绍:
    概述:
        自定义的类,只要重写了__iter__() 和 __next__()方法,就可以称为迭代器,[你随便写个类,你只要能把这俩写了,那你就是迭代器]
    目的:
        隐藏底层的逻辑,让用户使用更方便
        惰性加载,用的时候才会获取.

回顾:for循环格式
    for i in 可迭代类型:
        pass
"""
# 需求:模拟range(1,6),自定义 迭代器实现同等逻辑
# 场景1:回顾 range()用法
for i in range(1,6):
    print(i)
print('-'*23)

# 场景2:自定义迭代器
# 1.自定义 迭代器类
class MyIterator:
    # 2.通过init魔法方法,初始化属性,指定:范围
    def __init__(self,start,end):
        self.current_value= start       # 当前值,默认为 开始值
        self.end=end                    # 结束值

    # 3.重写iterator魔法方法,返回当前对象(即:迭代器对象).
    def __iter__(self):
        return self

    # 4.重写next方法,返回当前值,并更新当前值
    def __next__(self):
        # 4.1判断当前值是否合法
        if self.current_value >= self.end:
            raise StopIteration
        # 4.2走这里,说明当前值合法,返回当前值,并更新当前值
        # value=self.current_value        # value =              1    2   3   4   5
        # self.current_value+=1           # self.current_value = 2    3   4   5   6
        # return value                    #                      1    2   3   4   5

        # 效果同上,代码更简单
        self.current_value+=1           # self.current_value = 2    3   4   5   6
        return self.current_value-1     #                      1   2   3   4   5

# 5.创建迭代器对象,并遍历
for i in MyIterator(1,6):
    print(i)

# for i in 10:
#     pass
```

![image-20260415194335495](Python进阶-img/image-20260415194335495.png)



> 流数据:就是一个一个往外蹦过来的数据,就跟流水线一样的数据

![image-20260415194719582](Python进阶-img/image-20260415194719582.png)

> next(迭代器对象),next()函数的作用就是得到元素并指针向后移动一位







### python生成器

> 1 生成器的概念?如何使用?
> 存储规则，用数据的时候现场生成
>
> ==数据不是一次性全部生成出来,而是要用的时候,根据规则去生成==
>
> 生成器是 根据一定规则生成数据的一种机制,每次调用生成器只生成一个值,可以节省大量内存

> 生成器归根结底他的目的是就是减少内存空间,**节约内存**
>
> 数据不是一次性全部生成出来,而是使用一个,再生成一个,可以节约大量的内存

> ==生成器是简化的迭代器==

> 生成器就是买家具,那你用一个,我再给你生成一个,而生成器是用一个现生成一个
>
> 迭代器是我把规则放这,一堆的数据我都给你生成好了,你是不是用一个拿一个啊,不用不拿,但是数据还在

<img src="Python进阶-img/image-20260415195813692.png" alt="image-20260415195813692" style="zoom:67%;" />

> 列表,字典,集合推导式,还少元组推导式,元组推导式没有这个概念,你按照元组的格式写,它其实叫`生成器`

#### 生成器的第一种写法，元组推导式

![image-20260415200059629](Python进阶-img/image-20260415200059629.png)

这个还是需要案例，不然太抽像了，事后还记不住

<img src="Python进阶-img/image-20260415201102560.png" alt="image-20260415201102560" style="zoom:67%;" />

<img src="Python进阶-img/image-20260415201141181.png" alt="image-20260415201141181" style="zoom:50%;" />

> 那么如果换成小括号呢,按照我们的设想,是不是应该是元组,但是不,是对象

![image-20260415201348404](Python进阶-img/image-20260415201348404.png)

>  所以啊我想表达意思是没有元组推导式的概念,那你这样写,它其实本质是一个生成器

![image-20260415201943846](Python进阶-img/image-20260415201943846.png)

![image-20260415203653326](Python进阶-img/image-20260415203653326.png)

#### 生成器的第二种写法,yield关键字

<img src="Python进阶-img/image-20260415204805275.png" alt="image-20260415204805275" style="zoom:67%;" />

```py
# 写个函数，yield往这一标记就ok了

# 需求:通过yield方式,获取到生成器之 1~10 之间的整数
# 回顾:推导式写法
my_g=(i for i in range(1,11))

# yield方式如下
# 1.定义函数,存储到生成器中,并返回
def my_fun():
    # my_list=[]                # 创建
    # for i in range(1,11):
    #     my_list.append(i)     # 添加
    # return my_list            # 返回

    # 效果类似于上边的代码
    # yield在这里做了三件事:1.创建生成器对象 2.把数据保存到生成器对象中 3.返回生成器对象
    for i in range(1,11):
        yield i

# 2.测试
my_g2=my_fun()
print(type(my_g2))      # <class 'generator'>

print(next(my_g2))
print(next(my_g2))
print('-'*23)
for i in my_g2:
    print(i)
```





#### 生成器的应用场景，dataloader的封装

![image-20260415204934186](Python进阶-img/image-20260415204934186.png)



![image-20260415210646176](Python进阶-img/image-20260415210646176.png)

这里其实并没有体现出生成器的特性，文件内容一次性全部加载出来了

![image-20260415211708723](Python进阶-img/image-20260415211708723.png)



>  两个索引分别是idx是生成器的索引，中括号里的切片是lines的索引，lines是个列表，装的是每一行的歌词,==batch_size设置多少==,那一个列表里面==一个元素里就有几行歌词==

这样写完全没有节省内存啊，还更占用内存了，readlines本来就是全部读进了内存，那后面再用生成器有啥意义？应该一行一行读出来然后放进列表，够8条就放进生成器然后清空

<img src="Python进阶-img/image-20260415212902083.png" alt="image-20260415212902083" style="zoom:67%;" /> 



![image-20260415213154802](Python进阶-img/image-20260415213154802.png)

#### 上午内容回顾

![image-20260415213516951](Python进阶-img/image-20260415213516951.png)

> range底层咋做的,你不知道,但是呢我只会把我的这些批量的数据我提供给你,他是一次性生成所有的数据

> 生成器的目的是减少内存占用,除此以外他跟迭代器是一样的,都是基于规则生成数据的

> yield关键字作用
>
> 1.创建生成器对象
>
> 2.添加元素到生成器
>
> 3.返回

![image-20260415214059167](Python进阶-img/image-20260415214059167.png)

> 如果想要对迭代过程进行高度控制,用迭代器,否则就用生成器

> Property属性

![image-20260415214306363](Python进阶-img/image-20260415214306363.png)

> 正则表达式 
>
> 正则:正确符合规则的字符串
>
> ^异或表示开头
>
> $刀乐表示结尾

> 正则做判断是不是手机号,学规则,正则的作用就是:校验

![image-20260415214743048](Python进阶-img/image-20260415214743048.png)

### Property属性

目的只有一个:

<img src="Python进阶-img/image-20260415215106598.png" alt="image-20260415215106598" style="zoom: 50%;" />



<img src="Python进阶-img/image-20260415215230426.png" alt="image-20260415215230426" style="zoom:67%;" />



#### 装饰器方式

<img src="Python进阶-img/image-20260415215332395.png" alt="image-20260415215332395" style="zoom: 50%;" />



<img src="Python进阶-img/image-20260415220908727.png" alt="image-20260415220908727" style="zoom:67%;" />

> 告诉你不能迭代

![image-20260415221019888](Python进阶-img/image-20260415221019888.png)



![image-20260415222722508](Python进阶-img/image-20260415222722508.png)

get_age,set_age... 你这么折腾自己干啥?什么意思?

@==获取值的函数名==.setter

我能不能把get_age我就叫age

<img src="Python进阶-img/image-20260415222113116.png" alt="image-20260415222113116" style="zoom:50%;" />

> ==但是为了便于调用,实际开发中,私有的属性,我们提供的函数名,都是去掉私有后,你的名字直接写的==
>
> java的get\set方法

<img src="Python进阶-img/image-20260415222854116.png" alt="image-20260415222854116" style="zoom:50%;" />

> 这里就不标黄了

<img src="Python进阶-img/image-20260415221429481.png" alt="image-20260415221429481" style="zoom:50%;" />

> 本来就是想访问私有数值

![image-20260415221524083](Python进阶-img/image-20260415221524083.png)

#### Property属性之类属性方式

乌龟的屁股-龟腚

> 类属性的意思就是：你需要做一层封装，什么封装呢？

![image-20260416101844145](Python进阶-img/image-20260416101844145.png)

> 给一个age属性,用property修饰,==把这两个函数(方法)当类属性来用==

![image-20260416102627907](Python进阶-img/image-20260416102627907.png)

> 两个名字不能一样

> 刚刚是因为你的装饰器不一样,别人能够很好的区分,所以获取和设置值方法可以名字一样

<img src="Python进阶-img/image-20260416102645206.png" alt="image-20260416102645206" style="zoom:67%;" />

![image-20260416104223632](Python进阶-img/image-20260416104223632.png)

![image-20260416104247069](Python进阶-img/image-20260416104247069.png)



### 正则表达式

在Java里边用的是regexp

<img src="Python进阶-img/image-20260416104359825.png" alt="image-20260416104359825" style="zoom:67%;" />

<img src="Python进阶-img/image-20260416105447523.png" alt="image-20260416105447523" style="zoom:50%;" />

>  如果是封闭环境开发，可以用猫头鹰校验器,点个高亮,点个match,这边正常写规则,下边就会帮你匹配式子
>
> 匹配到的就会高亮
>
> 如果想要别的,也可以加加加

<img src="Python进阶-img/image-20260416110112587.png" alt="image-20260416110112587" style="zoom:67%;" />

> 好不能和 i 匹配

<img src="Python进阶-img/image-20260416110316196.png" alt="image-20260416110316196" style="zoom:67%;" />

![image-20260416110833310](Python进阶-img/image-20260416110833310.png)

<img src="Python进阶-img/image-20260416112208045.png" alt="image-20260416112208045" style="zoom:50%;" />

<img src="Python进阶-img/image-20260416112222219.png" alt="image-20260416112222219" style="zoom:50%;" />





<img src="Python进阶-img/image-20260416112319706.png" alt="image-20260416112319706" style="zoom:67%;" />



![image-20260416112809764](Python进阶-img/image-20260416112809764.png)

![image-20260416112829347](Python进阶-img/image-20260416112829347.png)





> r是取消路径的那个操作,取消转义



<img src="Python进阶-img/image-20260416113207557.png" alt="image-20260416113207557" style="zoom:50%;" />

> 先接收一个正则返回正则对象
>
> 由正则对象.sub在这里边替换
>
> compile返回的是一个正则对象

```py
"""
演示正则替换

回顾正则的使用步骤:
    1. 导包
    2. 正则匹配
        result = re.match('正则表达式', '要校验的字符串')
        result = re.search('正则表达式', '要校验的字符串')
        result = re.compile('正则表达式').sub(替换后的内容,要被替换的字符串)       替换
    3. 获取匹配结果.
        result.group()
"""
import re

# 1.定义字符串
s='开心你就大声笑,哈哈,呵呵,嘿嘿,嘻嘻,桀桀桀,啦啦啦'

# 2.把上述的 哈,呵,嘿,嘻,桀 替换为 ♥, | 代表或者的意思
#                   正则规则         新字符串  要被替换的字符串
result=re.compile('哈|呵|嘿|嘻|桀').sub('♥',s)

# 3.打印结果
print(result)
print('-'*23)

# 新版API的写法      compile就不需要了
# 参1:正则规则,参2:新字符串,参3:要被替换的字符串
result=re.sub('哈|呵|嘿|嘻|桀', '♣①', s)     # 各个公司都有自己的敏感词库
print(result)
```



### 正则表达式编写

#### 单个字符

<img src="Python进阶-img/image-20260416115307142.png" alt="image-20260416115307142" style="zoom:50%;" />



![image-20260416115354580](Python进阶-img/image-20260416115354580.png)



<img src="Python进阶-img/image-20260416115430517.png" alt="image-20260416115430517" style="zoom: 67%;" />

> 

![image-20260416145858344](Python进阶-img/image-20260416145858344.png)

> []代表括号中的任意一个就欧克

<img src="Python进阶-img/image-20260416150030351.png" alt="image-20260416150030351" style="zoom:50%;" />



<img src="Python进阶-img/image-20260416150228646.png" alt="image-20260416150228646" style="zoom:50%;" />



<img src="Python进阶-img/image-20260416150311281.png" alt="image-20260416150311281" style="zoom:50%;" />



![image-20260416150411545](Python进阶-img/image-20260416150411545.png)



![image-20260416150446099](Python进阶-img/image-20260416150446099.png)



![image-20260416150501146](Python进阶-img/image-20260416150501146.png)



![image-20260416150909818](Python进阶-img/image-20260416150909818.png)



#### 多个字符

![image-20260416151238727](Python进阶-img/image-20260416151238727.png)

> *不能单独出现

![image-20260416151522108](Python进阶-img/image-20260416151522108.png)



![image-20260416161036218](Python进阶-img/image-20260416161036218.png)



<img src="Python进阶-img/image-20260416161126707.png" alt="image-20260416161126707" style="zoom:67%;" />



![image-20260416161231707](Python进阶-img/image-20260416161231707.png)



![image-20260416161313262](Python进阶-img/image-20260416161313262.png)



![image-20260416161428889](Python进阶-img/image-20260416161428889.png)



![image-20260416161838357](Python进阶-img/image-20260416161838357.png)



#### 使用re模块匹配指定字符串开头或结尾

![image-20260416171436198](Python进阶-img/image-20260416171436198.png)



![image-20260416171455005](Python进阶-img/image-20260416171455005.png)

![image-20260416205203818](Python进阶-img/image-20260416205203818.png)

#### re模块提取分组数据

##### |

<img src="Python进阶-img/image-20260416205231632.png" alt="image-20260416205231632" style="zoom:67%;" />



![image-20260416210012492](Python进阶-img/image-20260416210012492.png)



![image-20260416210049855](Python进阶-img/image-20260416210049855.png)

<img src="Python进阶-img/image-20260416210817029.png" alt="image-20260416210817029" style="zoom:67%;" />

<img src="Python进阶-img/image-20260416211316803.png" alt="image-20260416211316803" style="zoom:50%;" />

##### ()

![image-20260416211337949](Python进阶-img/image-20260416211337949.png)

![image-20260416211926579](Python进阶-img/image-20260416211926579.png)

##### \num,单级的html

![image-20260416214711871](Python进阶-img/image-20260416214711871.png)

> 网页横线网上全都是head
>
> 往下都是body

<img src="Python进阶-img/image-20260416212316509.png" alt="image-20260416212316509" style="zoom:67%;" />



![image-20260416212401274](Python进阶-img/image-20260416212401274.png)



![image-20260416213440515](Python进阶-img/image-20260416213440515.png)

> 这个杠1并不是简单的让代码少些一点，还有一个特殊的功能

![image-20260416213828771](Python进阶-img/image-20260416213828771.png)

> \1引用第1组,要求要和第1组的内容一模一样,而不是遵循和分组1一样的正则规则就行
>
> ==就是第一组内容是啥，引用的内容就得是啥。 他开始搞错了以为是引用的规则。==

![image-20260416214752437](Python进阶-img/image-20260416214752437.png)



##### 扩展,多级的html



![image-20260416215833845](Python进阶-img/image-20260416215833845.png)

>  设置分组名 (?P==<==分组名==>==该组的re)  使用分组名==(?P=分组名)==

![image-20260416215645500](Python进阶-img/image-20260416215645500.png)



<img src="Python进阶-img/image-20260416215924824.png" alt="image-20260416215924824" style="zoom:67%;" />



![image-20260416220045305](Python进阶-img/image-20260416220045305.png)

```py
import re

# 1需求:在列表中["apple","banana","orange","pear"]，匹配apple和pear
# list=["apple","banana","orange","pear"]
#
# for s in list:
#     result=re.match('apple|pear',s)
#     if result:
#         print(f"我喜欢吃的水果:{result.group()}")
#     else:
#         print(f"我不喜欢吃的水果:{s}")

# 2需求:匹配出163、126、qq等邮箱
# email='abcd@163.com'
# result=re.match('^[a-zA-Z_0-9]{4,}@(163|126|qq)\.com',email)
# print(result.group())

# 3需求:匹配qq:10567这样的数据，提取出来qq文字和qq号码
# s="qq:10567"
# result=re.match('(qq):(\d*)',s)
# if result:
#     print(f"qq={result.group(1)}")
#     print(f"号码：{result.group(2)}")
# else:
#     print("匹配失败")
# 4需求:匹配出<html>hh</html>
html_s="<html>hh</html>"
# result=re.match('<html>.*</html>',html_s)
result=re.match(r'<(html)>.*</\1>',html_s)    # 出现了右斜杠(Windows的反骨)就要用r转义
print(result.group())

# 5需求:匹配出<html><h1>www.itcast.cn</h1></html>
html_s="<html><h1>www.itcast.cn</h1></html>"
result=re.match(r'<(?P<A>html)><(?P<B>h1)>.*</(?P=B)></(?P=A)>',html_s)
print(result.group())
```





## 数据结构与算法

...













# 重要点,多记几遍

## 类操作

```py
# 创建类对象
对象名=类()
# 类外,设置属性,获取属性
对象名.属性名="xxx"
对象名.属性名
对象名.方法名()
```

> 类属性可以通过对象名.的方式调用,也可以通过类名.的方式调用



## 🧠 为什么要加 `global` 声明？核心是「Python 的变量作用域规则」

你说的没错：**全局变量在函数里「读」是可以直接用的，但「写」必须加 `global` 声明**，这是 Python 最容易踩的坑之一！

------

一、先看两个对比，一眼懂区别

1. 只「读」全局变量：不用 `global`，完全正常

```
global_num = 0

def test_read():
    # 只读取，不修改
    print(global_num)  # 正常输出 0，不需要 global

test_read()
```

2. 要「写」（修改）全局变量：不加 `global` 直接报错

```
global_num = 0

def test_write():
    # 尝试修改，没加 global
    global_num += 1  # ❌ 报错：UnboundLocalError: local variable 'global_num' referenced before assignment
    print(global_num)

test_write()
```

3. 加了 `global` 声明：修改成功

```
global_num = 0

def test_write():
    global global_num  # ✅ 声明：我要修改全局的 global_num
    global_num += 1
    print(global_num)  # 正常输出 1

test_write()
print(global_num)  # 全局变量也变成了 1
```

------

二、背后的核心规则：Python 的「LEGB 作用域」

Python 解释器在查找变量时，遵循严格的优先级：

1. **L（Local）**：当前函数 / 方法的局部作用域
2. **E（Enclosing）**：外层嵌套函数的作用域
3. **G（Global）**：模块级的全局作用域
4. **B（Built-in）**：Python 内置作用域（如 `print`、`len`）

关键规则：

- **如果只是读取变量**：解释器会按 L→E→G→B 顺序查找，找不到就报错。
- 如果要给变量赋值（写操作）：
  - 解释器**默认认为这是「创建局部变量」**，直接在局部作用域创建同名变量，**完全屏蔽全局变量**。
  - 如果你**没有提前声明 `global`**，就会出现「先引用、后创建」的错误（比如 `global_num += 1` 本质是 `global_num = global_num + 1`，右边要读、左边要写，解释器认为右边读的是局部变量，但还没创建，就报错了）。
