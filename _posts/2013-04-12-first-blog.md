---
    layout: post
    title: 个人站点搬迁至github
---

其实也不叫搬迁，就在github上新建了个站点，之前的站点由于没来及备份资料，已经找不回了。

`github`加`jekyll`的方式是我比较喜欢的方式，至少不用打理服务器了，还能用`markdown`来写。

新的站点采用`jekyll`的方式，使用`bootstrap`布局，用`markdown`的语法完成，托管在`github.com`上。

访问域名还是 <http://qifendi.com>

## test code highlight

{% highlight javascript %}
var text = "hello world";
console.log(text);

//test object highlight
function Foo() {
	this._name = "Foo";
}

Foo.prototype.modifyName = function(name) {
	this._name = name;
};

var foo = new Foo();
foo.modifyName('foo');
{% endhighlight %}