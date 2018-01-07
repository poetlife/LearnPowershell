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
