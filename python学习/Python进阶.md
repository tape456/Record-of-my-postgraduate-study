

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









### 多线程

















# 重要点,多记几遍

```py
# 创建类对象
对象名=类括号
# 类外,设置属性,获取属性
对象名.属性名="xxx"
对象名.属性名
对象名.方法名()
```

