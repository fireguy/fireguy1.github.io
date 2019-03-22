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
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/git/20190318081402340.png?q-sign-algorithm=sha1&q-ak=AKIDWk4NETS4dp8YT5qLd7sAYcYVav8yJSYg&q-sign-time=1553258114;1553259914&q-key-time=1553258114;1553259914&q-header-list=&q-url-param-list=&q-signature=ddf940795789458c5b9069ed36395392d47104bb&x-cos-security-token=a4b65ea327a1281e87bab6f8b18d29104db9efde10001)
### git-GUI
[git-GUI Clients](https://git-scm.com/downloads/guis/)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/git/20190318083343938.png?q-sign-algorithm=sha1&q-ak=AKIDuBSNmTh00k9ju3SvFLdFgofSgFdONZx2&q-sign-time=1553258139;1553259939&q-key-time=1553258139;1553259939&q-header-list=&q-url-param-list=&q-signature=5d2efc5158c34d995f0cd20b9e9c59a9c5bd94ec&x-cos-security-token=0c8c321761aa1fb826005cec11fbae11a711fac410001)

## 工作区、暂存区和版本库
- 工作区：git init指令执行的目录
- 版本库：工作区的隐藏目录.git
- 暂存区: 版本库的stage（或index）
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/git/20190318100549699.png?q-sign-algorithm=sha1&q-ak=AKIDSLMyBooYQoiPrd5h4riUhEGb3fReZ59P&q-sign-time=1553258177;1553259977&q-key-time=1553258177;1553259977&q-header-list=&q-url-param-list=&q-signature=e92dd3b74abbdb287d040477e956e2b833fe8ce7&x-cos-security-token=4e8ad10f64d9d074dffa4deace106d001df18a5e10001)

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
git reset --hard HEAD^|HEAD指向的版本是当前版本，回到上一版本（前提是没有推送到远程库）
git reset --hard HEAD^^|HEAD指向的版本是当前版本，回退上两个版本（前提是没有推送到远程库）
git reset --hard HEAD~50|HEAD指向的版本是当前版本，回退上指定版本数（前提是没有推送到远程库）
git reflog|查看提交命令历史，可查看提交版本号(commit id/SHA1)
git reset --hard <SHA1> | 回到未来指定版本<SHA1>
git checkout -- <file>|丢弃工作区的修改,让这个文件回到最近一次git commit或git add时的状态
git reset HEAD <file> | 放弃暂存（内容不变）
git rm <file>| 删除文件，相当于先rm <file>再git add <file>
git diff|查看文件修改内容
git diff HEAD -- <file>|查看<file>与最新版本的差异

>git config命令的--global参数，表明这台机器上的所有Git仓库都会使用这个配置，也可以对某个仓库指定不同的用户名和邮箱地址
>
### Git进阶
指令|说明
:--|:--
ssh-keygen -t rsa -C "youremail@example.com"|创建SSH key,~/.ssh目录下生成id_rsa和id_rsa.pub两个文件，公钥配置到服务端
ssh-add ~/.ssh/id_rsa | 添加私秘钥，如果添加失败可以先执行命令$ eval \`ssh-agent\`, \`是～键上的那个符号，然后再次添加私秘钥
ssh -T git@github.com | 判断是否绑定成功
git remote add origin https://github.com/username/repositoryname.git | 关联远程仓库
git push -u origin master| 推送到远程仓库，-u 表示第一次推送master分支的所有内容，此后，每次本地提交后，只要有必要，就可以使用命令$ git push origin master推送最新修改。
git clone https://github.com/usern/repositoryname.git |从远程克隆 
git config --global alias.st status | 设置别名，以后st就表示status
git branch | 查看分支
git branch <name> | 创建分支
git checkout <name> | 切换分支
git checkout -b <name> | 创建+切换分支
git merge <name>| 合并分支到当前分支,当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。
git merge --no-ff -m "description" <branchname> | 通常进行分支合并时，git会使用Fast forward模式，删除分支后，分支信息会丢失，可以使用--on-ff参数，禁用Fast forward，需要时加上一个-m参数把commit描述写进去。这样进行合并后的历史有分支，能看出来曾经做过合并。
git branch -d <name> | 删除非当前分支
git branch -D <name> | 强行删除分支，丢弃一个没有被合并过的分支
git log --graph | 查看分支合并图




# 参考
- [Git-Manual](https://git-scm.com/doc) 
- [Git-book:《Pro Git v2》](https://git-scm.com/book/en/v2)
- [Git-video](https://git-scm.com/videos)
- [廖雪峰-Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
- [Git学习笔记](https://github.com/iuuan/learngit/blob/master/learning-note.md)


