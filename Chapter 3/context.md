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
Example:
```
PS > help *log*
Show-EventLog                     Cmdlet    Microsoft.PowerShell.M... Displays the event logs ...
Write-EventLog                    Cmdlet    Microsoft.PowerShell.M... Writes an event to an ev...
Disable-AppBackgroundTaskDiagn... Cmdlet    AppBackgroundTask         Disable-AppBackgroundTas...
Enable-AppBackgroundTaskDiagno... Cmdlet    AppBackgroundTask         Enable-AppBackgroundTask...
Get-AppxLog                       Function  Appx                      ...
Export-BinaryMiLog                Cmdlet    CimCmdlets                Export-BinaryMiLog...
Import-BinaryMiLog                Cmdlet    CimCmdlets                Import-BinaryMiLog...
Get-MpThreatCatalog               Function  Defender                  ...
New-AutologgerConfig              Function  EventTracingManagement    ...
Get-AutologgerConfig              Function  EventTracingManagement    ...
Set-AutologgerConfig              Function  EventTracingManagement    ...
Start-AutologgerConfig            Function  EventTracingManagement    ...
Remove-AutologgerConfig           Function  EventTracingManagement    ...
Get-DtcLog                        Function  MsDtc                     ...
Reset-DtcLog                      Function  MsDtc                     ...
Set-DtcLog                        Function  MsDtc                     ...
Clear-PcsvDeviceLog               Function  PcsvDevice                ...
Get-PcsvDeviceLog                 Function  PcsvDevice                ...
Get-LogProperties                 Function  PSDiagnostics             ...
Set-LogProperties                 Function  PSDiagnostics             ...
Start-StorageDiagnosticLog        Function  Storage                   ...
Stop-StorageDiagnosticLog         Function  Storage                   ...
Get-WindowsUpdateLog              Function  WindowsUpdate             ...
```
从技术上来说，帮助系统并不知道shell中有哪些命令，**它实际上是寻找那些帮助主题**。
\*作为一个通配符，可以匹配0个或者多个字符。
## 详解帮助
### 参数集和通用参数
Example:
```
PS > help Get-EventLog
Syntax
    Get-EventLog [-LogName] <String> [[-InstanceId] <Int64[]>] [-After <DateTime>] [-AsBaseObject
    ] [-Before <DateTime>] [-ComputerName <String[]>] [-EntryType <String[]> {Error | Information
     | FailureAudit | SuccessAudit | Warning}] [-Index <Int32[]>] [-Message <String>] [-Newest <I
    nt32>] [-Source <String[]>] [-UserName <String[]>] [<CommonParameters>]

    Get-EventLog [-AsString] [-ComputerName <String[]>] [-List] [<CommonParameters>]
```
注意，这里这个命令提供了两个不同的参数集，且每个PowerShell的Cmdlet参数的结尾都有\[<CommonParameters>]，这个泛指每个Cmdlet命令都是使用的一组包含8个参数的集合。

### 可选和必选参数
```
  Get-EventLog [-LogName] <String> [[-InstanceId] <Int64[]>] [-After <DateTime>] [-AsBaseObject
    ] [-Before <DateTime>] [-ComputerName <String[]>] [-EntryType <String[]> {Error | Information
     | FailureAudit | SuccessAudit | Warning}] [-Index <Int32[]>] [-Message <String>] [-Newest <I
    nt32>] [-Source <String[]>] [-UserName <String[]>] [<CommonParameters>]
```
 其中，`[-LogName] <String>`为**必选参数**，其他的类似`[[-InstanceId] <Int64[]>]`的为**可选参数**。
### 位置参数
通常来说，参数是有位置性的，这意味着只要你把参数值放在正确的位置，你就可以只提供这个参数值，而不需要输入具体的参数名。
有两种方式确定位置参数：
1. 通过语法概要
2. 通过详细的帮助文档
### 参数值

### 发现命令实例

