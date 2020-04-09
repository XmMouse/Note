# 命令
## 为何
1. 为何只有一个.git 安全 不需要为每个文件和远程库建立连接 传统的版本库和工作区是分开的必须要网络通信过渡依赖网络
2. git commit -a 提交一切更改删除可以跳过git add 但是不建议使用
## 如何执行
1. 从当前目录向上查找
## 是什么
暂存区是一个目录
## 其他
git grep
## 配置
1. 分别存在版本库，根目录， /etc
2. 写入配置
git config global/sysem user.name "xiaomeng"
git config global/sysem alias.co commit
git config global/sysem  color.ui true
3. 读取生效的配置
git config user.name
4. 删除
git config --unset --global user.name
4. 环境变量GIT_CONFIG 指定配置文件自定义的git用个这个
## git stash
把尚未提交的内容保存到零时区
git stash pop / apply
git stash list
git stash save  “”
## git clean
删除本地多余的目录
## 初始化
git clone
git init
## git diff
1. index - worker none
2. index - head HEAD
3. index-head --cached
## log
### git log 
1. git log --pretty=fuller
2. git log --pretty=oneline
2. git log --graph
## git status
1. git status
2. git status -s 带简要信息
## git checkout
默认作用在暂存区
本质： 操作的是HEAD
checkout可以建立一条新的开发线但是不能作为分支
head 可以到指向历史记录但是无法保存和提交随时🉑可能被清除
需要合并到其他分支去
三种用法
git checkout head -- path
git checkout branch
git checkout -b new branch
## git reset
默认作用在版本库
本质-影响的是分支游标如master
git reset Head -- filepath 覆盖暂存区
git reset --soft(只是移动游标)/hard（覆盖工作区和暂存区）/mixed（覆盖暂存区）
## ^
表示向上移动当有多个父提交的时候用^2的方式表示第几个父提交
1. ^  父提交
2. ^^ 父提交的父提交
3. ^3 第三个父提交
4. ~3 向上移动三个父提交 ～加数字表示有多少个^
## git rev-parse
git rev-parse作用一:  的作用是把引用换成hash
git rev-parse作用二： --git-dir --show-toplevel --show-prefix
## git rev-lsit 
## git show
1. 查看blob 显示内容
2. 查看tree 
3. 查看tag 提交内容
## 显示目录
    ls-tree(查看版本库目录)
    ls-file(查看暂存区目录)
    cat-file
## git blame
获取文件每一行的内容是在哪个版本添加的
前提-代码还在文件中
## git bisect（定位到坏版本）
解决代码bug代码不再文件中的时候
## 和工作区的关系
reset 不影响工作区覆盖index
reset --hard
checkout . file 使用index覆盖暂存区
checkout header . file 覆盖index和工作区未暂存和未提交均覆盖
## 高危操作
checkout

reset --hard
## git add
-u add 所有更改
## 版本库结构
1. branch->commit->tree->blob
## git branch
## git remote 
1. -v 显示远程详细信息
## git origin
1. 本身无含义
2. origin是一个不可变的本地分支（只能由fetch改变）
## git reflog
1. 本质就是查看.git/log下的文件
## git rm 
删除本地和暂存区
## git archive -o latest.zip/tar head
## 改变历史
1. git commit --amend（不会建立新的提交）
2. 单步悔棋文件更改
先检出正确的版本， 在-amend提交
git checkout file
git commit -amend
3. 多部悔棋（多个提交合并成一个）
git reset
git commit
## 改变时间线
git cherry-pick commit 把commit的补丁文件拿出来在当前head重新执行
## git rebase
git cherry-pick的升级命令
git rebase --noto newBase since still
git rebase -i
## git revert
反向提交-和svn完全不同
## 裸版本库
mirror
bare
一般而言代工作区的版本库不接受push（会导致版本库和暂存区工作区内容不一致）
## 远程分支
git ls-remote
git remote -v
## 临时文件保存
 和文件名无关同样的内容共享一个松散文件
## 查看文件占用磁盘大小
du
## 清理未引用文件
git fsck // 列出所有未关联松散对象
git prune // 清除所有为关联的松散对象
## 协同工作
### 冲突解决
1. 逻辑冲突-改名字后的引用冲突
2. 文件内容冲突
A 重命名了文件1
B 改了文件 可以执行成功
冲突文件放在暂存区
本地文件可见
所以解决冲突只用编辑本地文件然后add
3. 树冲突
对同一个文件同时改名字
