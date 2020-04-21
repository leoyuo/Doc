## :g(global) 命令

```
:g/pattern/command

command : c -- confirm,d -- delete, m -- move,s -- substitude
```

## 匹配某一行，在匹配的行尾添加序号
```
:let i=0
:%g/pattern/s/$/\='added string'.i/ | let i=i+1

```

| 命令 | 解析 |
|:---- | :---- |
|%g	 |	在整个文件中匹配 (:help :g )|
| pattern | 匹配,可以是正则表达式 |
| s/$ | 替换行尾 (:help :s)|
|\=	 |	使用表达式的结果进行替换 (:help \= ) '='字符需要转义 |
| 'added string'.i | 字符串拼接 |
|printf	 |	按指定格式输出 (:help printf() )|
| \| | 命令拼接，同时运行两条命令 |
| let i=i+1 | 赋值操作，使i值自加 |
|g	 |	替换行内所有出现的匹配 (:help :s_flags)|
| \- | \- |
| printf("%x",i) | 将i格式化成十六进制数 | 


## 匹配某一行，在匹配的行尾添加序号，序号显示十六进制

```
:let i=0
:%g/pattern/s/$/\='0x'.printf("%x",i)/ | let i=i+1
```