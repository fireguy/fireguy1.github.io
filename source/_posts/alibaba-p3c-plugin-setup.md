---
title: alibaba-p3c-plugin-setup
date: 2019-02-21 22:12:41
tags:
  - eclipse
  - intelliJ idea
  - plugin
  - Alibaba
  - sonar
  - pmd
categries:
  - baisic
---

# Alibaba Java代码规约扫描插件
2017年10月14日杭州云栖大会，Java代码规约扫描插件全球首发仪式正式启动，规范正式以插件形式公开走向业界，引领Java语言的规范之路。

源码：[alibaba/p3c](https://github.com/alibaba/p3c)

相关文档或书籍：
- 中文版: *[阿里巴巴Java开发手册](https://github.com/alibaba/p3c/blob/master/%E9%98%BF%E9%87%8C%E5%B7%B4%E5%B7%B4Java%E5%BC%80%E5%8F%91%E6%89%8B%E5%86%8C%EF%BC%88%E8%AF%A6%E5%B0%BD%E7%89%88%EF%BC%89.pdf)*
- English Version: *[Alibaba Java Coding Guidelines](https://alibaba.github.io/Alibaba-Java-Coding-Guidelines)*
- 《阿里巴巴Java开发手册》书籍版天猫官方店: *[阿里巴巴Java开发手册最新版](https://detail.tmall.com/item.htm?spm=a1z2e.8325951.feedDetail.4.3315431gklIXe&id=562626792765&ns=1&abbucket=14)*
- 《码出高效》书籍版天猫官方店: *[码出高效：Java开发手册](https://detail.tmall.com/item.htm?spm=a230r.1.14.40.7dee7d6bwpO82U&id=575107529181&ns=1&abbucket=20)*

# 安装Eclipse插件
## 要求
 - Eclipse Juno+
 - maven3.+
 - JDK 1.7+

## 离线安装
- 离线插件：[点我获取](https://p3c.alibaba.com/plugin/eclipse/update/plugin.zip)
- 安装步骤：略

## 在线安装
启动Eclispe，依次选择菜单的Help >> Install New Software,进入Install对话框。如图所示，点击【Add...】，并在弹出的Add Repository对话框中分别输入Name和插件URL，点击【Add】。然后根据提示进行安装。
```
Name: alibaba-p3c #自定义
Location: https://p3c.alibaba.com/plugin/eclipse/update
```
![](http://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/install-add-repository.png)
注意安装完成后可能弹Security Warning，点击【Install anyway】即可。
![](http://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/security-warning.png)
安装完成后，会提示重启Eclipse, 插件会在下次启动后生效。
![](http://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/software-update-restart.png)
## 使用
![](http://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/ecipse-use-p3c-plugin.png)
# 安装IntelliJ IDEA插件
## 要求
  - Project JDK: 1.7+
  - Gradle: 3.0+（Require JDK1.8+ for gradle）

## 离线安装
- 离线插件：[点我前往下载](https://plugins.jetbrains.com/plugin/10046-alibaba-java-coding-guidelines)
- 安装步骤：略

## 在线安装
启动IntelliJ IDEA，依次选择Settings >> Plugins
通过关键字"alibaba"搜索plugin,找到'Alibaba Java Coding Guidelines' plugin 安装
![](http://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/idea-p3c-plugin-setup.png)
重启IntelliJ IDEA使插件生效。
## 插件使用

## 参考
 - [github-alibaba/p3c](https://github.com/alibaba/p3c)
