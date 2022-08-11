---
layout: post
title: ubuntu系统安装
date: 2022-08-11 15:35
categories:
  - 系统
---

Ubuntu系统下的安装
<!-- More -->

# docker环境安装
* 安装[docker](https://docs.docker.com/install/)和[docker-compose](https://docs.docker.com/compose/install/)
```bash
# root用户下
apt-get update -y
adduser ${REMOTE_USERNAME}
echo '${REMOTE_USERNAME} ALL=(ALL:ALL) ALL' | sudo EDITOR='tee -a' visudo
usermod -aG docker ${REMOTE_USERNAME}

# ${REMOTE_USERNAME}用户下安装docker
curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun

# 安装docker-compose 参考自
sudo curl -L "https://github.com/docker/compose/releases/download/1.28.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```
