---
title: 个人博客的创建
date: 2018-03-09 15:42:53
categories: hexo,搭建博客
tags: [hexo,github,npm,基础]
toc: true
---
使用Hexo+Github创建个人博客：
    

> 基本技术

github，node，git
   
 - http://www.runoob.com/w3cnote/git-guide.html（github菜鸟教程）
 - http://www.runoob.com/nodejs/nodejs-install-setup.html（node菜鸟教程）
 - https://git-scm.com/ （git官网）




----------
## 具体创建步骤 ##
*该博客是在安装好git、node、配置过github的情况下*

 一. 创建一个github项目

 
 项目名固定格式为：yourname.github.io,并且勾选Initialize this repository with a README。Description：可不填写。如图：![此处输入图片的描述][1]
 由于我已经创建过，所以会有错误提示，请忽略
>1、打开已创建好的项目，点击右上角有一个settings，进入settings页面，下拉找到**GitHub Pages**，会发现一句：
>> Your site is published at http://snowbeatrain.github.io/


    
>2、直接点击该链接就可以直接访问您刚刚创建的项目所自动生成的博客网页（目前该博客内容为创建项目时的readme.md的内容 ）。后续查看个人博客就直接可以访问该地址：
>> yourname.github.io


>3、点击 下面的Choose a theme，可以更换主题，系统提供了几种简单的博客主题供你选择。（个人喜好不同，我没有使用这些，而是使用的从hexo上下载的主题）
    如果不喜欢可以自行百度搜索，在知乎上有几篇比较好的文章可以点看看一下。（文章下面我会提到主题的使用与更换）


----------


二. 安装hexo以便于快速、简洁且高效的博客框架参考文档:https://hexo.io/zh-cn/docs/
    
>1、全局安装hexo
>>打开CMD或者打开我们gitbash。输入命令：**npm install hexo -g**
安装完成之后输入hexo -v检查是否安装成功

>2、初始化一个blob文件夹用于存放博客
>>创建一个blog文件夹并打开使用鼠标右键点击并运行gitbash，输入命令：**hexo init** (网速过慢，耐心等待)
>>安装依赖项目：**npm install**


>3、运行hexo，本地电脑初始预览博客
>>输入命令：**hexo -g**
>>输入命令：**hexo s**  开启服务器，运行返回的地址：http://localhost:4000/,打开个人博客网页
>>如果访问后无法跳转，可能是可能是4000端口被占用，可以运行以下命令更换端口号：'**hexo server -p 端口号**'
    打开后可以看到以下页面，如图：
    ![此处输入图片的描述][2]

----------


三.将一和二两步联系起来，以便于访问**yourname.github.io**就可以查看到我们上图展示的页面

>1、打开我们刚刚创建的blog文件夹，找到该目录下的_config.yml文件
>>该文件为主配置文件，比如设置博客页展示的个人信息等，只需要在对应的位置填写信息就好。
    
>2、下拉到底，找到Deployment。修改为：
    >>deploy:
            >>>type: git
            >>>repo: git@github.com:yourname/yourname.github.io.git
            >>>branch: master

>然后就可以通过**yourname.github.io**访问了。
    
>3、本地新建一篇博客同步到网上
    >>1、输入命令：**hexo new post “博客名”**
    此时在blog文件夹下的source中的_posts目录中就会看该文件
    >>2、使用编辑器编辑好内容后，就可以输入命令**hexo d -g**生成部署博客了，但是在部署前需要安装一个扩展:**npm install hexo-deployer-git --save**
    >>3、部署成功后访问你的地址：http://yourname.github.io。 那么将看到生成的文章


  [1]: https://raw.githubusercontent.com/SnowBeatRain/blogImages/master/creatProject.png
  [2]: https://raw.githubusercontent.com/SnowBeatRain/blogImages/master/successLocalhost.png
  

----------
## 主题设置与切换 ##
（如果你认为hexo创建的博客默认主题还好不需要更换请忽略）
    这里提供我使用过的两种主题的简单配置
    
一.安装：
 1. 安装主题：
    >输入命令：**git clone https://github.com/iissnan/hexo-theme-next themes/next**

2.修改配置：
>在blog目录中，打开主配置文件_config.yml，找到并修改theme：next
>在blog目录中，打开themes文件下的next目录。找到_config.yml，进行该主题的具体配置

二.切换主题：
    在完成一的前提下如果我想更换主题
 1. 切换主题：
    >和安装一样，输入想安装的新主题,输入命令：**git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia**

2.修改配置：
>在blog目录中，打开主配置文件_config.yml，找到并修改theme：yilia
>在blog目录中，打开themes文件下的yilia目录。找到_config.yml，进行该主题的具体配置

3.运行：
>hexo clean   //清空之前主题
hexo g     //生成静态文件
hexo s     //在本地运行
hexo d    //发布到github的page上

参考文档

 使用Hexo+Github一步步搭建属于自己的博客（基础）
 http://www.cnblogs.com/fengxiongZz/p/7707219.html
 使用Hexo+Github一步步搭建属于自己的博客（进阶）
 http://www.cnblogs.com/fengxiongZz/p/7707568.html
 
 