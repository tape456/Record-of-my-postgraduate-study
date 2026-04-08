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















### 烤地瓜案例

















## 定义类的三种格式p19

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



![image-20260405153931589](Python进阶-img/image-20260405153931589.png)











## 学生管理系统

![image-20260408113833901](Python进阶-img/image-20260408113833901.png)

![image-20260408115017494](Python进阶-img/image-20260408115017494.png)

![image-20260408115042104](Python进阶-img/image-20260408115042104.png)



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
