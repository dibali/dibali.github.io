---
title: HEXO+Github,搭建属于自己的博客
date: 2017-08-17 20:39:27
tags:
---

## 准备工作
1. 安装[Node](https://nodejs.org)(必须)，用来生成静态页面,点击下载，然后一路next安装即可
2. 安装[git](https://git-scm.com/downloads)(必须)，把本地hexo内容提交到github上去

## 安装Hexo
1. git里执行安装命令`npm install -g hexo`，等待装完
2. git里切换到博客即将存放的目录，然后执行初始化命令`hexo init blog`

至此，安装工作已经完成，blog就是你的博客根目录，所有的操作都在里面进行

## 配置github
1. 建立Repository,Repository name规则：`github用户名.github.io`,例如：[dibali.github.io](https://dibali.github.io)
2. 现在的blog文件里应该有如下文件：

- node_modules
- public  
- source  
- db.json
- package.json
- scaffolds  
- themes
- `_config.yml`

3. vim `_config.yml`:
翻到最后，将代码改成下面的样子：

		deploy:
			type: git
			repo:
				github: https://github.com/dibali/dibali.github.io.git
				oschina: https://git.oschina.net/diba/diba.git
			branch: master

4. 执行命令`npm install hexo-deploy-git --save`
5. 执行配置命令`hexo deploy`,然后再浏览器中输入http://dibali.github.io

## 部署三部曲
每次部署，依次执行如下三个命令：

```
hexo clean
hexo generate
hexo deploy
```

> FROM  潘柏信(http://www.jianshu.com/p/465830080ea9)
