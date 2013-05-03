---
layout: post
title: "Directspace.net 年付15刀768MB内存VPS监控"
description: "监控Directspace.net 年付15刀768MB内存VPS是否有货，基于nodejs。"
category: vps
tags: [directspace, vps, nodejs]
---

### vps配置

> * CPU: 1核心
> * 硬盘: 20G
> * 保证内存: 512MB
> * 最大内存: 768MB
> * 月流量: 750GB
> * 虚拟化技术: openvz
> * 价格: 15美元/年
> * 测试IP: 69.163.35.1

这款VPS还是非常有性价比的，以至于官方长期无货，下面的脚本就是用来监视官方是否放货的。

### 项目地址

<https://github.com/soncy/directspace-monitor>

### 使用前提

确保已经安装了`nodejs`，`git`，`sendmail`

### 使用方法

    git clone git://github.com/soncy/directspace-monitor.git
    cd directspace-monitor/
    node dsmonitor.js youremail@email.com -t

`youremail@email.com`替换成接收邮件的邮箱，不填的话会发送到我的邮箱哦，如果发到139的邮箱，就可以设置短信提醒了

使用`-t`参数会在脚本启动时往邮箱发一封邮件来测试是否能收到邮件

建议在screen下启动监控脚本。

邮件标题：`DirectSpace 有货啦！`

### 可以帮忙

不方便自己跑这脚本的同学可以把邮箱地址给我，我在我的VPS上跑。

### 官方链接

<http://eportal.directspace.org/cart.php?a=add&gid=22>


