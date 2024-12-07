# git远程连接github仓库的 quick start(mac为例)

[教程视频](https://www.bilibili.com/video/BV1HM411377j?vd_source=8924ad59b4f62224f165e16aa3d04f00&spm_id_from=333.788.videopod.sections&p=11)

## 1.创建SSH密钥 和git clone

终端

```shell
cd ~/.ssh
#协议为rsa 大小为4096
ssh-keygen -t rsa -b 4096
[密钥名称] #密钥名称 可缺省
[密钥密码] #密码密码 可却省（感觉没有必要）
```

假设为的密钥名称是`rads_mac`

现在应该出现了`rads_mac`和`rads_mac.pub`两个文件，分别是私钥和公钥

复制公钥文件添加到github中

还需要在密钥同目录下创建`config`文件，内容如下

```txt
# github
Host github.com
HostName github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/rads_mac
```

最后一行的rads_mac是我的密钥名称

再到某空目录下执行`git clone [SSH]`就可以拉取仓库了

## 2.提交文件

对于任何在本地创建的文件，需要先`git add [filename]`，这样在提交时该文件才会被包括在被提交文件中

对于`git clone`得到的文件则不需要使用`git add`

修改文件时，修改的是本地文件而非本地仓库的文件

需要使用`git commit -a -m "[commit message]"`来提交到本地仓库

`-a`意为所有文件，`-m`是提交的备注信息

然后使用`git push`就可以推送到远程仓库了

## 3.拉取文件

`git pull`

## 4.本地git配置

```shell
git config --global user.name "my name" #设置name
git config --global user.email "my email" #设置email
git config --global --list #查看git配置信息
```

