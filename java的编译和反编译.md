# java的编译和反编译

## 1 什么是编译

java的编译就是将.java文件编译成.class字节码文件，这种.class的类文件才是虚拟机能够识别的，我们已经知道java在不同的操作系统上有不同的虚拟机，java编译的字节码文件在所有操作系统上是一样的，只是不同的操作系统上的虚拟机能够将相同的字节码文件解释成当前操作系统可以识别的语言， 所以编译的作用是将程序员能够看懂的代码转化成jvm能够识别的二进制字节码文件。

### 1.1 如何编译

java文件的运行肯定要先经过编译生成.class文件然后才能执行，jdk中bin目录下的javac.exe就是windows系统下执行编译的文件。

## 2 java的反编译

反编译，那就是将.class文件转化成.java文件了。既然java是开源的语言，那么java的反编译就不是什么难题， jdk自己就提供了反编译工具，javap.exe，不是很好用， 但是可以通过它来看字节码文件被jvm解释执行的过程

### 2.1 javap.exe

依然是Hello.java,存放在桌面上名为java的文件夹中。

```java
public class Hello{
    public static void main(String[] args){
        System.out.println("Hello World!");
    }
}
```

 编译后的Hello.class也在文件夹中

![javap 反编译](_v_images/_javap反编译_1540374216_10975.png)

 看的出来，反编译的效果不是很好，只给出了方法声明，却没有方法体，这不是我们想要的效果，查看一下帮助

![javap -help](_v_images/_javaphelp_1540374267_4684.png)

加入-c试一下

![javap -c](_v_images/_javapc_1540374309_29608.png)

### 2.2 jad.exe

所以，被大家广泛使用的反编译工具是jad.exe   下载地址 ：链接：http://pan.baidu.com/s/1pL0VzQz 密码：si4i        一些成熟的反编译工具的核心都是jad。将jad.exe放到java安装目录下的bin目录中。

![jad](_v_images/_jad_1540374367_25048.png)

生成jad文件

![生成jad文件](_v_images/_生成jad文件_1540374415_5362.png)

查看jad文件

![查看jad文件](_v_images/_查看jad文件_1540374449_9561.png)

### 2.3 eclipse上的反编译插件

不引入源码包可以查看大概的源码

help-->eclipse marketplace 搜索 decompiler 

