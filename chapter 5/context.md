# 第五章 什么是提供程序
> 请谨记，PowerShell并不是Cmd.exe。你可能觉得某些东西看起来差不多，但是我们确信它们大有不同。

## 什么是提供程序
一个PowerShell的提供程序，或者说PSProvider，其本质上是一个[适配器](https://baike.baidu.com/item/%E9%80%82%E9%85%8D%E5%99%A8)。他可以访问某些数据储存介质，并使得这些介质看起来像是磁盘驱动器一样。
## FileSystem的结构
Windows文件系统主要由**3种对象组成**：
+ 磁盘驱动器：最上层的对象，包含文件夹和文件。
+ 文件夹： 容器对象，可以包含文件夹和文件。
+ 文件： 最小单位的对象。
![Windows资源管理器](https://github.com/poetlife/LearnPowershell/blob/master/pics/5_1.jpg)
PowerShell中的术语和文件系统略有**不同**。因为PSDrive可能不是指向某个文件系统——比如PSDrive可以映射到注册表，所PowerShell不使用“文件夹/文件”的说法，而采用更通俗的说法“Item”。每个项都会存在对应的属性。比如，一个文件项可能有最后写入的时间，是否只读等属性。
## 文件系统——其他数据存储的模板
其他形式的数据源存储衍生于文件系统，所以严格算起来，文件系统可以算作其他数据存储的模板。
![Windows注册表结构](https://github.com/poetlife/LearnPowershell/blob/master/pics/5_2.jpg)
## 使用文件系统
在使用提供程序的时候，需要熟悉的另外一个Cmdlet是`Set-Location`。该参数的功能是将Shell中当前路径变更为不同路径。
```
PS E:\> Set-Location -Path D:/
PS D:\>
PS D:\> cd E:/
PS E:\>
```
创建一个新的项：
```
PS E:\> new-item testfolder


    目录: E:\


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       2018-01-07     15:10              0 testfolder
```
你必须要告诉Cmdlet你希望创建的类型是什么。要不然就会产生下面的后果：

![后果](https://github.com/poetlife/LearnPowershell/blob/master/pics/5_3.jpg)

所以，若我们需要创建一个新的文件夹：
```
PS E:\> new-item -ItemType Directory testfolder


    目录: E:\


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----       2018-01-07     15:13                testfolder
```
执行显示结果如下：

![后果2](https://github.com/poetlife/LearnPowershell/blob/master/pics/5_4.jpg)

## 使用通配符以及绝对路径
大部分项的Cmdlet都包含了`-path`属性。默认情况下，该属性**支持通配符**输入。
其中，**“\*”通配符表示0个或多个字符，“？”通配符仅代表单个字符**。
PowerShell为了显示不使用通配符，给出了一个新的参数`-LiteralPath`。该参数不支持任何通配符。
