---
title: JAVA
tags:
  - 复习
categories: JAVA
hide: true
abbrlink: 40121
date: 2021-04-17 23:41:21
---

# JAVA

### 题目

```
程序不能选择忽略事件。   错

java 不能重写在超类中定义的静态方法

构造方法可以是静态的

数组中的元素可以不是是基元数据类型。比如指针,结构体型

在Java 1.8中，“检查异常”必须在程序中处理。

Java允许创建不规则数组，即Java多维数组中各行的列数可以不同。( )

一个Java类可以不能有多个父类。

声明为final的方法不能在子类中被覆盖。

一个非抽象类不可以有选择地实现接口的部分抽象方法。    要实现所有，抽象类才能有选择

受保护的数据或方法可以由任何包中的子类访问。

受保护的数据或方法不可以由不同包中的任何类访问

元注解不能用于注解Java程序中的类的成员方法。

final类可以有实例，不能拓展

子类和父类可以不在一个包中

如果方法中发生必检异常，则必须捕获该异常或在其方法头中声明该异常。

在Java程序中，不能使用protected来修饰一个类。

抽象类是不能实例化的。

类及其属性、方法可以同时有一个以上的修饰符来修饰。

private 修饰的成员变量或方法的可见范围为当前类。 没有权限修饰符修饰的成员变量或方法的可见范围为当前包。 
protected 修饰的成员变量或方法的可见范围是当前包及该类的子类，即可以被同一个包、该类的子类（可以不同包）的方法访问。 
public修饰的成员变量或方法可以被所有包中所有类中的方法访问

java应用程序经过编译后会产生一个以（.class ）为扩展名的字节码文件,Java应用程序源文件的扩展名为(java )。

Java应用程序由若干个类所构成,这些类可以在一个源文件中,也可以分布在若干个源文件中,其中必须有一个源文件含有主类。

sizeof不是java关键字

abstract修饰抽象类抽象方法，抽象类一定要被继承，抽象方法一定要被重写

自动转换次序.byte->short->int->long->float->double

定义合法标识符规则：
 （1）由26个英文字母大小写，0-9 ，_或 $ 组成
 （2）数字不可以开头。
 （3）不可以使用关键字和保留字，但能包含关键字和保留字
 （4）Java中严格区分大小写，长度无限制
 （5）标识符不能包含空格

class表示___类;类对象__; *.class表示___类文件___; *.java表示__java文件___; java文件编译后是___class;类__文件


A.构造方法的主要作用是完成对类的对象的初始化工作
B.构造方法的返回类型只能是void型，即在方法名前加void    错
C.一般在创建新对象时，系统会自动调用构造方法
D.构造方法是类的一种特殊方法，它的方法名必须与类名相同

一个Java文件中可以定义有多个class声明，并且类名称可以与文件名称同名

(1)final类不能实现任何接口。
(2)public接口可以被任何一个类实现。
(3)友好类和它所实现的接口必须在一个包里。
(4)如果一个类和友好接口在同一个包里，就允许它实现该接口。  13错


```

### 代码

```java
switch(变量){

　　　　　　case 值:要执行的语句;break;

　　　　　　…

　　　　　　default:要执行的语句;

　　　　}

	Scanner num=new Scanner(System.in);

	nextLine（）方法返回的是Enter键之前的所有字符，它是可以得到带空格的字符串的。

	next（）会自动消去有效字符前的空格，只返回输入的字符，不能得到带空格的字符串。
    （简单点说，next我只要字，nextLine我啥都要）
    
1.十进制转成二进制

	String s = Integer.toBinaryString(n)  //将十进制数转成字符串，例如n=5 ，s = "101"

2.将字符串转成整形

	int a = Integer.valueof("1002");  //当然s只能是数字类的字符串

或者

	int a = Integer.parseInt("1002");

3.将整形转成字符串
	String s = String.valueof(1025);  直接转成了

 

4.将整形转成十六进制的数

String s = Integer.toHexString(18);   //输出结果12

1	isLetter()
是否是一个字母
2	isDigit()
是否是一个数字字符
3	isWhitespace()
是否是一个空白字符
4	isUpperCase()
是否是大写字母
5	isLowerCase()
是否是小写字母
6	toUpperCase()
指定字母的大写形式
7	toLowerCase()
指定字母的小写形式
8	toString()
返回字符的字符串形式，字符串的长度仅为1
    
    
    private String value;
	value=value.toUpperCase();//转大写


	private  String word;
	word=word.substring(0,1).toUpperCase()+word.substring(1).toLowerCase();
	//首字母大写，其他小写
	word.substring(0,1)//0开始到1分隔
        
        String s=sc.next();  输入11:20
		
		String x[]=s.split(":");//通过":"分隔字符串,x[0]="11",x[1]="20"
		int a=Integer.parseInt(x[0]);
		int b=Integer.parseInt(x[1]);

	System.out.printf("The BMI is %.4f",BMI);//保留四位小数
```

```
 //异常
 public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    while (sc.hasNext()) {
        String choice = sc.next();
        try {
            if (choice.equals("number"))
                throw new NumberFormatException();
            else if (choice.equals("illegal")) {
                throw new IllegalArgumentException();
            } else if (choice.equals("except")) {
                throw new Exception();
            } else
            break;
        }
        /*这里放置你的答案*/
        catch(NumberFormatException e) {
        	System.out.println("number format exception");
        	System.out.println(e);
        }
        catch(IllegalArgumentException e) {
        	System.out.println("illegal argument exception");
        	System.out.println(e);
        }
        catch(Exception e) {
        	System.out.println("other exception");
        	System.out.println(e);
        }
    }//end while
    sc.close();
}
 
 
```




```java



这是别人发的
DAY_01
1.Java源代码（通过javac编译为）->字节码文件->执行并运行结果
2.DOS 运行JAVA常见错误：
文件名被隐藏——隐藏已知类型的扩展名 这个√取消
javac +文件名+扩展名	java+类名 不带扩展名
3.
path环境变量配置作用：
程序执行需要使用外部指令javac,但是javac指令仅仅能在JDK安装目录
下的bin目录下使用。而程序开发的时候，不能将源代码写入JDK的安装目录
，因此需要将源程序保存到任意位置的指定目录
classpath作用：
设定为class文件的目录，使classpath目录中的.class可以在任意目录运行

DAY_02
4.关键字全部小写	goto和const是保留字
5.包其实就是文件夹，用于把相同类名进行区分
类或者接口：每个单词首字母大写 方法变量：从第二个单词开始首字母大写
文档注释/** **/
6.8421码 是bcd一种
7.!!!
byte b1 =3,b2 = 4,b;
b=b1+b2;//类型提升，将byte转化为Int类型
b=3+4;//常量相加，先把结果计算出来，然后再转为对应类型
XJad:将.class文件反编译为java文件
8.计算机中数据运算都是补码进行的
获取int a = 130二进制->做截取，截成byte->已知补码求原码
其中第三步：
补码 10000010->反码 10000001 -> 原码 11111110
由此byte 130 为-126
9.看程序写结果
字符和一个整数相加，println('a'+1) = 97+1=98
字符串数据和其他数据做+，这个+是字符串连接符

DAY_03 _04
1.&有false则false | 有true则true ^(异或) 相同为false
2.Alt+/自动填充函数
3.println("")里头可以输出汉字
Scanner in  =new Scanner(System.in);
System.out.println("echo:"+in.nextline());
System.out.println("2+3="+(2+3）);
4.ctrl+/ 注释代码或解开注释
5.System.out.println("100-"+in.nextInt()+"="+(100-nextInt()));要输入两次
6.return 不是结束循环，而是结束方法

DAY _05
1.数组逆序（元素对调）
返回值类型 void！！！（无需返回，void返回的就是数组地址）
for(int x=0; x<arr.length/2;x++){
	int temp = arr[x];
	arr[x] = arr[arr.lenght-1-x];
	arr[arr.length-1-x] = temp;
}
2.final int 常量定义
3.void类型 没有明确的返回值 直接输出
不能够输出调用 赋值调用 因为println不能是空类型
4.数组初始化有动态、静态两种方式，只能任选其一：
	动态：int[] arr = new int [3]  
	静态：int[]arr ={}  new可以看成是为arr分配地址
5.栈：存放局部变量
	栈的特点：用完即释放
堆：堆放所有new出来的东西
堆的特点：每个都有地址值 都有初始值 使用完毕变成垃圾，没有立即回收，会在空闲时回收
Array Index Out of Bound Exception:数组索引越界
Null Pointer Exception:空指针异常 

DAY_06
1、二维数组 定义格式 
推荐：数据类型 [][] 数组名 = new 数据类型[m][n]
其他：数据类型 数组名[][] = new 数据类型[m][n]
          数据类型[] 数组名[] = new 数据类型[m][n]
2.一个java文件中写两个类：一个基本的类，一个测试类
	在测试类（含主函数）中编译Java文件，会将该类所涉及的所有类都编译成class
	报错实参形参长度不同，一定是没有给一定数量的参数或者压根没有给参数
3.main 方法储存在栈里头，然后在堆里储存类的代码，最后调用在方法区的方法

DAY_07
1.成员变量与局部变量的区别
	成员变量在类中方法外 局部变量在定义中或方法声明上
	成员变量在堆内存，局部变量在栈内存
	成员变量随着对象的创建而存在，局部变量随着方法调用存在
	成员变量有默认初始化值，局部变量必须定义赋值然后才能使用
2.类型包括基本数据类型、引用类型（数组、类、接口）
  形式参数的改变直接影响实际参数（如果是引用类型的话）
  方法里头调用一个类，此时传进去的是类的地址
3.匿名对象：没有名字的对象 可以作为实际参数传递
  new student.show()不适合多次调用，用完被垃圾回收器回

DAY_08
1.在同一个文件夹下，类定义在一个文件还是两个文件下相同
2.构造代码块在构造函数之前执行，且出现在类中的成员位置
局部代码块用于限定变量的声明周期 静态代码块与构造代码块类似，只是用static修饰了
构造代码块只需要在代码外面有一个大括号，在一个类中代码无法在成员变量的位置直接执行
例如：class demo{ System.out.println(100) public demo(){}}中的输出是无法执行的
3.开发的原则：低耦合，高内聚 耦合：类与类之间的关系 内聚：自己完成事件的能力
4.子类不能继承父类的私有变量和私有方法，即只能继承父类所有非私有的成员
5.举例输出子类局部、成员、继承的父类变量
public void show(){
	int num = 30;
	System.out.println(num);
	System.out.println(this.num);
	System.out.println(super.num);
}
this()调用本类成员变量的构造方法，super()调用父类的构造方法 同理，super.方法，this.方法
6.子类所有构造方法默认会访问父类的【空参数】构造方法 子类初始化之前一定要先完成父类的初始化
7.父类如果只有一个含参构造函数，那么默认的无参构造函数会消失
因此要在父类加入一个无参构造函数；或者使用super()调用父类的含参构造函数
或者通过this()调用一个访问了父类构造方法的成员方法 而且this super必须在第一个语句上
8.public void call(String name){
	super.call(name);
	······；
}方法的重写	子类不能访问权限比父类更低 比如不可以子类为void 父类为public
父类用静态方法，子类也必须用静态方法重写

Day 09:
1、final 可以修饰类、方法、变量，此时父类的功能不能被覆盖
最终类不能被继承 final的方法 叫覆盖、重写、复写
final修饰基本类型：值不能发生改变 修饰引用类型：引用地址不能发生改变
2、多态：有继承关系、有方法重写、有父类引用指向子类对象
子类可以访问父类的变量，但是父类不能访问子类的变量 多态中成员变啦领编译运行看左边
成员方法的编译看左边，运行看右边
弊端：不能使用子类特有的功能
向下转型：把 Zi z = (Zi) f f能转化为zi
3、抽象类具有构造方法，但是不能实例化
4、接口没有构造方法 接口方法不能有主体

ctrl shitf f 格式化 ctrl shitf o 导包
Integer.toHexString 整数转为十六进制
public String toString(){
	return 
}

DAY 12
1、字符串一旦被赋值，就不能改变 String s 值不能变，但是引用s可以变
2、String s = new String("hello")创建2个对象,String s = "hello"创建1个对象
3、== 比较引用对象，是比较地址，equals默认是地址，但是String改写后 判断内容相等
4、字符串相加：如果是变量，先开空间再拼接，如果是常量，先加然后在常量池寻找 
有就返回
5、字符串内容为空 String s  = "",字符串对象为空 String s = null
6、boolean equals() 比较字符串内容是否相同，区分大小写
boolean equalsIgnoreCase() 比较自妇产内容是否相同，忽略大小写
boolean contains() 判断大字符串中是否包含小字符串
boolean startsWith() 判断字符串是否以某个指定的字符串开头
boolean isEmpty() 判断字符串是否为空
7、byte [] getBytes 把字符串转换为字节数组
char [] toCharArray() 把字符串转换为字符数组
static String valueof(char[] chs) 把字符数组转换为字符串
string.toLowerCase() 把字符串转成小写
compareTo 函数 按字典顺序比较两个字符串
8、Arrays.toString（arr）把arr转成字符串 Arrays.sort(arr)数组排序 
Integer.toString(number)  String s = "" + number String.valueof(number) int->String
String->Int: str.intValue()  Integer.parseInt(a)
9、Integer.toBinaryString()十进制转到二进制 Integer.toOctalString() 转到八进制
十进制转到其他进制： Integer.toString(num，rad)
其他进制转到十进制：Integer.parseInt("num",rad)
10、try{
	可能出现的问题
	}catch（异常名 变量比如：ParseException e）{
	针对问题的处理
System.out.println(e.getMessage());
	}（finally{
	释放资源
	}）
11、Exception e 所有异常的父类 simpleDateFormat("yyyy-MM-dd HH:MM:ss")
12、如果要自己写一个异常类 需要继承自Exception 或者 继承自RuntimeException



字符串考点
spllit方法 抽象类不能实例化 异常处理机制 数组的定义 
回文 二进制 三角函数 随机数 栈、队列 
```