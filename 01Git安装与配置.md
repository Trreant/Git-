## 版本控制系统
Git是很流行的一种版本控制系统。何为版本控制系统？版本控制系统是用来记录一个或者若干个文件内容变化，以便于将来查阅特定版本修订情况的系统。它能完整的记录整个文件目录变更的过程。其发展流程基本如下:  
<li>本地版本控制系统</li>
<li>集中式版本控制系统</li>
<li>分布式版本控制系统</li>


## Git起源
git的诞生与Linux内核开源项目有着密不可分的关系。早期的Linux开源社区使用BitKeeper来管理和维护代码，但在2005年开发BitKeeper的公司结束了与开源社区的合作，收回了Linux开源社区免费使用BitKeeper的权利。这就迫使Linux开源社区开发出自己的版本管理系统也就是Git来管理和维护代码。自2005年Git诞生到现在，Git已经成为一个成熟完善的版本管理系统。

## Git安装与配置
#### 下载安装
通常windows用户可以在[Git for Windows](https://git-scm.com/download/win)网站下载git软件。  
#### 配置用户信息
完成安装后需要进行配置。在**Git Bash**中使用如下命令来配置用户名和电子邮件地址
>git config --global user.name "username"  
>git config --global user.email "email@email.com"
#### 配置在线仓库
如果使用GitHub提供的在线仓库，需要先拥有一个*[GitHub](https://github.com)*账号。
之后在本地打开**Git Bash**,输入以下命令并按提示创建SSH Key
>ssh-keygen -t rsa -C "注册邮箱"   

之后从创建目录下(默认为/C/Users/用户名/.ssh/)下的id_rsa.pub文件中获取key的内容。登录GitHub并从右上角的Settings中打开SSH keys页面即可添加SSH key。
配置完成后可以输入
>ssh -T git@github.com

来测试ssh key配置是否成功。