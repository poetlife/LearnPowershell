# 第五章动手实验解答
> 本解答均经过测试，但不保证准确性

1. 在注册表中，定位到`HKEY_CURRENT_USER\software\microsoft\Windows\currentversion\explorer`。选中“Advanced”项，然后修改`DontPrettyPath`的值为0。
```
PS E:\> Set-Location -Path HKCU:
PS HKCU:\software\Microsoft\Windows\CurrentVersion\Explorer\> Set-ItemProperty -Path .\Advanced\ -
PSProperty dontprettypath -value 1
```

2. 创建空文件C:/Test.txt。
```
PS E:\> new-item -ItemType File -Name Test.txt


    目录: E:\


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       2018-01-07     15:40              0 Test.txt
```

3. 尝试用`Set-Item`去修改Test.txt的内容为TESTING，是否可行？是否报错？想想为啥报错。
```
PS E:\> set-item -Path .\Test.txt -Value TESTING

所在位置 行:1 字符: 1
+ set-item -Path .\Test.txt -Value TESTING
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotImplemented: (:) [Set-Item], PSNotSupportedException
    + FullyQualifiedErrorId : NotSupported,Microsoft.PowerShell.Commands.SetItemCommand
```
> 说明
    The Set-Item cmdlet changes the value of an item, such as a variable or registry key, to the
    value specified in the command.


不属于一个PSProvider。

4. `Get-ChildItem`的`-Filter`、`-Include`、`-Exclude`参数之间有什么不同？
