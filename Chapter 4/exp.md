# 第四章动手实验解答
> 不保证正确性！

1. 显示正在运行的进程列表。
```
Answer is:
PS > get-process
```
2. 显示最新的100个应用程序日志。
```
Answer is:
PS > get-eventlog -logname application -newest 100
```
3. 显示所有类型为“Cmdlet”的命令。
```
Answer is:
PS > get-command -commandtype cmdlet
```
4. 显示所有的别名。
```
Answer is:
PS > alias
```
5. 创建一个新的别名，使用该别名可以运行“D”获取目录列表
```
Answer is:
PS > new-alias -name D -value dir
```
6. 显示以字母M开头的服务名称。
```
Answer is:
PS > get-service -displayname M*
```
7. 显示所有的Windows防火墙规则。
```
Answer is:
PS > show-netfirewallrule
```
8. 显示所有Windows防火墙的入站规则。(__*remain unsolved!!*__)
```
Answer is:
PS > 
```
