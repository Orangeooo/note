## 路线

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

### maven

### springboot

Spring Boot是由Pivotal团队提供的全新框架，其设计目的是用来简化Spring应用的初始搭建以及开发过程。 -使用springboot以后,搭建一个spring应用和开发变得很简单

在pom文件中

spring boot 父节点依赖,引入这个之后相关的引入就不需要添加version配置，spring boot会自动选择最合适的版本进行添加。

```
<!--统一管理版本-->
<parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.5.2</version>
</parent>
```

#### 依赖

```
<dependency>
	<!--web依赖-->
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-web</artifactId>
	</dependency>
	
	<!--热部署依赖-->
	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-devtools</artifactId>
		<optional>true</optional>
		<scope>true</scope>
	</dependency>

	<!--mysql驱动-->
	<dependency>
		<groupId>mysql</groupId>
		<artifactId>mysql-connector-java</artifactId>
	</dependency>
	
	<!--mybatis的依赖-->
	<dependency>
		<groupId>org.mybatis.spring.boot</groupId>
		<artifactId>mybatis-spring-boot-starter</artifactId>
		<version>2.2.0</version>
	</dependency>
	
	<!--Swagger依赖-->
    <dependency>
      <groupId>io.springfox</groupId>
      <artifactId>springfox-swagger2</artifactId>
      <version>2.8.0</version>
    </dependency>
    <dependency>
      <groupId>io.springfox</groupId>
      <artifactId>springfox-swagger-ui</artifactId>
      <version>2.8.0</version>
    </dependency>
    <dependency>
      <groupId>com.github.caspar-chen</groupId>
      <artifactId>swagger-ui-layer</artifactId>
      <version>1.1.2</version>
	</dependency>

</dependencies>
```
#### 打包插件

```
<build>
	<plugins>
		<plugin>
		<!--springboot的maven插件-->
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-maven-plugin</artifactId>
		<version>2.2.6.RELEASE</version>
		<executions>
			<execution>
				<goals>
					<goal>repackage</goal>
				</goals>
			</execution>
		</executions>
		</plugin>
	</plugins>
</build>
```

### 三层结构

controller控制层

service业务层

dao持久化层

entity实体：私有属性，get/set，toString，满参构造，无参构造

#### 普通项目

结构

www
	project
		controller
			UserController
		dao
			UserDao
		entity
			UserEntity
		service
			impl
				UserServiceimpl
			UserService
		UserApplication

resources
	www
		project
			dao
				UserDao.xml
			application.yml

UserController

```java
@RestController
public class UserController {

    @Autowired
    UserService userService;
    @RequestMapping("queryUser")
    public List<User> queryUser(){
        List<User> users = userService.queryAllUsers();
        return users;
    }
}
```

UserDao

```java
public interface UserDao {

    List<User> queryAllUsers();
}
```

UserService

```java
public interface UserService {

    List<User> queryAllUsers();
}
```

UserServiceimpl

```java
@Service
public class UserServiceimpl implements UserService {
    @Resource
    UserDao userDao;

    @Override
    public List<User> queryAllUsers() {
        List<User> users = userDao.queryAllUsers();
        System.out.println(":"+users);
        return users;
    }
}
```

UserEntity

```java
public class User {

    private long id;
    private String username;
    private String sex;

    public User() {
    }

    public User(long id, String username, String sex) {
        this.id = id;
        this.username = username;
        this.sex = sex;
    }

    @Override
    public String toString() {
        return "User{" +
                "id=" + id +
                ", username='" + username + '\'' +
                ", sex='" + sex + '\'' +
                '}';
    }

    public long getId() {
        return id;
    }

    public void setId(long id) {
        this.id = id;
    }

    public String getUsername() {
        return username;
    }

    public void setUsername(String username) {
        this.username = username;
    }

    public String getSex() {
        return sex;
    }

    public void setSex(String sex) {
        this.sex = sex;
    }
}
```

启动类

```java
@MapperScan("www.project.dao")
@SpringBootApplication
public class UserApplication {

    public static void main(String[] args) {
        SpringApplication.run(UserApplication.class);
    }
}
```

UserDao.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper PUBLIC "-//mybatis.org/DTD Mapper 3.0" "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="www.qianfeng.dao.UserDao">

    <select id="queryAllUsers" resultType="www.qianfeng.entity.User">
        select * from user
    </select>

</mapper>
```

application.yml

```yaml
spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://1.117.54.58/test
    username: king
    password: cyh@CYH!0427
server:
  port: 8080
```

#### web项目

结构

www
	project
		controller
			UserController
		dao
			UserDao
		entity
			UserEntity
		service
			impl
				UserServiceimpl
			UserService
		UserApplication

webapp
	WEB-INF
		web.xml
	index.jsp

```
<!--mysql驱动-->
<dependency>
  <groupId>mysql</groupId>
  <artifactId>mysql-connector-java</artifactId>
</dependency>
```
