# 实验答案
> 自答，不保证正确性 -- author

1. pass
2. 哪一个Cmdlet命令能够把其他Cmdlet命令输出的内容转换到HTML？
```
Process to Answer This Question:
PS > Help *html*
名称
    ConvertTo-Html

摘要
    Converts Microsoft .NET Framework objects into HTML that can be displayed in a Web browser.


语法
    ConvertTo-Html [[-Property] <Object[]>] [[-Head] <String[]>] [[-Title] <String>] [[-Body] <String[]>]
     [-As <String> {Table | List}] [-CssUri <Uri>] [-InputObject <PSObject>] [-PostContent <String[]>] [-
    PreContent <String[]>] [<CommonParameters>]

    ConvertTo-Html [[-Property] <Object[]>] [-As <String> {Table | List}] [-Fragment] [-InputObject <PSOb
    ject>] [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]


说明
    The ConvertTo-Html cmdlet converts .NET Framework objects into HTML that can be displayed in a Web br
    owser. You can use this cmdlet to display the output of a command in a Web page.

    You can use the parameters of ConvertTo-Html to select object properties, to specify a table or list
    format, to specify the HTML page title, to add text before and after the object, and to return only t
    he table or list fragment, instead of a strict DTD page.

    When you submit multiple objects to ConvertTo-Html , Windows PowerShell creates the table (or list) b
    ased on the properties of the first object that you submit. If the remaining objects do not have one
    of the specified properties, the property value of that object is an empty cell. If the remaining obj
    ects have additional properties, those property values are not included in the file.


-- More  --
```
3. 哪一个Cmdlet命令可以重定向输出到一个文件或者打印机上？
```
Process to Answer This Question:
PS > help *print*
Out-Printer
```
4. 哪一个Cmdlet可以操作process？
```
Process to Answer This Question:
PS > help *process*
```
5. 哪一个Cmdlet命令可以向事务日志（log）写入数据？
```
Process to Answer This Question:
PS > help *write*log*
Write-EventLog
```
6. 你必须知道别名是Cmdlet命令的昵称。哪一个Cmdlet可以用于创建、修改或导入别名？
```
Process to Answer This Question:
PS > help *aliases*
PS > help *alias*
```
7. 怎么保证你在shell中输入都在一个脚本（transcript）中，怎么保存这个脚本到一个文本文件中？
```
Process to Answer This Question:
PS > Start-Transcript -Path E:/result.txt -noclobber
PS > dir
PS > Stop-Transcript
```
导出的文件如文件中的`result.txt`

8. 从安全事件（event）日志检索所有的条目可能需要很长的时间，你怎么只获取最近100条记录呢？
```
Process to Answer This Question:
PS > get-eventlog -logname application -newest 100
```
9. 是否有办法可以获取一个远程计算机上安装的服务（service）列表？
```
Process to Answer This Question:
PS > get-service -computername <>
```
10. 是否有办法看到一个远程计算机运行了什么进程？
```
Process to Answer This Question:
PS > get-process
```
11. 尝试查看`Out-File`这个Cmdlet命令的帮助文档，通过这个Cmdlet命令输出到文件每一行记录的默认宽度大小为多少个字符？是否有一个参数可以让你修改这个宽度？
```
answer:
 -Width <Int32>
        Specifies the number of characters in each line of output. Any additional characters are truncate
        d, not wrapped. If you omit this parameter, the width is determined by the characteristics of the
         host. The default for the Windows PowerShell console is 80 characters.

        是否必需?                    False
        位置?                        named
        默认值                None
        是否接受管道输入?            False
        是否接受通配符?              False
 ```
 12. 防止`Out-File`覆盖文件？
 ```
 answer:
 -noclobber
 ```
 13. 怎么查看在PowerShell中预先定义所有别名（aliases）的列表？
 ```
Process to Answer This Question:
PS > alias
```
14. 怎么使用别名和缩写的参数名称来写一条最短的命令，就能检索出一台名为server1计算机中正在运行的进程列表？
```
Process to Answer This Question:
PS > gps server1
```
15. 有多少个Cmdlet命令可以处理普通对象？（object）
```
Process to Answer This Question:
PS > man *object*
Name                              Category  Module                    Synopsis
----                              --------  ------                    --------
ForEach-Object                    Cmdlet    Microsoft.PowerShell.Core Performs an operation against ea...
Where-Object                      Cmdlet    Microsoft.PowerShell.Core Selects objects from a collectio...
Compare-Object                    Cmdlet    Microsoft.PowerShell.U... Compares two sets of objects.
Group-Object                      Cmdlet    Microsoft.PowerShell.U... Groups objects that contain the ...
Measure-Object                    Cmdlet    Microsoft.PowerShell.U... Calculates the numeric propertie...
New-Object                        Cmdlet    Microsoft.PowerShell.U... Creates an instance of a Microso...
Register-ObjectEvent              Cmdlet    Microsoft.PowerShell.U... Subscribes to the events that ar...
Select-Object                     Cmdlet    Microsoft.PowerShell.U... Selects objects or object proper...
Sort-Object                       Cmdlet    Microsoft.PowerShell.U... Sorts objects by property values.
Tee-Object                        Cmdlet    Microsoft.PowerShell.U... Saves command output in a file o...
Get-WmiObject                     Cmdlet    Microsoft.PowerShell.M... Gets instances of WMI classes or...
Remove-WmiObject                  Cmdlet    Microsoft.PowerShell.M... Deletes an instance of an existi...
```
因此，12个命令。
16. 这一章中简单的提到了数组（array）。什么帮助主题可以告诉你关于它们的更多信息？
```
Process to Answer This Question:
PS > about_Arrays
```
