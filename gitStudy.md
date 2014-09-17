## Git学习笔记

* 创建版本库
```
git init
```
* 把文件添加到版本库
```
git add readme.txt  
```
* 提交文件到仓库
```
git commit -m "wrote a readme file
```
#### 总结
* 初始化一个Git仓库,使用git init命令
* 添加文件到Git仓库,分两步:
    第一步,使用git add(可反复多次使用,添加多个文件)
    第二步,使用git commit,完成
	
	
* 查看之前的修改
```
git diff readme.txt
``` 	