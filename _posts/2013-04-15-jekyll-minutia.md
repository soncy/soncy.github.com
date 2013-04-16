---
layout: post
title: "jekyll的一些使用细节"
tags: [jekyll]
category: Jekyll
---

### rake post的使用

jekyll默认的没有`rake post`命令，jekyll-bootstrap才有，如果要用的话可以自己在`username.github.com`目录下建一个Rakefile文件，内容可以参考：<https://github.com/plusjade/jekyll-bootstrap/blob/master/Rakefile>

### RDiscount的安装

网上有写RDiscount安装教程是错的，正确的安装方法是：

	[sudo] gem install rdiscount

不是：

	[sudo] gem install RDiscount

	
### 自动生成

本地启动`jekyll --server`后，每次对模板，内容或者样式的更改都需要重启服务才会生成新的页面，这样改动频繁的话很麻烦，jekyll提供一个`--auto`参数可以自动生成，启动服务的时候使用`jekyll --server --auto`，或者加到配置文件中即可，不过貌似只有更改根目录下的文件(比如`_config.yml`)才会触发重新生成，更改模板或者文章内容不会触发重新生成。有知道方法的可以告诉一声，谢谢。

### URL

如果文章里写了分类（category），那么生成静态页面的时候会加上分类的目录，如：

	---
	layout: post
	title: "jekyll的一些使用细节"
	tags: [jekyll]
	category: Jekyll
	---

就会生成一个jekyll目录，然后在jekyll目录下再按日期和标题生成，最后的url就是：`/jekyll/2013/04/15/jekyll-notice.html`，如果不想生成这个目录或者不想在URL中有这个路径，可以在配置文件中指定永久链接格式，参数：`permalink`，如：`permalink: /:year/:month/:day/:title.html`，这样url就是`/2013/04/15/jekyll-notice.html`了。