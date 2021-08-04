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
