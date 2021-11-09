# 第一章 Java程序设计概述

Java特点：

简单性；面向对象；分布式；健壮性；安全性；体系结构中立；可移植性；解释型；高性能；多线程；动态性

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

## hello,world demo

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

单行

//

多行

/*

*/

自动生成文档

/**
  *
  *
  */

多行注释不能嵌套

## 数据类型

### 整型

int				4字节				-2 147 483 648~2 147 483 648

short			2字节				-32 768 - 32 767

long				8字节				-9 223 372 036 854 775 B08 - 9 223 372 036 854 775 807

byte				1 字节				-128~127

