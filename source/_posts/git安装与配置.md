---
title: Git安装与配置
date: 2018-03-16 14:30:51
tags: [git,github]
categories: git  
toc: true  
---

## 关于Git ##
Git是作为我们源代码管理、版本控制和团队开发时经常用的工具。

## Git是如何实现源代码管理的？ ##

 - 保存开发过程，它可以详细的保存我们每一次提交的内容以及修改内容。
 - 实验新特性而不破坏现有数据，产品需求在更新，我们需要开发新特性，为了不破环现有数据，我们可以使用git中的分制管理。
 - 多人合作开发，我们每个开发人员都可以从远程仓库下载最新版本，然后进行修改，提交，最终实现一个完整效果，高效的管理我们的项目。
 
## Git 的安装步骤： ##
 - 下载Git安装包 [官方下载地址][1]
 - 安装 [详细安装过程][2]
 - 安装完成之后，在开始菜单找到“Git Bash”，蹦出一个类似命令行窗口的东西，说明Git安装成功。

## Git安装完成之后进行如下配置 ##
- 在Git Bash 命令行窗口中输入命令创建你的账户（方便后续查看操作者）： 

> $ git config - -global user.name "yourname"

> $ git config - -global user.email "yourname@xx.com"

## 创建本地版本库 ##

 1. 在桌面创建一个文件夹： `myProject`;
 2. 打开终端输入命令`$ cd ....../myProject`; （进入该文件夹）
 或者打开文件夹，鼠标右键点击找到gitbash，打开gitbash；
 3.  `$ git init`; 将该文件夹变为 git 可管理的仓库。

## 创建github网上仓库 ##

 1. 在[GitHub网站][3]上注册一个账号，获取免费的git远程仓库。
 2. 登陆GitHub注册的账号。
 3. 配置SSH，便于本地git仓库和github仓库进行传输信息。
    SSH是计算机之间的加密通信协议。
    假设A 是中央服务器，B为客户端；
    当B想要访问中央服务器上的资源（加密资源），那     么中央服务器必须能够识别客户端

    ### 中央服务器如何识别客户端？ ###

    第一步：客户端首先生成公钥和私钥这两个秘钥对
    第二步：中央服务器需要添加客户端生成的公钥
    
    如何配置ssh：
    - 打开终端，（点击window左下角菜单，输入cmd回车或者直接在桌面右键打开gitbash） 
    - 输入命令：`$  ssh-keygen -t rsa -C email@xxx.com`
    - 一路回车，然后到用户主目录中查看SSH Key的秘钥对是否生成，即id_rsa 和 id_rsa.pub这两个文件
    - 打开[github官网][4]（已登录），点击右上角头像，下拉找到`Setting`点击打开
    - 在左边找到：`SSH and GPS keys`,点击打开，接着点击新建：`New SSH key`添加SSH key。
    - 接着填写任意的 title（可以不填写，默认为你的邮箱），在key的文本框中粘贴 id_rsa.pub 文件的内容。
    
    

 4. 添加远程仓库，点击 “+” 点击 `New repository`填写远程仓库的名称，描述性信息勾选Public选项。


## 简单运用git命令（将文件提交到github） ##

一 、在我们创建的myProject文件夹（也就是我们`git init`后的myProject文件夹）下随便创建一个文件。例如：index.html
打开终端控制：运行命令：`$ git remote add origin git@github.com:yourGitHubName/directory.git.`  关联本地仓库与远程仓库。

二 、克隆一个本地仓库，（上面第四步我们新建的仓库）
    打开该仓库，在右侧找到绿色按钮`Clone or dowenload`  复制输入框中的信息
    在你需要的位置右键点击gitbash或者cmd 进入到对应文件夹下，
    输入命令：`$ git remote add origin git@github.com:yourGitHubName/directory.git.`  关联本地仓库与远程仓库。

    
然后在该文件夹或者新克隆的文件夹下打开终端，再运行命令（'$' 符号可忽略）：

 1.  `$ git status`   查看git状态，看有没有要提交的文件
 2.  `$ git add 文件名`   将文件添加到git 暂存区。
 3.  `$ git commit -m “描述信息”`  将文件提交到 git 持久区。
 4.  `$ git diff`  查看修改的内容。
 5.  `$ git log`  输出日志 （git log –oneline ,显示日志简略信息）
 6.  `$ git checkout – file` 撤销工作区最后一次修改的代码
 7.  `$ git reset HEAD file` 撤销暂存区的修改，回退到工作区
 8.  `$ git reset –hard 版本号`  回退到仓库中的指定版本
 9.  `$ git push -u origin master,` 将本地仓库的所有内容推送到远程库


  [1]: http://msysgit.github.io/
  [2]: http://jingyan.baidu.com/article/a3a3f811d4cd308da2eb8ad1.html
  [3]: https://github.com/
  [4]: https://github.com/