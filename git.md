# Git

目前世界上最先进的分布式版本控制系统

http://git-scm.com/

zsh主题：zhann

## 安装

sudo apt install git

## 使用

### repository

初始化一个仓库

```
git init
```

提交操作

```
把文件添加到仓库
git add <file>
git add file2.txt file3.txt
强制添加已被忽视文件
git add -f <file>
把文件提交到仓库
git commit -m <message>
```

修改文件

```
查看仓库状态
git status

比较尚未缓存的改动，查看working tree与index的差别的。
git diff

确认之后再执行提交操作
git add <file>

查看已缓存j的改动，查看repository与index的差别的。
git diff --cached

查看已缓存的与未缓存的所有改动，查看working tree和repository的差别，HEAD代表的是最近的一次commit的信息
git diff HEAD

显示摘要而非整个 diff：git diff --stat

git commit -m <message>


```

忽视特殊文件

在Git工作区的根目录下创建一个特殊的`.gitignore`文件

https://github.com/github/gitignore

### 版本回退

```
显示版本信息
git log
git log --graph --pretty=oneline --abbrev-commit
-p 按补丁格式显示每个更新之间的差异。
--stat 显示每次更新的文件修改统计信息。
--shortstat 只显示 --stat 中最后的行数修改添加移除统计。
--name-only 仅在提交信息后显示已修改的文件清单。
--name-status 显示新增、修改、删除的文件清单。
--abbrev-commit 仅显示 SHA-1 的前几个字符，而非所有的 40 个字符。
--relative-date 使用较短的相对时间显示（比如，“2 weeks ago”）。
--graph 显示 ASCII 图形表示的分支合并历史。
--pretty 使用其他格式显示历史提交信息。可用的选项包括 oneline，short，full，fuller 和 format（后跟指定格式）。

回退
HEAD表示当前版本，HEAD^表示上一版本，HEAD^^表示上上版本
git reset --hard HEAD^

根据commit id反悔
git reset --hard <commit id>

查看回退记录
git reflog

区别
git reset   A->B->C => A->B
git revert  A->B->C => A->B->C->B
```

工作区与暂存区

工作区指当前git仓库的目录

执行git add 是指将当前目录下的文件添加到暂存区

git commit 是把暂存区的所有内容提交到当前分支



修改了内容，但还未执行add指令，可使用restroe退回

```
git restore <file>
```

删除文件后，git仓库中的不会被删除

如果要删除仓库中的，使用

```
git rm <file>
git commit -m "remove file"
```

如果是误删，需要恢复，使用

```
git restore <file>
```

## 远程管理

#### 403问题

Failed to connect to raw.githubusercontent.com port 443: Connection refused

[https://www.ipaddress.com](https://www.ipaddress.com/)查询raw.githubusercontent.com对应IP

```
sudo vim /etc/hosts
```

添加

ip.ip.ip.ip  raw.githubusercontent.com

#### 添加远程库

将本地的ssh公钥添加到github中

```
 git remote add origin git@github.com:Orangeooo/note.git
```

origin表示远程库的名字，git默认叫法

```
git push -u origin master
```

加上了`-u`参数，Git不但会把本地的`master`分支内容推送的远程新的`master`分支，还会把本地的`master`分支和远程的`master`分支关联起来

之后推送直接用

```
git push origin master
git push <远程主机名> <本地分支名>:<远程分支名>
如果本地分支名与远程分支名相同，则可以省略冒号：
git push <远程主机名> <本地分支名>
```

查看远程信息

```
git remote -v
```

解除本地和远程的绑定关系

```
git remote rm origin
```

#### 从远程库克隆

```
默认拉取master分支
git clone git@github.com:Orangeooo/note.git

如果想要dev分支，创建远程origin的dev分支到本地
git checkout -b dev origin/dev

如果远程分支已经有修改，先把最新的提交从origin/dev抓下来
git pull

设置dev和origin/dev的链接
git branch --set-upstream-to=origin/<branch> dev
git branch --set-upstream-to=origin/dev dev
```

## 分支管理

`HEAD`指向当前分支

创建分支

```
git branch <branchname>
git checkout -b dev
git checkout        -b参数表示创建并切换
新
git switch -c dev   -c参数表示创建并切换

```

切换分支

```
git checkout <branchname>
git switch master
```

查看分支

```
git branch
```

把`dev`分支的工作成果合并到当前`master`分支上

```
git merge dev
git merge <name>
```

`Fast-forward`表示快进模式，指的是直接将master指向dev

```
git merge --no-ff -m "merge with no-ff" dev
--no-ff参数，表示禁用Fast forward,会在merge时生成一个新的commit
```

删除分支

```
 git branch -d <name>
 
 删除尚未合并过的分支
 git branch -D <name>
```

如果两条分支都有新的提交，则无法快进模式合并，产生冲突

提示`Automatic merge failed;`

需要手动修改冲突文件

修改完成后重新add和commit

#### 临时保存

```
git stash
```

```
查看临时工作区
git stash list

恢复
git stash apply

删除
git stash drop

恢复并删除
git stash pop

多次stash后恢复指定的stash
git stash apply stash@{0}

复制一个特定的提交到当前分支
git cherry-pick <commitid>

把历史提交整理成一条直线
git rebase
```

## 标签

```
查看所有标签
git tag
查看标签信息
git show <tagname>

默认打在commit上
git tag <name>

打在历史提交上
git tag -a <tagname> -m <message> <commitid>

删除标签
git tag -d <tagname>
删除已推送的远程标签
git push origin :refs/tags/<tagname>

推送标签到远程
git push origin <tagname>
全部推送
git push origin --tags

查看删除远程tags执行效果
git ls-remote --tags origin
```

## SourceTree

git图形界面

https://www.sourcetreeapp.com/

