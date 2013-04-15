---
layout: post
title: "jekyll的一些使用细节"
description: ""
category: jekyll
tags: [jekyll]
---

### rake post的使用

jekyll默认的没有`rake post`命令，jekyll-bootstrap才有，如果要用的话可以自己在`username.github.com`目录下建一个Rakefile文件，内容可以参考：<https://github.com/plusjade/jekyll-bootstrap/blob/master/Rakefile>

### RDiscount的安装

网上有写RDiscount安装教程是错的，正确的安装方法是：

	[sudo] gem install rdiscount

不是：

	[sudo] gem install RDiscount

	
### 自动生成

本地启动`jekyll --server`后，每次对模板，内容或者样式的更改都需要重启服务才会生成新的页面，这样改动频繁的话很麻烦，jekyll提供一个`--auto`参数可以自动生成，启动服务的时候使用`jekyll --server --auto`，或者加到配置文件中即可，不过貌似只有更改根目录下的文件(比如`_config.yml`)才会触发重新生成，更改模板或者文章内容不会出发重新生成。有知道方法的可以告诉一声，谢谢。

