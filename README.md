git使用 https://www.runoob.com/git/git-tutorial.html

# git_useage
git 命令行使用方法


# Git 分支管理
## 创建分支命令：
git branch (branchname)
## 切换分支命令:
git checkout (branchname)
## 创建新分支并立即切换到该分支下：
git checkout -b (branchname) 
 
当你切换分支的时候，Git 会用该分支的最后提交的快照替换你的工作目录的内容， 所以多个分支不需要多个目录。

## 合并分支命令:
git merge 

## 示例：
$ mkdir gitdemo  
$ cd gitdemo/  
$ git init  
Initialized empty Git repository...  
$ touch README  
$ git add README  
$ git commit -m '第一次版本提交'  
[master (root-commit) 3b58100] 第一次版本提交  
 1 file changed, 0 insertions(+), 0 deletions(-)  
 create mode 100644 README  
 
## 列出分支
git branch

## 删除分支
git branch -d (branchname)

# Git 查看提交历史
git log - 查看历史提交记录。  
git blame <file> - 以列表形式查看指定文件的历史修改记录。  
 
# 远程仓库

# git与github  
 
### github创建远程仓库（创建了readme文件）

### 省略ssh相关过程
 
### 本地命令：
git init   
git add --all  
git commit -m 'init'
### 本地仓库与github仓库关联
git remote add origin git@github.com:BenYu2021/xxx.git  
 
### 把github远程仓库readme文件合并到本地，远程分支main  
git pull --rebase origin main  
### 提交到github  
git push -u origin main
 
 
# git commit、git push、git pull、 git fetch、git merge 的含义与区别

git commit：是将本地修改过的文件提交到本地库中；
git push：是将本地库中的最新信息发送给远程库；
git pull：是从远程获取最新版本到本地，并自动merge；
git fetch：是从远程获取最新版本到本地，不会自动merge；
git merge：是用于从指定的commit(s)合并到当前分支，用来合并两个分支；
 
# 回退到提交的版本
 
# pull错代码，恢复到pull之前 ---本地代码回退
 
先看到提交的代码的id,  
git reflog  
id是你要回退的代码的id  
git reset --hard [id]       
 
 # git删除已经add的文件
 
 当git add 某个文件到缓存区，还没有git commit 但是你不想这个文件了

就可以使用git rm命令，两种选择：

git rm --cached “文件路径”，不删除物理文件，仅将该文件从缓存中删除；
git rm --f “文件路径”，不仅将该文件从缓存中删除，还会将物理文件删除（不会回收到垃圾桶）。
git删除已经add的文件的两种方法：

用版本库内容清空暂存区，git reset HEAD （谨慎使用）

只把特定文件从暂存区删除，git rm --cached xxx
 
————————————————
版权声明：本文为CSDN博主「辣爷」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_35536883/article/details/95939294
 
 # ignore路径linux的写法
 忽略跟路径resources文件夹
/resources/
 不能写成./resources

 
#  Quick setup

 Quick setup — if you’ve done this kind of thing before

Get started by creating a new file or uploading an existing file. We recommend every repository include a README, LICENSE, and .gitignore.

…or create a new repository on the command line
echo "# algorithms" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:yumengmeng92/algorithms.git
git push -u origin main
…or push an existing repository from the command line
git remote add origin git@github.com:yumengmeng92/algorithms.git
git branch -M main
git push -u origin main
…or import code from another repository
You can initialize this repository with code from a Subversion, Mercurial, or TFS project.

