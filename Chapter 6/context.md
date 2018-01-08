# 第六章 管道：连接命令
## 一个命令与另外一个命令连接：为你减负
PowerShell通过**管道（Pipeline）**把命令相互连接起来。管道通过传输一个命令，把其**作为另外一个Cmdlet的输入**使得第二个命令可以通过第一个的结果作为输入并联合起来运行。
## 输出结果到CSV或XML文件
### 输出结果到CSV
```
PS E:\> Get-Process | Export-Csv result.csv
```
![CSV文件](https://github.com/poetlife/LearnPowershell/blob/master/pics/6_2.jpg)
