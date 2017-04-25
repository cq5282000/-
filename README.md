# git-online-repository-settings

本片博客主要关于如何设置git远程仓库连接，以及设置远程仓库的提交权限，操作系统为mac os

## 创建SSH Key

首先在用户的主目录下寻找.ssh文件，.ssh文件默认是隐藏的，运行指令即可查看

```bash
# Linux & Mac
$ ls -a
```

如果还是没有.ssh文件，则运行一下指令，然后在.ssh 文件下运行该指令，密码不能为空

```bash
# Linux & Mac
$ ssh-keygen -t rsa -C "youremail@example.com"
```

![image](https://github.com/cq5282000/git-online-repository-settings/blob/master/images/ls-a.png)

然后进入.ssh文件

```bash
# Linux & Mac
$ cd .ssh 
```

查找id_rsa和id_rsa.pub两个文件，

![image](https://github.com/cq5282000/git-online-repository-settings/blob/master/images/id_rsa.png)

如果没有这两个文件的话，运行指令创建：

```bash
# Linux & Mac
$  ssh-keygen -t rsa -C "youremail@example.com"
```

## 登陆GitHub，设置SSH Keys

点击账号的settings

![image](https://github.com/cq5282000/git-online-repository-settings/blob/master/images/settings.png)

然后点击左侧栏里的ssh and gpg key,然后点击new ssh key,

![image](https://github.com/cq5282000/git-online-repository-settings/blob/master/images/ssh_key.png)

title里面的内容任意填写，在Key文本框里粘贴id_rsa.pub文件的内容，至此我们的电脑就可以向远程仓库提交代码了.

## git项目－脚手架的使用

第一步在项目的同级目录下，意思是把脚手架复制到自己的项目下面

```bash
# Linux & Mac
$  git clone git@xx.com:adp/react-starter.git ［自己的项目名称］
```

第二步是在项目里面，是修改远程分支的，因为上面复制下来的分支是react-starter的

```bash
# Linux & Mac
$ git remote set-url origin [项目的远程仓库的路径]
```
