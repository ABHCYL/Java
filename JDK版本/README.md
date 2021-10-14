### 一：JDK8与 JDK11版本切换
首先在本机上安装好Jdk8和Jdk11。
 
在win10下，环境变量。 
如果不需要多个jdk版本，只需一个JAVA_HOME变量（把JDK的路径作为变量的值）即可。
 
为了方便管理切换JDK版本，把不同的JDK新建成不同的变量，比如说，JDK8的变量叫JAVA_HOME8，JDK11的变量叫JAVA_HOME11.

在JAVA_HOME中不再是JDK的绝对路径（直接填写不同JDK版本的各自的路径当然可行，但是不便于切换），只需填入%JAVA_HOMEXX%即可，如下图。

使用JDK8  

![](https://raw.githubusercontent.com/ABHCYL/pitcure/main/jdk8.png)   

使用JDK11  

![](https://raw.githubusercontent.com/ABHCYL/pitcure/main/jdk11.png)   

按理说，版本切换到这里就应该成功了。但是，在我的电脑上，更改JAVA_HOME变量的指向只是切换了javac的版本，而Java版本没有跟着变动。如图  

![](https://raw.githubusercontent.com/ABHCYL/pitcure/main/javac_version.png) 
![](https://raw.githubusercontent.com/ABHCYL/pitcure/main/java_version.png) 

按网上的解决办法，存在一个路径（下图第一个变量值），   
![](https://raw.githubusercontent.com/ABHCYL/pitcure/main/javapath.png)   

在此路径中有3个exe文件（即命令java），  
![](https://raw.githubusercontent.com/ABHCYL/pitcure/main/javapath_exe.png)   

在安装第一个jdk8时，安装包会把这3个exe（对于8版本）安装在这个路径位置，并且这个位置在路径查找时优先级比用户自定义的JAVA_HOME更高，所以运行时的java version是8而javac是11 version，解决办法很简单，删掉3个exe文件就好了。

如下图，javac 和java 版本一致。   
![](https://raw.githubusercontent.com/ABHCYL/pitcure/main/javacequaljava.png)
