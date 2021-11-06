## 目录

1、Java学习方法介绍、第一阶段课程以及学习目标介绍

2、常用DOS命令、JDK环境安装

3、Java数据类型、类型转换

4、运算符（赋值、算数、逻辑、关系、三目（三元）运算符）

5、if、if-else、switch、break、多重条件

6、for、while、do-while

7、循环嵌套、循环终止

8、方法的概念、方法的定义、方法的组成、方法的调用

9、方法的形参与实参、方法的返回值类型与返回值、return的两种用法、递归

10、数组的引言、数组的概念、数组的创建、数组的使用

11、数组的复制、数组的扩容、数组参数和返回值、可变长参数

12、3种排序、二维数组

13、杨辉三角

14、面向对象

15、构造方法、构造方法重载、有参构造和无参构造各自作用、this关键字

16、成员变量、成员方法、成员变量和局部变量区别

17、封装、什么样的代码需要封装、继承

18、多态、访问修饰符

19、super、super和this区别

20、三个修饰符、静态方法、静态代码块、普通代码块、抽象类的定义、抽象类的作用

21、接口的语法、与抽象类的异同、接口的微观概念、接口规范、接口引用、接口的多态、接口和抽象类的区别和用途（接口定义规范、抽象类定义差异）

22、什么是内部类、成员内部类、静态内部类、局部内部类、局部内部类访问外部类局部变量

23、局部内部类的应用场景、匿名内部类、Object类、getClass方法、hashCode方法、toString方法、equals方法、equals方法重写、finalize方法

24、什么是包装类、8种包装类型、装箱和拆箱的常用方法、整数类型的缓冲区

25、String类、字符串的不变性、字符串的常用方法、可变字符串

26、什么是集合、Collection体系集合、Collection父接口、List子接口、ArrayList、LinkedList、Vector

27、线性表与链表的区别和优劣、泛型集合、Collections工具类

28、Set子接口、HashSet、HashSet去重原理、重写hashCode与equals、LinkedHashSet、TreeSet、TreeSet去重原理

29、算法时间复杂度、空间复杂度、排序算法、查找算法、数据结构

30、什么是异常、异常体系分类、异常的产生、异常的传递、throws、异常的处理（try、catch、finally）、自定义异常

31、什么是进程、什么是线程、线程的组成、创建线程的两种基本方式、线程状态

32、线程安全问题、同步代码块、同步方法、线程状态（6状态）、死锁问题、生产者消费者、线程通信（wait、notify、notifyAll）

33、线程池概念、线程池原理、线程池相关接口与类、Callable接口、Future接口、Lock接口、重入锁、读写锁

34、线程安全集合、Collections工具获得线程安全集合、CopyOnWriteArrayList

35、线程案例

36、流的概念、流的分类、字节流、字节节点流、字节过滤流

37、File、FileFilter、字符编码、字符流、字节过滤流、流的标准使用步骤、[XML]

38、对象序列化

39、IO流综合案例

40、什么是网络、什么是计算机网络、网络模型、TCP/IP模型、TCP/UDP、IP、IPV4应用分类、Port端口

41、InetAddress类、基于TCP的网络编程、开发步骤

42、Lambda表达式、Stream API、Date Time API、Optional类

43、什么是类对象、获取类对象、Class的常用方法、注解

44、DOM4J、SAX

45、游戏面板、游戏按钮、游戏逻辑、游戏数据读取、游戏线程控制、游戏计分算法、游戏血量算法等

46、完成小游戏项目

## Spring

### jdk配置

常用版本：1.8.0；1x.0

环境变量

名称：JAVA_HOME	值：jdk安装路径

名称：CLASSPATH	值：.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;

名称：Path	值：%JAVA_HOME%\bin	和	%JAVA_HOME%\jre\bin

检查：输入java，javac
