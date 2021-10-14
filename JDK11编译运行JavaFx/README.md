## JDK11编译运行JavaFx的命令行方法
Java11把JavaFx包从jdk分离出去，所以用JDK11需要先下载FX的包。
在我的电脑上安装位置如下图（重要：不要把javafx-sdk-17.0.0.1放在复杂的带空格的路径，否则会导致无法察觉的细小错误，我因此浪费了1个小时）
![](https://raw.githubusercontent.com/ABHCYL/pitcure/main/javafx-sdk.png)

指定路径"N:\javafx-sdk-17.0.0.1\lib"

>使用形如
javac --module-path "N:\javafx-sdk-17.0.0.1\lib" --add-modules javafx.controls your.java
的命令行编译

>使用形如
java --module-path "N:\javafx-sdk-17.0.0.1\lib" --add-modules javafx.controls your
的命令行运行
