---
title: Gitlab安装配置教程
date: 2016-10-27 10:25:11
tags: [git, linux]
---

> 官网地址: [gitlab](https://about.gitlab.com/)

# 基础安装教程
下面介绍在centos 6 上安装的方法，其他方法可参考官网[https://about.gitlab.com/downloads](https://about.gitlab.com/downloads)
<!-- more -->
1. 开启http和ssh
```sh
sudo yum install curl openssh-server openssh-clients postfix cronie
sudo service postfix start
sudo chkconfig postfix on
sudo lokkit -s http -s ssh
```

2. 添加gitlab软件源并且安装
```sh
curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
sudo yum install gitlab-ce
```

3. 自动配置gitlab并启动
```sh
sudo gitlab-ctl reconfigure
```

# 高级配置

1. 修改Gitlab默认端口号
    
gitlab默认端口号是`80`，我们需要修改为其他端口号，方法如下：

修改配置文件
```sh
sudo vi /etc/gitlab/gitlab.rb
```

将其中的`external_url`增加端口号即可，如我的改为`8888`端口
```bash
external_url 'http://192.168.70.22:8888'
```

再次执行以下命令使配置生效并重启服务
```sh
sudo gitlab-ctl reconfigure
```
