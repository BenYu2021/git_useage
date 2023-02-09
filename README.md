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

## git修改默认分支main
git config --global init.defaultBranch main
## 修改当前项目的分支为 main
git config --global init.defaultBranch main

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
git rm -r --cached “文件夹路径”  删除文件夹  
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

# git撤销已经push的提交

git log  
git reset --soft 倒数第二次提交版本id  
git push origin master --force  
重新提交  
 
 
 # 删除远程仓库
删除远程仓库你可以使用命令：

git remote rm [别名]

# .gitignore忽略规则简单说明

```
#               表示此为注释,将被Git忽略
*.a             表示忽略所有 .a 结尾的文件
!lib.a          表示但lib.a除外
/TODO           表示仅仅忽略项目根目录下的 TODO 文件，不包括 subdir/TODO
build/          表示忽略 build/目录下的所有文件，过滤整个build文件夹；
doc/*.txt       表示会忽略doc/notes.txt但不包括 doc/server/arch.txt
 
bin/:           表示忽略当前路径下的bin文件夹，该文件夹下的所有内容都会被忽略，不忽略 bin 文件
/bin:           表示忽略根目录下的bin文件
/*.c:           表示忽略cat.c，不忽略 build/cat.c
debug/*.obj:    表示忽略debug/io.obj，不忽略 debug/common/io.obj和tools/debug/io.obj
**/foo:         表示忽略/foo,a/foo,a/b/foo等
a/**/b:         表示忽略a/b, a/x/b,a/x/y/b等
!/bin/run.sh    表示不忽略bin目录下的run.sh文件
*.log:          表示忽略所有 .log 文件
config.php:     表示忽略当前路径的 config.php 文件
 
/mtk/           表示过滤整个文件夹
*.zip           表示过滤所有.zip文件
/mtk/do.c       表示过滤某个具体文件
 
被过滤掉的文件就不会出现在git仓库中（gitlab或github）了，当然本地库中还有，只是push的时候不会上传。
 
需要注意的是，gitignore还可以指定要将哪些文件添加到版本管理中，如下：
!*.zip
!/mtk/one.txt
 
唯一的区别就是规则开头多了一个感叹号，Git会将满足这类规则的文件添加到版本管理中。为什么要有两种规则呢？
想象一个场景：假如我们只需要管理/mtk/目录中的one.txt文件，这个目录中的其他文件都不需要管理，那么.gitignore规则应写为：：
/mtk/*
!/mtk/one.txt
 
假设我们只有过滤规则，而没有添加规则，那么我们就需要把/mtk/目录下除了one.txt以外的所有文件都写出来！
注意上面的/mtk/*不能写为/mtk/，否则父目录被前面的规则排除掉了，one.txt文件虽然加了!过滤规则，也不会生效！
 
----------------------------------------------------------------------------------
还有一些规则如下：
fd1/*
说明：忽略目录 fd1 下的全部内容；注意，不管是根目录下的 /fd1/ 目录，还是某个子目录 /child/fd1/ 目录，都会被忽略；
 
/fd1/*
说明：忽略根目录下的 /fd1/ 目录的全部内容；
 
/*
!.gitignore
!/fw/ 
/fw/*
!/fw/bin/
!/fw/sf/
说明：忽略全部内容，但是不忽略 .gitignore 文件、根目录下的 /fw/bin/ 和 /fw/sf/ 目录；注意要先对bin/的父目录使用!规则，使其不被排除。

```
 
# ubuntu升级git
    sudo apt update  # 更新源
    sudo apt install software-properties-common # 安装 PPA 需要的依赖
    sudo add-apt-repository ppa:git-core/ppa    # 向 PPA 中添加 git 的软件源
    sudo apt-get update
    sudo apt-get install git
