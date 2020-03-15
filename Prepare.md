1. Git安装
- 换行符选择推荐的“Checkout Windows-style, commit Unix-style line endings”
- 其它默认
----
2. 初始设置
- 设置使用 Git 时的姓名和邮箱地址
```
$ git config --global user.name "Firstname Lastname"
$ git config --global user.email "your_email@example.com"
```
这个命令，会在“~/.gitconfig”中以如下形式输出设置文件。
```
[user]
name = Firstname Lastname
email = your_email@example.com
```
.gitconfig在系统默认路径下，通常为
```
C:\Users\administrator
```
- 提高命令输出的可读性
```
$ git config --global color.ui auto
```
“~/.gitconfig”中会增加下面一行。
```
[color]
ui = auto
```
