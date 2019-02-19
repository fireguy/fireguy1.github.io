---
title: 基于Hexo + Github Page搭建个人博客
date: 2019-02-20 00:54:04
tags:
  - hexo
  - hexoeditor
  - github
  - gitpages
  - hexo-next-theme
categories: 
  - basic
---
# 方案
    本文使用的是A方案。
  - A. Hexo + Github page
  - B. Jekyll + Github page
   
# Hexo使用技巧
## Hexo部署免输密码
使用如下配置，可以在进行hexo deploy或hexo d部署时免输密码，前提已成功配置SSH Key。
```
deploy:
  type: git
  repo: git@github.com:fireguy/fireguy.github.io.git
  branch: master
```
## 使用ＨexoEditor编辑器提高效率
HexoEditor使用请参考[Github/HexoEditor](https://github.com/zhuzhuyule/HexoEditor) 

# 参考
- [Hexo](https://hexo.io/)
- [Hexo theme:next](https://github.com/theme-next/hexo-theme-next)
    - [theme-next guide](http://theme-next.iissnan.com/)
