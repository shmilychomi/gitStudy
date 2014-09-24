## Git学习笔记

* 创建版本库  
	`
	git init
	`
* 把文件添加到版本库  
	`
	git add readme.txt  
	`
* 提交文件到仓库  
	` git commit -m "wrote a readme file`

#### 总结
* 初始化一个Git仓库,使用git init命令
* 添加文件到Git仓库,分两步:
    第一步,使用`git add`(可反复多次使用,添加多个文件)
    第二步,使用`git commit`,完成
	
***
	
* 查看之前的修改  
`
git diff readme.txt
`

### 总结
* 要随时掌握工作区的状态，使用git status命令。
* 如果git status告诉你有文件被修改过，用git diff可以查看修改内容。

***

### 版本回退  
查看历史记录  
`git log`

格式化输出信息  
`git log --pretty=oneline`  

退回到上一个版本  
`git rest --hard HEAD^`
(在Git中HEAD表示当前版本,也就是最新的提交,上一个版本是HEAD^ 上上个版本是HEAD^^)  

指定退回到某个版本  
`git rest --hard 3628164` 3628164为版本号

Git的版本回退速度非常快，因为Git在内部有个指向当前版本的HEAD指针，当你回退版本的时候，Git仅仅是把HEAD从指向“append GPL”：
![Alt text](./pic/0.jpg)  

改为指向“add distributed”：  

![Alt text](./pic/1.jpg)

显示每一次命令
`git reflog`  

### 总结
* HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。  
* 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
* 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

***

### 工作区和暂存区

####工作区（Working Directory）：就是你在电脑里能看到的目录，比如我的learngit文件夹就是一个工作区：
![Alt text](./pic/2.jpg)  
#### 版本库 （Repository）：工作区有一个隐藏目录“.git”，这个不算工作区，而是Git的版本库。

Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD。  

![Alt text](./pic/3.jpg)  

##### 前面讲了我们把文件往Git版本库里添加的时候，是分两步执行的：

##### 第一步是用“git add”把文件添加进去，实际上就是把文件修改添加到暂存区；

##### 第二步是用“git commit”提交更改，实际上就是把暂存区的所有内容提交到当前分支。

##### 因为我们创建Git版本库时，Git自动为我们创建了唯一一个master分支，所以，现在，commit就是往master分支上提交更改。

##### 你可以简单理解为，需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改。

`Git is a distributed version control system. `  
`Git is free software distributed under the GPL.`  
`Git has a mutable index called stage.`  

##### 然后，在工作区新增一个LICENSE文本文件（内容随便写）。
##### 先用git status查看一下状态：
* git status
* On branch master
* Changes not staged for commit:
* (use "git add <file>..." to update what will be committed> )
* (use "git checkout -- <file>..." to discard changes in > working directory)
*    modified:   readme.txt

* Untracked files:
* (use "git add <file>..." to include in what will be committed)

*    LICENSE
* no changes added to commit (use "git add" and/or "git commit -a")

#####  Git非常清楚地告诉我们，readme.txt被修改了，而LICENSE还从来没有被添加过，所以它的状态是Untracked。

##### 现在，使用两次命令git add，把readme.txt和LICENSE都添加后，用git status再查看一下：
 
 
*  git status
* On branch master
* Changes to be committed:
*   (use "git reset HEAD <file>..." to unstage)
 
*       new file:   LICENSE
*       modified:   readme.txt

##### 现在，暂存区的状态就变成这样了：
![Alt text](./pic/4.jpg)


### 总结
##### 暂存区是Git非常重要的概念，弄明白了暂存区，就弄明白了Git的很多操作到底干了什么。

***
### 管理修改
为什么Git比其他版本控制系统设计得优秀，因为Git跟踪并管理的是修改，而非文件。  

什么是修改？比如你新增了一行，这就是一个修改，删除了一行，也是一个修改，更改了某些字符，也是一个修改，删了一些又加了一些，也是一个修改，甚至创建一个新文件，也算一个修改。

##### Git管理的是修改，当你用“git add”命令后，在工作区的第一次修改被放入暂存区，准备提交，但是，在工作区的第二次修改并没有放入暂存区，所以，“git commit”只负责把暂存区的修改提交了，也就是第一次的修改被提交了，第二次的修改不会被提交。

### 总结
##### 理解了Git是如何跟踪修改的，每次修改，如果不add到暂存区，那就不会加入到commit中。

***
### 撤销修改
`git checkout -- readme.txt`

命令`git checkout -- readme.txt`的意思是,把readme.txt文件在工作区的修改全部撤销,这里有两种情况:一种是readme.txt修改后还没有被放到暂存区,现在撤销修改就回到和版本库一模一样的状态;一种是readme.txt已经添加到暂存区后,又作了修改,现在撤销修改就回到添加暂存区后的状态.总之,就是让这个文件回到最近一`git commit`或者`git add`时的状态.


#####`git checkout -- file`中`--`很重要,没有`--`就变成了创建一个新分支的命令.


以下文件

> $ cat readme.txt  
Git is a distributed version control system.  
Git is free software distributed under the GPL.  
Git has a mutable index called stage.  
Git tracks changes of files.  
My stupid boss still prefers SVN.  

> $ git add readme.txt    

使用`git status`查看,修改只是添加到了暂存区,还没有提交:  

> $ git status  
 On branch master  
 Changes to be committed:  
   (use "git reset HEAD <file>..." to unstage)  
       modified:   readme.txt  
no changes added to commit (use "git add" and/or "git commit -a")  

#####丢弃修改的工作区
> $ git checkout -- readme.txt

> $ git status
 On branch master
nothing to commit (working directory clean)

### 总结
##### 场景1:当改乱来某个工作区文件的内容,想丢弃工作区的修改时,用命令`git checkout -- file`
##### 场景2: 当不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。
##### 场景3:已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库.

***
### 删除文件
Git中,删除也是一个修改操作.添加一个新文件test.txt到Git并提交.

> $ git add test.txt  

> $ git commit -m "add test.txt"

> [master 94cdc44] add test.txt

> 1 file changed, 1 insertion(+)

> create mode 100644 test.txt

用rm命令删除.
`rm test.txt`

Git知道删除了文件.因此工作区和版本库就不一致礼.`git status`命令会显示哪些文件被删除.

> $ git status  
> *#* On branch master  
> *#* Changes not staged for commit:  
> *#*   (use "git add/rm <file>..." to update what will be   
> committed)  
> *#*   (use "git checkout -- <file>..." to discard changes > in working directory)  
> *#*  
> *#*       deleted:    test.txt  
> *#*  
> no changes added to commit (use "git add" and/or "git > commit -a")   

现在用两个选择.一个1确实从版本库中删除该文件,使用`git rm`删掉,并且`commit`

> *$* git rm test.txt  
> rm 'test.txt'  
> *$* git commit -m "remove test.txt"  
> [master d17efd8] remove test.txt  
> 1 file changed, 1 deletion(-)  
> delete mode 100644 test.txt  

另一种情况是删错了.因为版本库里还有.可以把误删除的文件恢复到最新版本.  

`git checkout -- test.txt`

### 总结
命令git rm用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失`最近一次提交后你修改的内容。`
