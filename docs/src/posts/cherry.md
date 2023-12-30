---
icon: edit
date: 2023-8-30
category:
  - Cherry
tag:
  - red
  - small
  - round
---


# 嵌入式笔记总结

## static的三种用法

1、static：修饰局部变量的时候。局部变量出了作用域不销毁，本质上，static修饰局部变量的时候，改变了变量的存储位置的。影响了变量的生命周期，生命周期变长，和程序的生命周期一样，保存上一的值。  
2、static：修饰全局变量的时候，这个全局变量的外部连接属性就变成内部链接属性。其他源文件（.c）就不能在使用这个全局变量了。  
3、static：修饰函数->一个函数本来就具有外部链接属性的，但是被static修饰的时候，外部链接属性就变成了内部链接属性，其他源文件（.c）就无法使用了。

### git 工具版本控制
//全局初始化  
git config  --global user.name "liyan"  
git config --global user.email "2360216442@qq.com"   
git config --list  
//初始化  
git init  
//查看状态  
git status  
//添加文件到缓存区  
git add 文件名   
git add .  //解析.gitignore文件内容  
git add *  //不解析.gitignore文件内容  
//提交  
git commit -m "注释"   //单引号和双引号有区别，单引号会作为注释内容  
//查看日志  
git log  
git log --pretty=oneline //单行显示日志  
//查看当前修改的内容  
git diff 文件名  
//版本回退(回滚)  
//在windows的cmd控制台下操作git，想要回滚到上一次提交，  
//但是输入git reset --hard HEAD^后就显示more?，  
//多按几次回车后就报错如下，如何解决呢？   
//这是因为cmd控制台中换行符默认是^，而不是\ ，所以它的more？  
//的意思是问你下一行是否需要再输入，而^ 符号就被当做换行符而被git命令忽略掉了  
解决方法有如下几种：  
加引号：git reset --hard "HEAD^"  
加一个^：git reset --hard HEAD^^  
换成~：git reset --hard HEAD~ 或者 git reset --hard HEAD~1
~ 后面的数字表示回退几次提交，默认是一次    
git reflog  
git reset --hard fea3a8a  
//修改和删除  
//还没有提交到缓存  
git checkout 1.txt  
//对于已经提交的缓存区  
git rm -rf 1.txt  
git commit -m "xxx"  
//创建分支  
git branch debug  
//查看分支  
git branch  
//切换分支  
git checkout master  
//创建分支并且切换  
git checkout -b test  
//合并分支(先要切换到目标分支)  
git merge test  

//远程仓库github  
//获取已存在的项目  
git clone https://github.com/shenshelin/test.git  
//制作整数  
C:\Program Files\Git\usr\bin\ssh-keygen -t rsa -C '你的邮箱名'  
//生成的文件在C:\Users\你的用户名\.ssh 目录下  
//初次上传需要绑定  
git remote add origin https://github.com/shenshelin/2105_test.git  
//上传分支  
git push -u origin main  
//查看更新  
git remote show origin  
//获取更新  
git pull//git pull <远程主机名> <远程分支名>:<本地分支名>  
git fetch <远程主机名> //这个命令将某个远程主机的更新全部取回本地  
//如果只想取回特定分支的更新，可以指定分支名：  
git fetch <远程主机名> <分支名> //注意之间有空格  
git fetch origin master //从远程主机的master分支拉取最新内容   
git merge FETCH_HEAD    //将拉取下来的最新内容合并到当前所在的分支中  

1、git add .  
2、git commit -am 'xxx'。    
3、git checkout  切换分支。    
4、git merge   合并分支  
5、git push   保存并提交到远程。
