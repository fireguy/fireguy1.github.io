---
title: 在Ubuntu 18.04上安装jenkins
date: 2019-03-13 21:27:25
tags: 
  - jenkins
---

# jenkins
## ubuntu 
```
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ >/etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get install jenkins
```

![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/1.png?q-sign-algorithm=sha1&q-ak=AKIDh1ONHzNVtBBmZJakuflEh60s8Ul2F38a&q-sign-time=1553306835;1553308635&q-key-time=1553306835;1553308635&q-header-list=&q-url-param-list=&q-signature=6cbad198cbe964c4b58587bb10817bba75638231&x-cos-security-token=e6d60f2b18b715a6132c3ee0d3090ffb6154ce4a10001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/2.png?q-sign-algorithm=sha1&q-ak=AKID1YV7VFQn1Br6zcnPClyalJ61XtuAfOpt&q-sign-time=1553306924;1553308724&q-key-time=1553306924;1553308724&q-header-list=&q-url-param-list=&q-signature=8f802c17f6bc8476efaac4af55aabe1872768573&x-cos-security-token=4be5d5c912ceeeb9ebc9a9f9ce2f79ad62afe57810001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/3.png?q-sign-algorithm=sha1&q-ak=AKIDqcTt7pCopfkc00Gg2PJnb22xRRqm2D2x&q-sign-time=1553306948;1553308748&q-key-time=1553306948;1553308748&q-header-list=&q-url-param-list=&q-signature=856aba9bfdf1b79151a7066c0f4c56c7a5f27861&x-cos-security-token=0078377c7bdea41a4a01e8a41dc5a493b3ec30c210001)

## 问题1
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/4.png?q-sign-algorithm=sha1&q-ak=AKIDdZ7RvG1JgrKPelyP7Rq62MyZaBbtBwxX&q-sign-time=1553306974;1553308774&q-key-time=1553306974;1553308774&q-header-list=&q-url-param-list=&q-signature=bb41b1ef37bdc994d5fbc5d97f1521a04412a87d&x-cos-security-token=9474a8119bbae86fe2c22f73f84d0f8bc728655e10001)
### 解决办法
将type -p java的输出内容替换/etc/init.d/jenkins文件中的'type -p java'，重新加载，重启jenkins，验证http://localhost:8080
```
sudo gedit /etc/init.d/jenkins
systemctl daemon-reload
sudo service jenkins start
systemctl status jenkins.service
```
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/5.png?q-sign-algorithm=sha1&q-ak=AKIDScD5IgjLxFy7g2pTjhIn8544HTK1YK1w&q-sign-time=1553306998;1553308798&q-key-time=1553306998;1553308798&q-header-list=&q-url-param-list=&q-signature=4d7ed23b02b06eb5832fe1b2771b216412a575a3&x-cos-security-token=cf6443ce547ee80b8431e93e5b3a62df2b81ccde10001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/6.png?q-sign-algorithm=sha1&q-ak=AKIDSV88fkRZVwi7KJEqr3dOnEFmKSl02hJ7&q-sign-time=1553307016;1553308816&q-key-time=1553307016;1553308816&q-header-list=&q-url-param-list=&q-signature=3c7ddb478c38b14ef3858efb81bee1c242245cb3&x-cos-security-token=ea2ae71a52fe1f15a87cbe03a261f75e768184a210001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/7.png?q-sign-algorithm=sha1&q-ak=AKIDwbmi5t0QdxDlh6UmTM3gXgHWKiT13dY8&q-sign-time=1553307032;1553308832&q-key-time=1553307032;1553308832&q-header-list=&q-url-param-list=&q-signature=125248012158aca4a562e083f385d44124031ac9&x-cos-security-token=cfd2985015a6ecebd6a4c0d2d5a5101721483d3510001)

## 问题2
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/8.png?q-sign-algorithm=sha1&q-ak=AKIDPyuGujRHeJS9YVjEI2pc4KVEDBpN9uGo&q-sign-time=1553316429;1553318229&q-key-time=1553316429;1553318229&q-header-list=&q-url-param-list=&q-signature=097bc09a211aba5ce7cf3b0df49ccaf96c189a2d&x-cos-security-token=161268e244b930e76d151caf1dc19d78ca2780b010001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/9.png?q-sign-algorithm=sha1&q-ak=AKIDftEkfv2VI38PuQ67eaKrK1w5DpRxzRxX&q-sign-time=1553316451;1553318251&q-key-time=1553316451;1553318251&q-header-list=&q-url-param-list=&q-signature=36536c6c088d75e327e3410070ed4f810089c69f&x-cos-security-token=d39b67e6e37fe3417ba724efa1068e9cd28e9d7910001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/10.png?q-sign-algorithm=sha1&q-ak=AKIDQfaP4sm1iNSxm2Zj7zq2gbYT1d9vaTN5&q-sign-time=1553306881;1553308681&q-key-time=1553306881;1553308681&q-header-list=&q-url-param-list=&q-signature=0f47f46a65c94e16970d0130cf08a0e0a1a574cf&x-cos-security-token=a1519009033a59f6c659f3e1022fbfac5847ea5510001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/11.png?q-sign-algorithm=sha1&q-ak=AKIDHBFa2lwSIIRr4wGP56zoOdItuEQfk7BO&q-sign-time=1553316470;1553318270&q-key-time=1553316470;1553318270&q-header-list=&q-url-param-list=&q-signature=4c98049d039ce48062c031443ce99e804fb551d5&x-cos-security-token=cd6274e265dc1d89700fa5135200acd0c2d3248110001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/12.png?q-sign-algorithm=sha1&q-ak=AKIDMPfGJgs10qb7TRubMyWNf1N2dPqgyO44&q-sign-time=1553316485;1553318285&q-key-time=1553316485;1553318285&q-header-list=&q-url-param-list=&q-signature=d86833bcae18d9e8c4b3952a172e3e867518dc23&x-cos-security-token=0c4f8e90a055ff30a8cc98bc2b6ddb0ae2a67f3e10001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/13.png?q-sign-algorithm=sha1&q-ak=AKIDruOHqp46o5Ga8DIIEXzTHwfizPlFNBiG&q-sign-time=1553316500;1553318300&q-key-time=1553316500;1553318300&q-header-list=&q-url-param-list=&q-signature=4f2651b24980e0675002035a47c49c71bf1da804&x-cos-security-token=9cd7d436b4439986d2723f00bf352aceff03437010001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/14.png?q-sign-algorithm=sha1&q-ak=AKIDZWBGnhigVX0YyakJpEHEldhBI8QvQQn5&q-sign-time=1553316516;1553318316&q-key-time=1553316516;1553318316&q-header-list=&q-url-param-list=&q-signature=72f9054bb396bb23380d7a4f41f9ce8c25ffa6bc&x-cos-security-token=8985efed126451f41a2e40bf746cacd24916346510001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/15.png?q-sign-algorithm=sha1&q-ak=AKIDpqtPvaJA40InJaYWPz4gTyd42uo96AdH&q-sign-time=1553316530;1553318330&q-key-time=1553316530;1553318330&q-header-list=&q-url-param-list=&q-signature=94811aca49f68f32b77ece954b8486f2f7a9ed17&x-cos-security-token=6392005799145a9c91ee08444bff81477251af5110001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/16.png?q-sign-algorithm=sha1&q-ak=AKIDR7rnPe4FuQidQycssMOVjkpyH3Ppo3e1&q-sign-time=1553316546;1553318346&q-key-time=1553316546;1553318346&q-header-list=&q-url-param-list=&q-signature=cc38214c80fd72c7eeb199bc5cc135ae8be6aa32&x-cos-security-token=a778e73c398ac026dd89db40a3d19acdc8488d8410001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/17.png?q-sign-algorithm=sha1&q-ak=AKIDfrBJC1bFlD67SwAqdCUXCoE685WXTPLi&q-sign-time=1553316561;1553318361&q-key-time=1553316561;1553318361&q-header-list=&q-url-param-list=&q-signature=68ca3683cd343a026466cebf728419b2e1dfd99d&x-cos-security-token=a6168750289872a32513d6a8af537095f4f7ce2c10001)
![](https://fireguytop-1257361176.cos.ap-chongqing.myqcloud.com/jenkins-setup/18.png?q-sign-algorithm=sha1&q-ak=AKIDSAuWg2aIxYcJ8gcpv8dqR9S870aPh5oQ&q-sign-time=1553316579;1553318379&q-key-time=1553316579;1553318379&q-header-list=&q-url-param-list=&q-signature=cfd9f3e429cb38551eca7e5654f4a2ffcfbf0aac&x-cos-security-token=acfcd076aacc78a574b5763dd2ce31182bc5e30a10001)
