---
title: git+hexo命令
date: 2017-08-18 11:00:25
tags:
---

## hexo常用命令
```
hexo new"postName" #新建文章
hexo new page"pageName" #新建页面
hexo generate #生成静态页面至public目录
hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
hexo deploy #将.deploy目录部署到GitHub
hexo help # 查看帮助
hexo version #查看Hexo的版本
```

## git命令
在你用git之前,要先报家门,否则代码不能提交
```
$ git config --global user.name diba
$ git config --global user.email dba.li@163.com
```

创建版本库
```
$ cd E:/
$ mkdir test
$ git init
```

<!-- more -->

在test存放你的代码文件
```
git add index.php 把 index.php 提交到暂存区
git commit -m "新建index.php" 把 index.php 提交到版本库
git add . 提交所有变动
git status 查看需要提交的缓冲文件
git commit -m
```

用rm命令删除文件,并直接commit,提交到版本库
```
$ touch foo.php # 创建foo.php
$ git add foo.php
$ git commit -m " 练习删除"
$ ls
foo.php index.php
# 开始删除
$ git rm foo.php
rm 'foo.php'
$ git commit -m "删除foo.php"
[master e4dc37c] 删除foo.php
1 file changed, 0 insertions(+), 0 deletions(-)
delete mode 100644 foo.php
$ ls
index.php
```

把代码推到远程仓库
- 本地库添加远程库
```
$ git remote add origin https://git.oschina.net/lianshou/test.git
意思是:添加1个远程库,代号是origin,地址是 https://....test.git
```

- push 推代码
```
git push origin master 意思是,把本地的版本(默认是master),推到代号为
origin的远程库去. 这个过程会让你输入用户名/密码,即你注册时的账户密码.
```

- clone 复制远程库
```
$ cd F:/
$ git clone https://git.oschina.net/lianshou/test.git
$ cd test
$ ls
index.php
```

- pull 拉取最新代码
```
git pull origin master
```

其他git命令
```
git mv config.php ./inc/config.php 移动
git mv config.php config.inc.php 改名
git log 查看项目的日志
git log <file> 查看某文件的日志
git log . 查看本目录的日志
git log --pretty=oneline 让日志单行显示
git reflog 查看版本变化
git reset --hard HEAD^ 切换为 head 的前1版本
git reset --hard HEAD^^ 切换为 head 的前2版本
git reset --hard HEAD~100 切换为 head 的前100版本
git reset --hard 6207e59 利用版本号来切换
git reset --hard 6207 版本号不用写那么长,只要能保证不与其他版本号重复就行
```

查看分支
```
git branch
* master 说明只有master分支，且处于master分支
```

创建分支
```
git branch dev
```

切换分支
```
git checkout dev 切换到dev分支
git branch -b dev 创建并切换到dev分支
```

合并分支
```
git merge dev 在主分支下合并dev分支上的内容
```

删除分支
```
git branch -d dev
```

添加远程仓库
```
git remote add origin https://git.oschina.net/lianshou/test.git
git remote rename origin online 修改远程仓库名(代称)
```

> FROM 西岭老湿(http://www.xiling.me)

> 接下来 ，推荐 [十八哥农场](http://www.yanshiba.com/)

> 本章完结

>     谢谢支持
