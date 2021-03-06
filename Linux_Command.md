## **strings**

strings命令在对象文件或二进制文件中查找可打印的字符串。字符串是4个或更多可打印字符的任意序列，以换行符或空字符结束。 strings命令对识别随机对象文件很有用。

### [语法]

```
strings [ -a ] [ - ] [ -o ] [ -t Format ] [ -n Number ] [ -Number ] [ file ... ]
```
### [选项]
```
-a --all：扫描整个文件而不是只扫描目标文件初始化和装载段
-f –print-file-name：在显示字符串前先显示文件名
-n –bytes=[number]：找到并且输出所有NUL终止符序列
- ：设置显示的最少的字符数，默认是4个字符
-t --radix={o,d,x} ：输出字符的位置，基于八进制，十进制或者十六进制
-o ：类似--radix=o
-T --target= ：指定二进制文件格式
-e --encoding={s,S,b,l,B,L} ：选择字符大小和排列顺序:s = 7-bit, S = 8-bit, {b,l} = 16-bit, {B,L} = 32-bit
@ ：读取中选项
```
### [实例]
查找ls中包含libc的字符串，不区分大小写：
```
strings /bin/ls | grep -i libc
```

## **rpm**
rpm命令是RPM软件包的管理工具。rpm原本是Red Hat Linux发行版专门用来管理Linux各项套件的程序，由于它遵循GPL规则且功能强大方便，因而广受欢迎。逐渐受到其他发行版的采用。
### [语法]
```
rpm(选项)(参数)
```
### [选项]
```
-a：查询所有套件；
-b<完成阶段><套件档>+或-t <完成阶段><套件档>+：设置包装套件的完成阶段，并指定套件档的文件名称；
-c：只列出组态配置文件，本参数需配合"-l"参数使用；
-d：只列出文本文件，本参数需配合"-l"参数使用；
-e<套件档>或--erase<套件档>：删除指定的套件；
-f<文件>+：查询拥有指定文件的套件；
-h或--hash：套件安装时列出标记；
-i：显示套件的相关信息；
-i<套件档>或--install<套件档>：安装指定的套件档；
-l：显示套件的文件列表；
-p<套件档>+：查询指定的RPM套件档；
-q：使用询问模式，当遇到任何问题时，rpm指令会先询问用户；
-R：显示套件的关联性信息；
-s：显示文件状态，本参数需配合"-l"参数使用；
-U<套件档>或--upgrade<套件档>：升级指定的套件档；
-v：显示指令执行过程；
-vv：详细显示指令执行过程，便于排错。
```
### [实例]
查找linux中安装的软件，筛选出gcc
```
rpm -qa |grep gcc
```
