## Git文件状态
对Git而言，一个工作目录下的文件无非两种状态，**已跟踪(Tracked)**和**未跟踪(Untracked)**。已跟踪的文件是指被纳入了版本控制的文件，在上一次快照中有它们的记录。在工作一段时间后，这些文件可能处于**未修改(Unmodified)**，**已修改(Modified)** 或者**暂存(Staged)**状态。工作目录中除已跟踪文件外的所有文件都属于未跟踪文件。首次克隆某个仓库之后，工作目录中的所有文件都处于已跟踪、未修改的状态。当对某些文件进行编辑之后，由于它们与上次快照发生了变化，Git将它们标记为已修改状态。我们可以将这些文件放入暂存区，然后提交这些修改，这样它们将又回到未修改的状态。
![](https://git-scm.com/book/en/v2/images/lifecycle.png "Git的文件状态变化")
## 检查文件状态
查看当前目录下的文件状态使用 <code>git status</code>命令来查看文件状态。

	a1213@DESKTOP-8M2VEPS MINGW64 /e/Git/Git学习 (master)
	$ git status
	On branch master
	Your branch is up-to-date with 'origin/master'.
	Changes to be committed:
	  (use "git reset HEAD <file>..." to unstage)

          modified:   01Git安装与配置.md

	Changes not staged for commit:
	  (use "git add <file>..." to update what will be committed)
	  (use "git checkout -- <file>..." to discard changes in working directory)

          modified:   02获取Git仓库.md

	Untracked files:
	  (use "git add <file>..." to include in what will be committed)
	
	      03Git基本操作.md
	      init

如上所示，键入 <code>git status</code> 命令后可以看到工作目录下处于暂存状态,已修改状态和未跟踪状态的文件列表。<code>git status</code> 命令的输出是十分详细的，但有的时候我们并不需要这么繁琐的信息，只需要简单地了解文件状态。此时可以使用 <code>git status -s</code> 或者 <code>git status --short</code> 来查看文件状态。其输出如下
	
	a1213@DESKTOP-8M2VEPS MINGW64 /e/Git/Git学习 (master)
	$ git status -s
	M  01Git安装与配置.md
	 M 02获取Git仓库.md
	A 03Git基本操作.md
	?? init

偏左侧的“<code>M </code>”表示被修改已暂存，偏右侧的“<code> M</code>”表示被修改还未放入暂存区，未跟踪的文件前方用“<code>??</code>”标记。未修改(已提交)的文件则用“<code>A </code>”进行标记。
## 跟踪新文件
使用 <code>git add 文件名</code> 来跟踪一个文件。其后所跟的文件名可以用正则表达式表达。例如输入<code>git add *.md</code>即可跟踪当前目录所有以".md"结尾的文件。
