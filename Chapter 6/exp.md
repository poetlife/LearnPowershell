# 第六章动手实验示例代码
> 不保证正确性！

1. 在控制台输入`Get-Service | Export-CSV services.csv | Out-File`会发生什么？为什么会那样？
```
所在位置 行:1 字符: 41
+ Get-Service | Export-CSV services.csv | Out-File
+                                         ~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Out-File]，PSArgumentNullException
    + FullyQualifiedErrorId : ArgumentNull,Microsoft.PowerShell.Commands.OutFileCommand
```
因为`Export-CSV`已经包括了导出文件至储存的功能。

2. 有什么方式能在不`get-service`的前提下停止一个服务？
传入`-name`参数

3. 如何创建一个竖线分隔符文件替代一个逗号分隔符文件？你可以依旧使用“Export-CSV”命令，但是应该使用什么参数？
`-delimiter`

4. 可以在已导出的CSV文件头部忽略#命令行吗？这一行通常包括了类型信息，但是如果你想从一个特定文件中获取并忽略的时要怎么做？
```
PS > get-process | export-csv -notypeinformation
```

5. 后面题目都太简单了，因此，不一一赘述。
