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
----
3. 创建GitHub账户
----
4. 设置SSH key
在Git Bash中运行下面的命令创建 SSH Key。
```
$ ssh-keygen -t rsa -C "your_email@example.com"
Generating public/private rsa key pair.
Enter file in which to save the key
(/Users/your_user_directory/.ssh/id_rsa): 按回车键
Enter passphrase (empty for no passphrase): 输入密码
Enter same passphrase again: 再次输入密码
```
输入密码后会出现以下结果。
```
Your identification has been saved in /Users/your_user_directory/.ssh/id_rsa.
Your public key has been saved in /Users/your_user_directory/.ssh/id_rsa.pub.
The key fingerprint is:
fingerprint值 your_email@example.com
The key's randomart image is:
+--[ RSA 2048]----+
|     .+   +      |
|       = o O .   |
略
```
id_rsa 文件是私有密钥， id_rsa.pub 是公开密钥。
----
5. 添加公开密钥
点击右上角的账户设定按钮（Account Settings），选择 ![SSH and GPG Keys](https://github.com/settings/keys) 菜单。点击New SSH Key，然后在![弹出的页面](https://github.com/settings/ssh/new)的Title 中输入适当的密钥名称。 Key 部分请粘贴 id_rsa.pub 文件里的内容（全文）。id_rsa.pub的内容可以用如下方法查看。
```
$ cat ~/.ssh/id_rsa.pub
ssh-rsa 公开密钥的内容 your_email@example.com
```
添加成功之后，创建账户时所用的邮箱会接到一封提示“公共密钥添加完成”的邮件。
----
6. 通信测试
请用下面的代码进行测试。
```
$ ssh -T git@github.com
The authenticity of host 'github.com (207.97.227.239)' can't be established.
RSA key fingerprint is fingerprint值 .
Are you sure you want to continue connecting (yes/no)? 输入yes
```
出现如下结果即为成功。
```
Hi lucienyong! You've successfully authenticated, but GitHub does not
provide shell access.
```
注意，测试时要在系统路径下。
----
7. 使用社区功能
既然说 GitHub 能够以人为焦点，那么在创建账户后不妨试试![Follow（关注）](https://github.com/trending/developers)别人。
