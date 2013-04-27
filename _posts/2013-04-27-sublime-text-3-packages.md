---
layout: post
title: "Sublime text 3 for Mac的packages相关"
description: "Sublime text 3的packages安装，运行模式，如何修改等"
category: sublime text
tags: [sublime text, packages]
---

### 如何安装Package Control

根据Sublime作者的[描述](http://wbond.net/sublime_packages/package_control/installation#ST3)，Sublime Text 3(以下简称ST3)的Package安装方式如下：

使用`Preferences > Browse Packages…`打开Packages目录

    cd Packages/
    git clone https://github.com/wbond/sublime_package_control.git "Package Control"
    cd "Package Control"
    git checkout python3

安装完之后就可以跟ST2一样使用Package Control了

### 安装的Packages在什么位置

ST3和ST2的 Packages管理有一个很大的不同就是，用户安装的packages不再放在`~/Library/Application Support/Sublime Text 3/Packages`目录下了，而是放到了`~/Library/Application Support/Sublime Text 3/Installed Packages`目录下，一个packages也不再是一个目录，以`Todo Manager.sublime-package`这样的格式存放的zip包。

### 安装ST3时自带的Packges在哪

比如`Color Scheme - Default`这样的默认的packages在哪呢？在：
    
    /Applications/Sublime Text.app/Contents/MacOS/Packages

同样是以 `Color Scheme - Default.sublime-package`的方式存在

### 如何修改Packages

使用`unzip`解压你想要修改的`*.sublime-package`，修改后重新压缩，并将后缀改回 `.sublime-package`即可

### 兼容ST2的Packages模式

ST3的Packages兼容ST2的方式，即可以直接将你想要的packages以目录的方式放到 `~/Library/Application Support/Sublime Text 3/Packages`目录。

### 其他注意

ST3的Packages采用了`Python 3`，如果你的packages出现了不工作的情况，在原作者还没来得及更新的情况的，可以自己用`` ctrl+` ``调出控制台，查看错误信息并修改。
  