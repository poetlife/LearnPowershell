# 第三章 使用帮助系统
## 帮助系统：发现命令的方法
在碰到错误的时候，去想办法使用帮助系统是个更好的选择，而非是直接google或者bing。
## 可更新的帮助
PowerShell可以通过互联网进行下载更新、修正和拓展。
使用命令：`PS > update-help`即可更新帮助信息。

![1.jpg](https://github.com/poetlife/LearnPowershell/blob/master/pics/3_1.jpg)

如果当前计算机并没有接入互联网，那么可以通过某台连上互联网的计算机使用如下命令离线保存帮助文档：`PS > Save-Help`然后在未连接互联网的电脑上使用以下命令：`PS > update-help -SourcePath <path of saved file>`即可离线更新帮助文档。

## 查看帮助
1. `Get-Help`
2. `Help`等同于`Get-Help | more`，实际上是一个函数
3. `Man`等同于`Help`，实际上是`Help`的昵称，或者称作别名
4. 在Shell中，`Ctrl + C`组合键总表示**返回**的意思

## 使用帮助找命令
