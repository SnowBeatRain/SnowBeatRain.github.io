---
title: 常见的我容易忘记的git分支命令
date: 2018-05-18 20:35:46
tags: [git,分支]
---

## 创建分支 ##
  

 1. 本地分支
 >`git branch <name>`
 2. 推送远程
 >`git push origin <name>`   默认推送到远程自动创建一个test分支
 >`git push --set-upstream origin <name>` 将本地分支提交到远程
 3. 创建本地分支并切换
 >`git checkout -b <name>`
 4. 拉取远程分支
 >`git checkout -b test origin/test`  git checkout -b 本地分支名 origin/远程分支名
 >如果上面的失败则先运行一下  `git fetch`
## 查看分支 ##

 1. 查看本地分支
 >`git branch`
 2. 查看所有分支（包括远程）
 > `git branch -a`

## 切换分支 ##

>`git checkout <name>`


## 合并分支 ##

1. 合并分支到当前分支
>`git merge <name>`  然后进行git push -u origin master 提交代码

## 删除分支 ##

 1. 删除本地分支
 >`git branch -d <name>`
 2. 删除远程分支
 >`git push origin --delete <name>`

