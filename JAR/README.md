### 一：编译有关的.java文件
比如有两个.java文件：PersonAddress.java和PersonAddresstest.java。
一个是工具类，一个测试类。如图：
![](https://raw.githubusercontent.com/ABHCYL/Java/main/JAR/%E7%BC%96%E8%AF%91.png)
### 二：生成jar
#### 方法1：在命令行中指定主类
把两个文件打包到一个名为PersonAddresstest的jar里，同时，想要在命令行中指定主类，而不是提前写一个.MF文件，需要使用命令。
> jar -cvfe PersonAddresstest.jar PersonAddresstest PersonAddress.class PersonAddresstest.class
![](https://raw.githubusercontent.com/ABHCYL/Java/main/JAR/cvfe.png)
在jar -cvfe 中，第1个参数是XXX.jar，第2个是主类的名字（就是带有main方法的类，不要加.class后缀），后面的参数是需要打包的类的名字（有.class后缀）。
#### 方法2：提前写一个.MF文件
不想要在命令行中指定主类 ，而是提前写一个.MF文件。
在XXX.MF文件中，需要添加第三行Main-Class: XXX（XXX是主类名字）。
比如
![](https://raw.githubusercontent.com/ABHCYL/Java/main/JAR/mf.png)

然后使用命令
> jar -cvfm PersonAddresstest.jar XXX.MF PersonAddress.class PersonAddresstest.class
![](https://raw.githubusercontent.com/ABHCYL/Java/main/JAR/cvfm.png)
在jar -cvfm 中，第1个参数是XXX.jar ， 第2个是XXX.MF，后面的参数是需要打包的类的名字（有.class后缀）。
### 三：运行.jar里指定的主类
> java -jar  PersonAddresstest.jar

或者( -cp ) 可以指定路径，但我不会。
> java -cp XXX.jar PersonAddresstest    
注：使用java -cp在XXX.jar后面要写主类名字。

![](https://raw.githubusercontent.com/ABHCYL/Java/main/JAR/%E8%BF%90%E8%A1%8C.png)
### 四：查看.jar的目录
.jar是一个压缩包，命令 cd 是无法进入的想要查看.jar里有什么文件，需要指令：
> jar -tf XXX.jar
![](https://raw.githubusercontent.com/ABHCYL/Java/main/JAR/tf.png)

参考：
![java打jar包的几种方式详解](https://www.cnblogs.com/mq0036/p/8566427.html)
