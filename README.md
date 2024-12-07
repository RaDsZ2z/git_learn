# # git远程连接github仓库的 quick start(mac为例)

[教程视频](https://www.bilibili.com/video/BV1HM411377j?vd_source=8924ad59b4f62224f165e16aa3d04f00&spm_id_from=333.788.videopod.sections&p=11)

## 1.创建SSH密钥 和git clone

终端

```shell
cd ~/.ssh
#协议为rsa 大小为4096
ssh-keygen -t rsa -b 4096
[密钥名称] #密钥名称 可缺省
[密钥密码] #密码密码 可却省
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

## 2.git push

## 
