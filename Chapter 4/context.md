# 第四章 运行命令
## 无需脚本，仅仅是运行命令
PowerShell拥有能够访问整个.Net Framework底层的能力，我们也看到PowerShell“脚本”实际上与通过Visual Studio编写的C#语言使用模式也十分类似。
## 剖析一个命令
```
PS > Get-EventLog -LogName Security -ComputerName WIN8, server1 -Verbose
```
`-LogName`是参数名称，`Security`是参数值，`-verbose`是开关参数，且PowerShell不区分大小写。
## Cmdlet命名惯例
1. Cmdlet是一个原生的PowerShell命令行工具，整个术语仅仅存在和类似C#的.Net Framework语言中，其读音为“command-let”。
2. **函数和Cmdlet类似，但是不是以.Net编写，而是以PowerShell自己的脚本语言编写**。
3. **工作流**是嵌入PowerShell的工作流执行系统的一类特殊函数。
4. **应用程序**是任意类型的外部可执行程序，包括类似PING、Ipconfig等命令行工具。
5. 命令是一个通用的术语，适用于上述的术语。
### Cmdlet命名规则
1. 动词+“-”+名词是命名的管理
2. 可以使用`PS > get-verb`查看可用的动词，且一般来说，名词使用单数
```
Verb        Group
----        -----
Add         Common
Clear       Common
Close       Common
Copy        Common
Enter       Common
Exit        Common
Find        Common
Format      Common
Get         Common
Hide        Common
Join        Common
Lock        Common
Move        Common
New         Common
Open        Common
Optimize    Common
Pop         Common
Push        Common
Redo        Common
Remove      Common
Rename      Common
Reset       Common
Resize      Common
Search      Common
Select      Common
Set         Common
Show        Common
Skip        Common
Split       Common
Step        Common
Switch      Common
Undo        Common
Unlock      Common
Watch       Common
Backup      Data
Checkpoint  Data
Compare     Data
Compress    Data
Convert     Data
ConvertFrom Data
ConvertTo   Data
Dismount    Data
Edit        Data
Expand      Data
Export      Data
Group       Data
Import      Data
Initialize  Data
Limit       Data
Merge       Data
Mount       Data
Out         Data
Publish     Data
Restore     Data
Save        Data
Sync        Data
Unpublish   Data
Update      Data
Approve     Lifecycle
Assert      Lifecycle
Complete    Lifecycle
Confirm     Lifecycle
Deny        Lifecycle
Disable     Lifecycle
Enable      Lifecycle
Install     Lifecycle
Invoke      Lifecycle
Register    Lifecycle
Request     Lifecycle
Restart     Lifecycle
Resume      Lifecycle
Start       Lifecycle
Stop        Lifecycle
Submit      Lifecycle
Suspend     Lifecycle
Uninstall   Lifecycle
Unregister  Lifecycle
Wait        Lifecycle
Debug       Diagnostic
Measure     Diagnostic
Ping        Diagnostic
Repair      Diagnostic
Resolve     Diagnostic
Test        Diagnostic
Trace       Diagnostic
Connect     Communications
Disconnect  Communications
Read        Communications
Receive     Communications
Send        Communications
Write       Communications
Block       Security
Grant       Security
Protect     Security
Revoke      Security
Unblock     Security
Unprotect   Security
Use         Other
```
## 别名：命令的昵称
```
PS > help aliases
PS > New-alias
PS > Export-Alias
PS > Get-Alias
```
## 使用快捷方式
### 简化参数名称
只要输入足够多的字母，能使PowerShell识别参数就可以了，PowerShell并不强制输入完整的参数名称。
### 参数名称别名
```
PS > (get-command get-eventlog | select -expandproperty parameters).computername.aliases 
```
### 位置参数
## 小小作弊一下：`Show-Command`
`Show-Command Cmdlet`允许你指定你无法用对的命令名称，并以图形化的方式将命令的参数名称展示出来
## 对扩展命令的支持
当需要运行`cmd.exe`中的命令时，你想PowerShell直接运行，可以直接在命令之后加两个破折号。
```
PS > Python E:/flask/"network programming"/CourseInfo.py -u 220150**** -p ** -o E:/1.txt -t E:/result.xlsx --
```
