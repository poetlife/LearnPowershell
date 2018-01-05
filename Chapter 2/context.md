# 第二章 初识PowerShell
## Choose Your Weapon!
在64-bit的电脑上，我们可以看到具有如下图所示的PowerShell工具：

![1.jpg](https://github.com/poetlife/LearnPowershell/blob/master/pics/2_1.jpg)

其中后面括号带有**x86**的表示64位系统上32位控制台，而其中后面带有**ISE**的表示这个是图形控制台。
### 控制台窗口
1. 不支持双字节字符集
2. 剪切板操作使用的是非标准键
3. PowerShell在输入的时候会提供少量的帮助信息

![2.png](https://github.com/poetlife/LearnPowershell/blob/master/pics/2_2.png)

### 集成脚本环境（ISE）
打开ISE：`PS ISE`，然后就可以打开ISE环境。
1. 支持双字节字符集
2. 提供常规的剪切板的操作

![3.jpg](https://github.com/poetlife/LearnPowershell/blob/master/pics/2_3.jpg)

## 重新认识代码输入
tab键可以补全很多参数，也可以遍历命令、目录等。

## 常见误区
1. 尽量使用64位的
2. 确保PowerShell具有管理员权限

## 如何查看当前的版本
```
PS > $PSVersionTable
Name                           Value
----                           -----
PSVersion                      5.0.10240.17146
WSManStackVersion              3.0
SerializationVersion           1.1.0.1
CLRVersion                     4.0.30319.42000
BuildVersion                   10.0.10011.16384
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
PSRemotingProtocolVersion      2.3
```
要求版本至少在3.0以上。
