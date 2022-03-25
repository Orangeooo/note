# 第一章 Java程序设计概述

Java特点：

简单性；面向对象；分布式；健壮性；安全性；体系结构中立；可移植性；解释型；高性能；多线程；动态性

交互方式：GUI，CLI 

JVM：java虚拟机，运行java程序

垃圾回收机制

# 第二章 Java程序设计环境

## 术语

JDK：Java Development Kit

JRE：Java Runtime Environment

SE：Standard Edition

EE：Enterprise Edition

ME：Micro Edition

Java FX

OpenJDK：JavaSE 的 一个免费开源实现

## 安装JDK

**下载**

[JDK下载地址](https://www.oracle.com/java/technologies/downloads/#java8)

推荐版本：Java SE Development Kit 8u311，Java SE Development Kit 11.0.13

**设置环境变量**

设置>系统>关于>高级系统设置>环境变量

```
JAVA_HOME:
C:\Program Files (x86)\Java\jdk1.8.0_291

CLASSPATH:
.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;

PATH:
%JAVA_HOME%\bin
%JAVA8_HOME%\jre\bin
```

cmd验证：

```
java
javac
```

.java-javac.exe->hello.class-java.exe->结果

javac程序是一个Java编译器，它将文件.java文件编译成.class文件

```
javac hello.java
```

java启动Java虚拟机执行.class文件中的字节码

```
java hello
```

之后使用集成开发环境IntelliJ IDEA

# 第三章 Java的基本程序设计结构

## hello,world

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("hello,world");
    }
}
```

## 类名命名规范及注意事项

以字母开头

不能使用保留字

长度无限制

驼峰命名法

源代码的文件名必须与公共类的名字相同

大小写敏感

main 方法必须声明为 public

## 注释

```java
//单行

/*
多行
*/

/**
	文档注释
	@author
	@version
  */
```

文档注释内容能被javadoc解析

多行注释不能嵌套

## 关键字/保留字

class等

## 数据类型

### 基本数据类型

#### 整型

int				4字节				-2^31~2^31-1

short			2字节				-2^15~2^15-1

long				8字节				-2^63~2^63-1

byte				1 字节				-128~127 

long型声明以l/L结尾

long l1 = 12L;

#### 浮点型

float				4byte				单精度				-3.403E38~3.403E28

double				8byte				双精度				-1.798E308~1.798E308

float型声明以f/F结尾

float f1 = 1.32F;

#### 字符型

char				2byte

char c1 = 'a';

转义符

\n

#### 布尔型

true

false

### 自动类型提升

byte + int = int 

float + int = float

byte , char , short 运算 = int

double > float > long > int > short > byte

### 强制类型转换

```
double d1 = 12.3;
int i1 = (int)d1;
```

### 引用数据类型

String s2 = "assd"

可以和基本数据类型做连接

## 运算符

算数运算符

赋值运算符

比较运算符

#### 逻辑运算符

& 与 && 区别

结果一样，&&短路

#### 位运算符

对整数的二进制运算

`>>>`无符号右移

异或 ^

m = (m ^ n) ^n

#### 三元运算符

（条件）？表达式1：表达式2

##  流程控制

分支结构

```java
if(条件一){
    
}
else{
    
}

if(条件一){
    
}
else if(条件二){
    
}
else{
    
}

switch(变量)
    case 常量1
        语句一
    case 常量2
        语句二
    default:
        语句三
}

break;//默认跳出当前最近包裹的语句
continue;//默认跳出当次最近包裹的语句

switch中的表达式只能是byte，short，char，int，
```

循环结构

```java
for(;;){

}

while(){

}

do{
    
} while(); 

break;//结束当前循环
continue;//结束当次循环
//关键字后不能写执行语句

//跳出指定循环
lable:for(){
    for(){
        break lable;
    }
}
```



## Scanner输入

```java
Scanner scanner = new Scanner(System.in);
int num = scanner.nextInt();
String st = scanner.next();
```

## 数组

长度确定后不能修改

```java
int[] num = new int[3];
int[] num = new int[]{1,2,3};
int[] num = {1,2,3};//类型推断
//索引从0开始
num[0] = 1;
```

### 内存结构

栈stack：局部变量

堆heap：new出的结构：对象，数组

方法区：常量池，静态域

数组地址存在栈中，指向堆中的数组空间，空间内存放内容

### 二维数组

数组地址存在栈中，指向堆中的数组空间，空间内存放数组地址，指向新的数组空间，新的数组空间中存放内容

```java
int[][] arr = new int[][]{{1,2,3,4},{3,4},{4,5,6}};
int[][] arr = new int[3][2];
//长度
arr.length//3
arr[0].length//4
```

杨辉三角

回环数

6个数，1-30之间随机且不重复

### 数组赋值

```java
//赋值是地址值，堆空间中不变
array2 = array1;

//数组复制
array2 = new int[array1.length];
```

### 排序

内部排序，外部排序

#### 选择排序

直接选择排序，堆排序

#### 交换排序

冒泡排序，快速排序

#### 插入排序

直接插入排序，折半插入排序，希尔排序

#### 归并排序

#### 桶式排序

#### 基数排序

### array工具类

```java
//判断两个数组相等
boolean equals(int[] a,int[ b])

//输出数组信息
String toString(int[] a)
Arrays.toString
//填充指定值到数组
void fill(int[] a,int val)

//排序
void sort(int[] a)

//堆排序后的数组进行二分法检索
int binarySearch(int[] a,int key)
```

### 常见异常

角标越界异常

空指针异常

### JVM内存结构

类装载器

方法区，虚拟机栈，堆，本地方法栈，程序计数器

垃圾收集器

执行引擎

本地接口库

# 第四章 面向对象

类及类的成员

属性，方法，构造器；代码块，内部类

三大特征

封装，继承，多态

关键字

this，super，static，final，abstract，interface，package，import

### 属性与局部变量

属性：定义在类中，有默认值，可以使用权限修饰符

局部变量：定义在方法中，没有默认值，不可使用权限修饰符

权限修饰符：private，default（缺省），protected，public

### 匿名对象

```java
new class.methon();
```

### 方法

重载：同名方法，参数不同

可变个数形参：

```
public void methon(String ... string){

}
相当于
public void methon(String[] string){

}
必须声明在末尾
```

方法参数的值传递机制：

形参：方法声明时的参数

实参：方法调用时实际传给形参的参数值

值传递：基本数据类型

引用传递：引用数据类型

递归

Tower of Hanoi

### 封装与隐藏

private

get，set

#### 权限修饰符

private：类内部

default：同一个包内

protected：不同包的子类

public：同一个工程

### 构造器

未定义时默认提供空参构造器

JavaBean

UML类图

### this

this表示当前对象或正在创建的对象，通常省略

特殊：类的方法的形参与类的属性重名，修饰属性

特殊：构造器的形参和类的属性重名

#### this调用构造器

this(形参列表);调用其他构造器 ,必须放在首行

### MVC设计模式

model，controller，view

model.bean/domain,model.dao,model.db

controller.activity,controller.fragment,controller.adapter,controller.service,controller.base

view.utils,view.ui

### import

import static

导入类或接口中的静态结构
