# 第六章 管道：连接命令
## 一个命令与另外一个命令连接：为你减负
PowerShell通过**管道（Pipeline）**把命令相互连接起来。管道通过传输一个命令，把其**作为另外一个Cmdlet的输入**使得第二个命令可以通过第一个的结果作为输入并联合起来运行。
## 输出结果到CSV或XML文件
### 输出结果到CSV
```
PS E:\> Get-Process | Export-Csv result.csv
```
![CSV文件](https://github.com/poetlife/LearnPowershell/blob/master/pics/6_2.jpg)
### 输出结果到XML
```
PS E:\> get-process | Export-Clixml 1.xml
```
### 对比文件
```
Compare-Object
```
## 管道传输到文件或打印机
## 转换成HTML
在PowerShell的世界里，动词“export”表示**你把数据提取，然后转换成为其他格式，最后将转换后的格式存到某些储存介质中**，而动词“ConvertTO”**仅仅是处理过程的一部分，它仅转换不保存**。
```
PS > Get-Service | ConvertTo-HTML | Out-File service.html 
```
