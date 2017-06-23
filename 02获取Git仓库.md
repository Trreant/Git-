# 获取Git仓库
获取Git仓库通常有两种方法：
<li>从服务器克隆一个现有的仓库</li>
<li>从本地创建一个Git仓库</li>


## 从服务器克隆一个Git仓库
在已有一个在线仓库地址的情况下，使用
>git clone [url]

命令即可以从服务器上克隆一个完整的Git仓库。它将包含这个Git仓库在服务器上的几乎所有数据。默认配置下Git仓库中每一个文件的每一个版本都将被克隆到本地仓库。如需重命名可以在该命令后面加上新的名字，即可为本地仓库取一个新的名字。

如果使用https的地址将会创建一个使用https方式提交的仓库，若需要重新建立ssh链接方式需先删除原来的提交方式：
>git remote rm origin  
>git remote add origin git@github.com:(用户名)/版本库名

## 从本地创建一个Git仓库 
在需要创建Git仓库的目录中打开GitBash，使用git init 命令即可创建一个本地仓库。如果需要将本地仓库与远程仓库关联起来，可以执行如下命令
>git remote add origin git@github.com:Trreant/Git-Study.git


首次进行上传操作时需要加 -u参数将本地的master分支和远程的master分支关联起来
>git push -u origin master


