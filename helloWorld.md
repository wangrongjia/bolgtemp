# helloWorld
## 1 Java是什么
java是一门编程语言，不同于汇编这种低级的计算机编程语言,java作为高级编程语言，需要运行环境,java 的运行环境就是jre(java runtime enviroment)   只是运行java程序的话，jre就够了.jre中就有java最重要的东西   jvm   java虚拟机  ,虚拟机是的java的灵魂， java要跨平台，一次编译，到处执行，就是靠它实现的.现在在jvm上运行的语言也不仅是java   groovy,scala,kotlin等  可见jvm的优秀,而jvm的深入研究是我们深入学习了java的基础,并对ee阶段有所涉猎后才会去研究的.开发的话  就需要jdk(java development kit)   开发工具包.

## 2 java和其他主流编程语言相比

现在比较主流的编程语言有哪些呢，C语言作为高级编程语言的鼻祖，其地位自然不可撼动，像windows,unix,linux这些操作系统的核心部分都是用c和c++写的（某些底层用的是会汇编，但是现在有耐心去啃汇编我也是服气的），jvm也是如此，用的是c和汇编搞出来的，那为什么要选择java呢？因为简单啊，C不是所有人都能搞得懂的（听说一个指针就可以难倒大部分人了）。然后java和c++相比，C++性能方面比java优越（难度应该比java稍微高），但是开发效率就不如java了，因为java开发人员众多，框架多。其他的编程语言就没什么值得比较了，想最近好多人都想要学的python(听所是入门快，前途光明，值得入手)，google大力推广的Go语言，付出相同的时间，前途不一定会比java好到那里去。

## 3 jdk下载与安装  

官网： [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html)    下载对应系统和位数的就可以了，一键式安装。

## 4 环境变量的配置

`系统变量` 中新增    `JAVA_HOME`  的变量    值为   jdk安装目录

![JAVA_HOME 变量](https://wxpp.oss-cn-qingdao.aliyuncs.com/blogimages/helloworld/942777-20170719190622021-2038048019.png)


同样的 ，`系统变量` 新增 类路径系统变量 `CLASSPATH`   值为 `%JAVA_HOME%/lib`  这一步的目的是在任何路径下都可以引用jdk自带的jar包

最后，编辑  `系统变量` path，添加 值 `%JAVA_HOME%/bin`  值之间要用分号间隔,这一步的目的是在任何路径下都可以运行jdk自带的工具程序(java.exe,javac.exe等)

## 5 hello world

新建 `Hello.java`文件
```java
public class Hello{
    public static void main(String[] args){
        System.out.println("Hello World");
    }
}
```

cmd  进入文件所在路径
```bat
#编译java文件生成字节码文件
javac Hello.java
#运行java文件
java Hello
```
![cmd中运行hello world](https://wxpp.oss-cn-qingdao.aliyuncs.com/blogimages/helloworld/942777-20170719192527474-63733593.png)
