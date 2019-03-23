---
title: Alibaba Java代码规约扫描插件安装与使用
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
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/install-add-repository.png?q-sign-algorithm=sha1&q-ak=AKID7ot2yUbeEdCA6SlwkwbRAiDFOzYhYPBF&q-sign-time=1553305742;1553307542&q-key-time=1553305742;1553307542&q-header-list=&q-url-param-list=&q-signature=fd095a11755df4317ae70bc75fb3a1f948edb408&x-cos-security-token=acdaf4916f98db7f060b4d71f4de0350026f548110001)
注意安装完成后可能弹Security Warning，点击【Install anyway】即可。
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/security-warning.png?q-sign-algorithm=sha1&q-ak=AKIDausbyi2gEKfVcSiOHzqnv6lyumEM65Lc&q-sign-time=1553305791;1553307591&q-key-time=1553305791;1553307591&q-header-list=&q-url-param-list=&q-signature=36bab4164644ec74a8e23894309473d3d8b776d9&x-cos-security-token=6f053d098365fa8f79d6f2f1390826179bb6d77610001)
安装完成后，会提示重启Eclipse, 插件会在下次启动后生效。
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/software-update-restart.png?q-sign-algorithm=sha1&q-ak=AKID0OjI2mRVonbTbF1flW8FcNVsdOGjWGdA&q-sign-time=1553305824;1553307624&q-key-time=1553305824;1553307624&q-header-list=&q-url-param-list=&q-signature=4a1d3337473ea909a595c2d47419cc8dff82c4a0&x-cos-security-token=44c63edd0d95943ac259c1d9067f771b5bffe12c10001)
## 使用
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/ecipse-use-p3c-plugin.png?q-sign-algorithm=sha1&q-ak=AKIDSbsjZuYUZ0LYXy170bjNkluo76TyaqVZ&q-sign-time=1553258572;1553260372&q-key-time=1553258572;1553260372&q-header-list=&q-url-param-list=&q-signature=d63e71a3b154d7bae573b8b72c0a7026e3616d45&x-cos-security-token=e5c267dac0c8221454b41f1f76f87b0ea359378910001)
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
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/alibaba-p3c-plugin-setup/idea-p3c-plugin-setup.png?q-sign-algorithm=sha1&q-ak=AKIDPCnejHqjxlMTLGUKd67fq9vosPZH3XIA&q-sign-time=1553305846;1553307646&q-key-time=1553305846;1553307646&q-header-list=&q-url-param-list=&q-signature=249d2730d3802d626a785dd496ee462fee8f9456&x-cos-security-token=f75db06d26a613baa9d79f30e8d7ad05166e581e10001)
重启IntelliJ IDEA使插件生效。
## 插件使用

## 参考
 - [github-alibaba/p3c](https://github.com/alibaba/p3c)
