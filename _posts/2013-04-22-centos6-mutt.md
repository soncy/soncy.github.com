---
layout: post
title: "centos 6.2下mutt添加附件的使用"
description: "centos 6.2下mutt添加附件的使用"
category: linux
tags: [linux]
---

切换到linode，系统是centos 6.2把原来的自动备份mysql脚本添加到定时任务后，发现居然一封邮件都没有收到，手动执行了下脚本，报了个错

	无法 stat email@gmail.com：没有那个文件或目录
	email@gmail.com：无法附加文件。
	
英文的错误应该是：

	Can’t stat email@gmail.com: No such file or directory
	email@gmail.com: unable to attach file.
	
大概意思是无法添加附件，这是mutt报出来的错，发送邮件的脚本如下：
	
	echo "数据库备份" | mutt -a databackup.sql -s "数据库备份" email@gmail.com
	
google之后发现老外也遇到过，解决方案如下：
	
	echo "数据库备份" | mutt -s "数据库备份" email@gmail.com -a databackup.sql

测试成功，在自己的两台centos 6.2上都有这个问题，不知道是不是centos 6之后改了mutt的用法