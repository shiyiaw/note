#  Java学习笔记

### 类变量 类方法

	+ 对象名调用 类名调用都可以
	+ static 修饰 

​	static 被类的所有的对象实例共享；

​	版本不同 静态变量所在位置不同

	+ 是同一个类 所有对象共享的

+ 类变量在类加载的时候就生成了。
+ 类名.类变量名访问 不许要创建对象实例

### 代码块

​	代码块 【修饰符】{ 代码}  要写修饰符只能写 static

	+ 是卸载构造器的前面
	+ 构造器都会调用 
	+ <u>static代码块 类的加载而执行 只执行一次</u> 
	+  对构造器的补充机制

#### **类什么时候被加载**

​			1.创建对象实例时

​			2.创建子类对象实例，父类也被加载

​			3.使用类的静态成员时 静态属性 静态方法

		- 如果只使用类的静态成员 普通代码块不会执行

#### 	创建对象 类调用顺序 

​			1.静态代码块 和 静态属性初始化 优先级一样调用按顺序

​			2.普通代码块 普通属性 

​			3.构造器

​			调用构造器 先调用super 带调用本类普通代码块

#### 	继承后的调用顺序

​			1.父类的静态代码块和静态属性|优先级一样 按定义顺序执行

​			2.子类的静态代码块和静态属性|优先级一样 按定义顺序执行

​			3.父类的普通代码块和普通属性初始化|优先级一样 按定义顺序执行

​			4.父类的构造方法

​			5.子类的普通代码块和普通属性初始化|优先级一样 按定义顺序执行

​			5.子类的构造方法  //面试题

  		**静态代码块只能调用静态成员，普通代码块可以调用任意成员。**

### 单例设计模式

单例

​	1.所谓类的单例设计模式，就是采取一定的方法保证在整个软件系统中，对某个类只能存在一个对象实例，并且该类只提供一个取得其对象实例的方法

2. 单例模式有两种方式：1）饿汉式 2）懒汉式

​	     饿汉式 步骤 1. 将构造器私有化

​					2.在类的内部直接创建

​					3.提供一个公共的static方法，返回对象

创建和返回对象 都得是static 因为这样才能不创建实例就可以调用

​			缺点：可能创建了没有使用，资源浪费

​		懒汉式步骤：1.构造器私有化

​								2.定义一个static静态属性对象

​								3.提供一个public的static方法，放								回对象

###  final关键字

 - 可以修饰类、属性、方法和局部变量

 - 中文意思 最后的、最终的

   下列情况用到

   1.当不希望类被继承是，用final修饰

   2.当不希望父类的某个方法被子类覆盖/重写，

   3.当不希望类的某个属性值被修改

   4.当不希望某个局部变量被修改

细节：1.final修饰属性又叫常量，大写一般用XXX_xx__

​			2.修饰时候必须赋初值，并且以后不能修改

​				赋值的位置：定义时 在构造器中  在代码块中 

   - 如果final修饰的属性是静态的，则初始化位置只能是1.定义时 2.在静态代码块 不能在构造器中

final类不能继承 但是可以实例化对象；

如果类是final类 就没必要写final

### 抽象类

#### 抽象类介绍

 	abstract 父类方法不确定 抽象方法是没有实现的方法

​	抽象类被继承 由子类实现

 - 抽象类方法 没有方法体

 - 抽象类不能实例化

 - 抽象类可以没有抽象方法 

 -  抽象类的本质还是类 可以有类的各种成员

 - <u>*一个类继承抽象类就必须实现所有抽象方法 除非他也是抽象类*</u>

   <u>*有方法体就算实现了*</u>

- 抽象方法不能使用private、final、static修饰，因为这些关键字都不能重写实现

#### 模板设计模式

### 接口interface

#### 	基本介绍

语法：		8/89999520-3300

+0//1058588.。。，。m'm'n?/ waza

~~~java
interface 接口名{
    属性
    方法 抽象方法 默认实现方法 静态方法
}
class 类名 implements 接口{
    自己属性
    自己方法
    必须实现接口的抽象方法
}
~~~

小结：

1.在jdk7 之前都是抽象方法

2.在jdk8 后 可以有静态方法和默认方法 可以有方法的具体实现

 	但是可以有默认方法但是 要default修饰

#### 细节

 - 接口中的是public方法 

 - 接口不能被实例化 可以不用abstract修饰

   快速打出所有方法使用快捷键 alt+enter

抽象类 实现接口 可以不实现接口方法

- 接口中的属性，只能是final的，并且是public static final
- 可以实现多个接口
- 接口中的属性的访问形式“接口名.属性名
- 一个接口不能继承其他类，但是可以继承多个接口
- 接口修饰符只能哟九年public 和 默认 和类的修饰符一样

 接口在一定程度上实现了代码解耦：即 接口规范性+动态绑定机制

```JAVA
interface usb{}
class a implements usb{}
class b imolements usb{}//多态 向上转型
usb a = new a();
a = new b();

usb[] usb = new usb[2];
usb[0] = new a();
usb[1] = new b();
```

多态的传递

```java
interface a{ }
interface b{ }
class m implements a{}

a man = new m(); 
b man = new m(); 错误 因为没有实现接口b
interface b extends a{ } 
```

 a 继承 b c继承b c也等于继承a

一个类 继承了a 实现了b接口 调用相同的属性是 要写 super或者接口名.属性

### 内部类

类的五大成员 ：成员 方法 构造器 代码块 内部类

内部类 ：被嵌套的类

~~~java
class outer{
    class inner{
        
    }
}
~~~

#### 内部类分类

> 定义在外部类局部位置上 比如方法内
>
> 1.局部内部类|有类名
>
> 2.匿名内部类|没有类名，==重点==
>
> 定义在外部类的成员位置：
>
> 1.成员内部类|没有static修饰
>
> 2.静态内部类|使用static修饰

#####  局部内部类

	- 不能添加访问修饰符，因为她就是个局部变量 但是可以final修饰
	- 可以直接访问外部类的所有成员包括私有
	- 作用域：只在方法体或代码块内
	- 直接访问外部类的成员
	- 外部类在方法中可以创建内部类的对象，在调用方法            

如果外部类和局部内部类的·成员重名，默认就近原则。如果想访问外部类的成员则使用 外部类名.this.成员 去访问

###### 匿名内部类 Anonymous

1）本质是类 2）内部类 3）该类没有名字

使用场景：类只是使用一次，后面不再使用

​					匿名内部类可以简化开发



~~~java
a man = new a(){
     void eat(){           System.out.println("abc"+getClass());
        }
    };
    man.eat();
    }

}
class a {
    void eat(){}
}
~~~

~~~java
new person()}{
    public void hi(){
        System.out.print("abn")
    }
}.hi();
~~~

##### 成员内部类

：1.直接访问所有成员

​	外部调用创建实例对象 再调用

在外部创建内部的类  a.b man = a.new b();

类名重复 就近原则 外部类名.this.属性

##### 静态内部类

​	1.放在成员位置 2.用static修饰 3.类只能访问静态成员

外部其他类访问  a.b man =new a.b();

重名访问外部类 只需要 外部类名.变量





## 我亦无他，唯手熟尔；



## 断点调试

F7跳入 F8跳过 shift+F8跳出 F9 resume执行到下一个断点



## 枚举

enumeration

### 自定义枚举

​	1.将构造器私有化

​	2.去掉setxxx方法，防止属性被修改

​	3.在类内部创建 固定的对象

​	4.优化 可以加final修饰符

### en um关键字

1.使用关键字enum替代类

2.直接写 对象名（参数）

3.多个对象 就用逗号间隔

4.需要写在最前面 对象

- 用enum关键字 会默认继承Enum 类 而且是final类 
- 如果使用无参构造器 括号和参数都可以i省略

## 快捷键

crtl+d 删除行

Alt+下箭头 复制一行

ctrl+/ 注释

alt+enter 自动导入类

ctrl+shifit+L 快速格式化代码

alt+ins 自动生成构造器 

ctrl+h 查看类的继承关系

crtl+b 快速定位方法

.var 自动分配变量名

## 常用类

包装类

针对八种基本数据类型相应的引用类型-包装类

![image-20220901151046708](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220901151046708.png)

有类的特点，可以调用类中的方法

Wrapper包装器

jdk5以后，就可以自动装箱和自动拆箱

```java
手动拆箱
int n1 = 100;
Integer integer = new Integer(n1);
Integer integer1 = =Integer.valueOf(n1);
自动拆箱
int n2 = 200；
Integer integer = n2;
底层使用的是 Integer.valueOf(n2);
自动拆箱 Integer -> int
int n3 = 
```

```
Object obj1 = true ? new Intger(1):new Double(2.0)
System.out.print(obj1)
输出1.0 三元运算符是一个整体
```

包装类型转String

   

```
Integer -> String
	Integer i = 100;
	String str1 = i + "";
	String str2 = i.toString();
	String str3 = String.valueof(i);
String -> Integer
	String str4 ="12345";
	Integer i2 = Integer.parseInt(str4);
	Integer i3 = new Integer(str4)
```



![image-20220906092537889](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220906092537889.png)

如果i在 IntegerCache.low(-128)~IntegerCache.high(127) 直接返回数组

只要有基本数据类型就 是判断值是否相等 

String

字符串对象用于保存字符串，也就是一组字符序列

字符串常量对象是用双引号括起来的字符序列

字符串的字符使用Unicode字符编码，一个字符（不区分字母汉字）占两个字节

String类常用构造器 有很多的构造器，构造器的重载

```java
STring s1 = new String();
String s2 = new String(String original);
String s3 = new String(chaar[] a);
String s4 = new String(char[] a,int starIndex,int count)
```

String 类实现了接口Serializabale [String 可以实现串行化：可以在网络传输]

String 是final类 不能被其他类继承

String 有属性private final char value【】 用于存放字符串内容

注意 value 是一个final，不可以修改 不能在指向新的对象 地址不可修改

创建String对象的两种方式

```
方法一：直接赋值String s = “hspedu”;
方法二：调用构造器String s = new String("hspedu");
```

![image-20220906124334362](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220906124334362.png)

字符串的特性

String是一个final类，代表不可变的字符序列

字符串是不可变的，一个字符串对象一旦被分配，其内容是不可变的 

常量相加，看的是池    变量相加，是在堆中

常用方法：StringBuilder StringBuffer

euqals:区分大小写，判断内容是否相等

equalslgnoreCase：忽略大小写的判断内容是否相等

length：获取字符的个数，字符串的长度

lastIndexOf：获取字符串最后一次出现的索引

substring：截取指定范围的子串

trim：去前后空格

charAt：获取某索引处的字符，注意不能使用Str[index]这种方式

toUpperCase:字符串变成大写

toLowerCase：

concat：拼接字符串

replace：替代字符串 对字符串本身没有影响

toCharArray：转换成字符数组 

StringBuffer类

1.StringBuffer的直接父类 是 AbstractStringBuilder

2.StringBuffer 实现了Serializable，即StringBuffer的对象可以串行化

3.在父类中 AbstractStringBuilder 有属性 char[] value, 不是final

​	该value数组存放 字符串内容，引出存放在堆中的

4.StringBuffer是一个final类，不能被继承

保存的是字符串常量，里面值可以修改，更新内容不要更新地址，效率高

StringBuffer的构造器

```
1.创建一个 大小为 16的char[]，用于存放字符内容
StringBuffer stringbuffer = new StringBuffer()；

2.通过构造器指定char[] 大小
StringBuffer stringbuffer1 = new StringBuffer(100);

3.通过 给一个String 创建 StringBuffer，chaar[] 大小就是str.length+16
```

```
String -> StringBuffer
String str = "hello tom";
方式1 使用构造器
注意 放回才是StringBuffer对象，对str本身没有影响
StringBuffer stringBufffer = new StringBuffer(str);

方式2 使用append方法
StringBuffer stringBuffer1 = new StringBuffer();
stringBuffer1 = stringBuffer1.append(str);
```

```
StringBuffer -> String
方法1 使用StringBuffer提供的toString方法
StringBuffer stringBuffer = new StringBuffer("adwda")

方法2 使用构造器来搞定
String s1 = new Stirng(stringBuffer3);
```

StringBuffer类常用方法

1.增append

2.删 delete(start，end)

3.改 replace(start,end,string)将start--end间的内容替换掉，不含end

4.查 indexOf 查找子串在字符串第1次出现的索引，如果招不到返回-1

5 插 insert

6.获取长度 length

StringBuilder  与StringBuffer兼容的api，但不保证同步(不是线程安全)，用于字符串缓冲区被单个线程使用的时候。大多数实现，它比StringBuffer要快。

主要操作append和insert

​	StringBuilder继承AbstractStringBuilder类

​	实现了Serializabale，说明StringBuilder对象是可以串行化(可以网络传输，可以保存到文件)

final类不能被继承

StringBuilder对象字符序列仍然存放在其父类AbstractStringBuilder的 char[] value；因此，字符序列是在堆中

StringBuilder的方法，没有做互斥的处理，没有在synchronized关键字，因此在单线程情况下使用



Arrays类

1.toString 返回数组字符串形式

2.sort排序(自然排序和定制排序)

3.binnarySearch 通过二分搜索法进行查找，必须排好序

​	二叉查找 必须有序才能查找

4.copyOf 数组的复制

```
Integer[] newArr = Arrays.copyOf(arr, arr.length);
从arr输中，拷贝arr.length个元素到newArr数组中
如果拷贝长度>arr.length就在新数组的后面增加null
```

5.fill元素的填充

```
Integer[] num = new Integer[](9,3,2)
Arrays.fill(num,99);
使用99去替换原来的元素。
```

6.equals比较两个数组袁术内容是否一致

```java
boolean equals =Arrays.equals(arr,arr2)
```

7.asList将一组值，转换成list

```java
List <Integer> asList = Arrays.asList(2,3,4,5,6,1)
System.out.println("asList=" + asList);
```

System类

1.exit退出当前程序

2.arraycopy：复制数组元素，比较适合底层调用，一般使用Arrays.copyOf

3.currentTimeMillens：返回当前时间距离1970-1-1的毫秒数

4.gc：运行垃圾回收机制 System.gc( )；

bigInteger 处理大的整数

BigDecimal 处理精度很高的小数



```java
创建SimpleDeleteFormat对象可以指定相应的格式
SimoleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 hh:mm:ss E");
String format = sdf.format(d1)；

```

![image-20220926154122681](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220926154122681.png)



```java
1.获得当前系统时间
2.date类在java.util包内
3.默认输出格式是国外的方式，要对格式进行转换
Date d1 = new Date(); 获取当前系统时间
Date d2 = new Date(9234567);通过指定毫秒数得到时间
System.out.println(d2)获取某个时间对应的毫秒数
    
1.创建SimpleDateForma对象，可以指定相应的格式
2.这里格式使用规定好的
SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 hh:mm:ss E");
String format = sdf.format(d1);format将日期转换成指定格式的字符串
System.out.printf(format);;

1.可以把一个格式化的String转换对应的Date
2.得到Date 仍然输出时，还是按照国外的方式，如果希望指定格式输出，需要转换
3.在把String -> Date，使用的sdf格式需要和给的String的格式一样，否则会抛出异常
String s = "1996年01月01日 10:20:30 星期一";
Date parse =sdf.parse(s);
System.out.printf(sdf.format(parse));
```





















































