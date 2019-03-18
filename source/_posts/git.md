---
title: git
date: 2019-03-18 20:12:05
tags:
  - git
---

# Git
## Git介绍
  - Git是分布式版本控制系统
  - 集中式VS分布式
    - 集中式版本控制系统，版本库集中存放在中央服务器，必须要联网才能工作,没有历史版本库。
    - 分布式版本控制系统，版本控制系统没有“中央服务器”，每个人电脑上都是一个完整的版本库。
    - 分布式系统优势：安全性更高，不需要联网，如果中央服务器故障，任何其他一个开发人员的本地都有最新的带有历史记录的版本库。
  - 主要区别在于历史版本库的存放，集中式系统历史版本只存在于中央服务器，而分布式控制系统中每个本地库都有历史记录存放。
## Git安装
### Ubuntu
```
sudo apt-get install git
git --version
```
### git
- [Github-Git](https://github.com/git/git)
- [Git下载地址](https://git-scm.com/download)
![](/git/20190318081402340.png)
### git-GUI
[git-GUI Clients](https://git-scm.com/downloads/guis/)
![](/git/20190318083343938.png)

## 工作区、暂存区和版本库
- 工作区：git init指令执行的目录
- 版本库：工作区的隐藏目录.git
- 暂存区: 版本库的stage（或index）
![](/git/20190318100549699.png)

将文件往版本库里添加时是分两步执行的:
  - 第一步是用`git add`把文件添加进去，实际上就是把文件修改添加到暂存区。
  - 第二步是用`git commit`提交修改，实际上就是把暂存区的所有内容提交到当前分支。

Git是如何跟踪修改的，每次修改，如果不用git add到暂存区，那就不会加入到commit中。

## Git命令
### 基础命令
#### git配置
指令|说明
:--|:--
git config --global user.name "Your Name"|配置user.name
git config --global user.email "email@example.com"|配置user.nameuser.email
git config --global -l|查看配置列表
git init|在当前目录创建git仓库
git add <file>|添加文件到仓库
git commit -m <message>|提交
git status|查看工作区状态
git log [--pretty=oneline]|查看提交历史
git reset --hard HEAD^|HEAD指向的版本是当前版本，回到上一版本
git reset --hard HEAD^^|HEAD指向的版本是当前版本，回退上两个版本
git reset --hard HEAD~50|HEAD指向的版本是当前版本，回退上指定版本数
git reflog|查看提交命令历史，可查看提交版本号(commit id/SHA1)
git reset --hard <SHA1> | 回到未来指定版本<SHA1>
git checkout -- <file>|丢弃工作区的修改
git rm <file>| 删除文件，相当于先rm <file>再git add <file>
git diff|查看文件修改内容


>git config命令的--global参数，表明这台机器上的所有Git仓库都会使用这个配置，也可以对某个仓库指定不同的用户名和邮箱地址
>


### Git进阶

# 参考
- [Git-Manual](https://git-scm.com/doc) 
- [Git-book:《Pro Git v2》](https://git-scm.com/book/en/v2)
- [Git-video](https://git-scm.com/videos)
- [廖雪峰-Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
- [Git学习笔记](https://github.com/iuuan/learngit/blob/master/learning-note.md)


