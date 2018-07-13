### 写在前面的话

最近做的项目用到了Oracle数据库，开始接触Oracle数据库要追溯到大二了，学了一个学期，上课呢，老师也是按照书上的，给我讲，从安装到用命令，再到用图形化视图工具。一个学期下来，发现除了在Windows上安装了几次Oracle和几个名词外，没有去真正使用过。要考试的最后那一周，安装考试题，学了一遍Oracle，收获还是蛮多的。

### 问题

以前用Oracle，会在product目录下找到驱动，那会儿还没有接触Maven。最近需要用到Oracle JDBC driver，在Maven仓库也有找到，但是不能下载，感到很奇怪，这是为什么啊？

 jar 包是可以下载的，也是可以用的

网上搜了一下

![Maven Oracle JDBC driver 不能下载](httpsupload-images.jianshu.ioupload_images5805596-8cd275453baa1eaf.pngimageMogr2auto-orientstrip%7CimageView22w1240)

原因大概是授权的问题。大都给出了解决方案，下面我们来操作一番。当然，如果你觉得添加jar也不错，那也是可以的。

### jar

我们首先要去找到jar包，并下载下来，你可以去Maven上找，也可以去Oracle官网找。

1.windows上安装Oracle后，在product目录下就能找到。

2.Maven仓库

![Maven 仓库 Oracle](httpsupload-images.jianshu.ioupload_images5805596-f95b7893cb3df380.pngimageMogr2auto-orientstrip%7CimageView22w1240)

![点击下载jar](httpsupload-images.jianshu.ioupload_images5805596-4913340d04883131.pngimageMogr2auto-orientstrip%7CimageView22w1240)

3.Oracle官网

网址：httpwww.oracle.comtechnetworkdatabaseapplication-developmentjdbcdownloadsindex.html

![Oracle 官网 JDBC driver](httpsupload-images.jianshu.ioupload_images5805596-253f0babd59f6407.pngimageMogr2auto-orientstrip%7CimageView22w1240)

### 安装到本地Maven仓库

我这里以第三种方式为例，安装到本地仓库

step 1去Oracle下载Oracle JDBC driver

![ojdbc 8](httpsupload-images.jianshu.ioupload_images5805596-0fec97d000ae2f4c.pngimageMogr2auto-orientstrip%7CimageView22w1240)

step 2 复制到我们自己的路径

step 3通过Maven安装

![mvn命令可用](httpsupload-images.jianshu.ioupload_images5805596-27e2a2c46e95bd1f.pngimageMogr2auto-orientstrip%7CimageView22w1240)

使用Maven的添加依赖（安装）命令：
mvn installinstall-file
-Dfile=EJavaideasshojdbc6.jar
-DgroupId=com.oracle
-DartifactId=ojdbc6
-Dversion=11.2.0.1.0
-Dpackaging=jar

演示：

![mvn install oralce](httpsupload-images.jianshu.ioupload_images5805596-2af681b7c50b5ac9.pngimageMogr2auto-orientstrip%7CimageView22w1240)

![本地仓库](httpsupload-images.jianshu.ioupload_images5805596-785f9c7a1402bb1f.pngimageMogr2auto-orientstrip%7CimageView22w1240)

### 测试

添加依赖

```xml
dependencies
    !-- 添加oracle驱动依赖 --
    dependency
        groupIdcom.oraclegroupId
        artifactIdojdbc8artifactId
        version12.2.0.1version
    dependency
dependencies
```

使用测试：

>暂无

### 资料

【1】[在Maven仓库中添加Oracle数据库的JDBC驱动依赖](httpsblog.csdn.neterlian1992articledetails74279106)