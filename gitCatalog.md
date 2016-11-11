#git

##常用命令
```
git log   退出按q  回车
```

```
远程管理仓库
git remote 

```







##需解决的问题
###1.如何在本地，把别人的代码修改然后上传到自己的git上

*Test 1* ：**EPICSV4SB文件上传git**

直接上传是可以的，只需要把他的仓库地址改成我的就行。 
具体操作步骤

```
git init 
git add -A
git remot -v 查看当前的远程仓库地址如不是你当前的仓库名和地址，则删除
git remote rm origin  一般默认的是origin
git remote add origin + 你的仓库地址  //替换仓库地址
git push -u origin master

```


*Test 2*： **上传areaDetector**


会有问题，本身有@+版本号，貌似是绑定的。（不知是否有其他办法）

间接解决办法：：将主目录或者子目录中的.git文件直接删除。



```
cd $(dir)
find . -name ".git" | xargs rm -Rf //递归删除.git
git add -A
git remot -v 查看当前的远程仓库地址如不是你当前的仓库名和地址，则删除
git remote rm origin  一般默认的是origin
git remote add origin + 你的仓库地址  //替换仓库地址
git push -u origin master

