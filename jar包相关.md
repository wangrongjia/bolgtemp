# jar包相关

## 1 jar包是什么

JAR(Java ARchive 归档)，简单的理解就是写好的一些类（或者其他的资源文件），将它们打包（压缩），然后别人就可以引用你的东西了，而不需要你把源代码引入到自己的工程中，这样可以减少空间，也方便别人引用。既然是压缩，那么和常见的压缩合适rar,zip,7z比有什么区别呢？jar包里面会有一个MANIFEST.FM的清单文件，里边有关于压缩文件的一些描述。

## 2 cmd下使用jar命令打jar包

![jar -help](https://wxpp.oss-cn-qingdao.aliyuncs.com/blogimages/jar%E5%8C%85%E7%9B%B8%E5%85%B3%20_%20%E7%8E%8B%E5%B0%8F%E6%B3%A1%E6%B3%A1%20_%20%E5%8D%9A%E5%AE%A2%E5%9B%AD/942777-20170804132157428-5989956.png)

2.1 示例一:文件归档

现在已经有Hello.java和对应的类文件

![java文件](https://wxpp.oss-cn-qingdao.aliyuncs.com/blogimages/jar%E5%8C%85%E7%9B%B8%E5%85%B3%20_%20%E7%8E%8B%E5%B0%8F%E6%B3%A1%E6%B3%A1%20_%20%E5%8D%9A%E5%AE%A2%E5%9B%AD/942777-20170804132751569-196444147.png)

`Hello.java`
```java
public class Hello{
    public static void main(String[] args){
        System.out.println("Hello World!");
    }
}
```

运行
```bat
jar cvf hello.jar Hello.class
```

生成hello.jar文件
![hello.jar](_v_images/_hellojar_1540375120_6476.png)

![hello.jar-META-INF](_v_images/_hellojarme_1540375158_21539.png)

 文件夹中的MANIFEST.MF文件就是该jar包的清单信息，也就是这个清单信息是jar包必须有的，缺省时jar.exe会自己帮我们加上，看一下默认生成的清单文件

`MANIFEST.MF`
```mf
Mainfest-Version: 1.0
Created-By: 1.8.0_131 (Oracle Corporation)

```

在最后添加 (**Hello后面需要有空格或者回车**)
```mf
Main-class: Hello

```

运行 
```bat
java -jar hello.jar
```

### 2.2 示例二:文件夹中所有文件生成jar包

新建`Print.java`
```java
public class Print{
    public static void print(String s){
        System.out.println(s);
    }
} 
```

`Hello.java`
```java
public class Hello{
    public static void main(String[] args){
        Print.print("Hello World");
    }
}
```

编译：
```bat
javac Hello.java Print.java
```

清单文件
`MANIFEST.MF`
```MF
Manifest-Version: 1.0
Created-By: 1.8.0_131 (Oracle Corporation)
Main-Class: Hello
```

![文件夹和清单的相对路径](_v_images/_文件夹和清单的相对路_1540375675_11079.png)

运行：
```bat
jar cvfm classes.jar MANIFEST.MF -C jar/
```

生成jar包后测试：
```bat
java -jar classes.jar
# 输出：
# Hello World
```










