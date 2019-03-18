---
title: jenkins setup
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

![](/jenkins-setup/20190313093123368.png)
![](/jenkins-setup/20190313093724682.png)
![](/jenkins-setup/20190314123354141.png)

## 问题1
![](/jenkins-setup/20190314122849087.png)
### 解决办法
将type -p java的输出内容替换/etc/init.d/jenkins文件中的'type -p java'，重新加载，重启jenkins，验证http://localhost:8080
```
sudo gedit /etc/init.d/jenkins
systemctl daemon-reload
sudo service jenkins start
systemctl status jenkins.service
```
![](/jenkins-setup/20190314123042225.png)
![](/jenkins-setup/20190314123300322.png)
![](/jenkins-setup/20190314123113162.png)

## 问题2
![](/jenkins-setup/20190314124343930.png)
![](/jenkins-setup/20190314124444015.png)
![](/jenkins-setup/20190314124457301.png)
![](/jenkins-setup/20190314124514120.png)
![](/jenkins-setup/20190314124605716.png)
![](/jenkins-setup/20190314124638403.png)
![](/jenkins-setup/20190314124904403.png)
![](/jenkins-setup/20190314125040336.png)
![](/jenkins-setup/20190314125055246.png)
![](/jenkins-setup/20190314125112763.png)
![](/jenkins-setup/20190314125134075.png)
