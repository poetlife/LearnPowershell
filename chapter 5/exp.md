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


不属于一个PSProvider。**并不是每种功能在每种储存中都能运行。**

4. `Get-ChildItem`的`-Filter`、`-Include`、`-Exclude`参数之间有什么不同？
>  -Exclude <String\[]>
        Specifies, as a string array, an item or items that this cmdlet excludes in the operation
        . The value of this parameter qualifies the Path parameter. Enter a path element or patte
        rn, such as \*.txt. Wildcards are permitted.
        
>  -Filter <String>
        Specifies a filter in the provider's format or language. The value of this parameter qual
        ifies the Path parameter. The syntax of the filter, including the use of wildcards, depen
        ds on the provider. Filters are more efficient than other parameters, because the provide
        r applies them when retrieving the objects, rather than having Windows PowerShell filter
        the objects after they are retrieved.
    
> -Include <String\[]>
        Specifies, as a string array, an item or items that this cmdlet includes in the operation
        . The value of this parameter qualifies the Path parameter. Enter a path element or patte
        rn, such as \*.txt. Wildcards are permitted.
        The Include parameter is effective only when the command includes the Recurse parameter o
        r the path leads to the contents of a directory, such as C:\\Windows\\*, where the wildcard
         character specifies the contents of the C:\\Windows directory.
