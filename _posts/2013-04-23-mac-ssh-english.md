---
layout: post
title: "中文mac osx ssh到目标机器提示信息变为中文的解决方案"
description: "中文mac osx ssh到目标机器提示信息变为中文的解决方案"
category: mac
tags: [mac, ssh]
---

最近登录VPS后发现所有的提示都变成中文了，比如`cd`一个不存在的目录，会提示：

    -bash: cd: ss: 没有那个文件或目录

这样方便理解，但是如果有错误信息的话，不便于去搜索引擎查找。

### 解决方案

变回英文提示信息的解决方案：在`~/.bash_profile`中增加
    
    export LANG=en_US.UTF-8
    export LC_CTYPE=zh_CN.UTF-8 #输入法设置
    export LC_NUMERIC="en_US.UTF-8"
    export LC_TIME="en_US.UTF-8"
    export LC_COLLATE="en_US.UTF-8"
    export LC_MONETARY="en_US.UTF-8"
    export LC_MESSAGES="en_US.UTF-8"
    export LC_PAPER="en_US.UTF-8"
    export LC_NAME="en_US.UTF-8"
    export LC_ADDRESS="en_US.UTF-8"
    export LC_TELEPHONE="en_US.UTF-8"
    export LC_MEASUREMENT="en_US.UTF-8"
    export LC_IDENTIFICATION="en_US.UTF-8"

这样包括日期格式在内的所有信息都是英文的了，上面说的目录不存在的提示就会恢复成：
    
    -bash: cd: ss: No such file or directory