---
layout: post
published: true
title: "CSS Reset的应用"
---

-----------------------------------------------------------

#### 1.CSS Reset的介绍
在HTML标签在浏览器里有默认的样式，例如 p 标签有上下边距，strong标签有字体加粗样式，em标签有字体倾斜样式。不同浏览器的默认样式之间也会有差别，例如ul默认带有缩进的样式，在IE下，它的缩进是通过margin实现的，而Firefox下，它的缩进是由padding实现的。在切换页面的时候，浏览器的默认样式往往会给我们带来麻烦，影响开发效率。所以解决的方法就是一开始就将浏览器的默认样式全部去掉，更准确说就是通过重新定义标签样式。“覆盖”浏览器的CSS默认属性。最最简单的说法就是把浏览器提供的默认样式覆盖掉！这就是CSS reset(来自百度百科)。

#### 2.reset.css
在HTML中通过样式表进行浏览器的默认设置重置。    
a.firfox的默认HTML样式表   
>[http://hg.mozilla.org/mozilla-central/file/tip/layout/style/html.css](http://hg.mozilla.org/mozilla-central/file/tip/layout/style/html.css)   
  
b.webkit的默认HTML样式表
>[http://trac.webkit.org/browser/trunk/Source/WebCore/css/html.css](http://trac.webkit.org/browser/trunk/Source/WebCore/css/html.css)

#### 3.为什么要重置呢？
因为浏览器众多，每个浏览器的样式不一，为了统一样式属性，便于编写css代码，提高各浏览器的显示效果的相同度。   

#### 4. 比较流行的css reset
可以访问[http://cssreset.com/](http://cssreset.com/),上面给出几种重置代码。可以研究研究开发出自己的重置样式。

#### 5. css reset 代码
a. 最为简化的css reset：
{% highlight vim %}
*{
	padding:0;
	margin:0;
}
{% endhighlight %}
这是最简单的css重设，将所有的元素的padding和margin设为0.更改一下：
{% highlight vim %}
    *{
	    padding:0;
	    margin:0;
	    border:0;
	    outline:0;
    }
{% endhighlight %}
在原来的基础上添加对border,outline属性的重设，设为初始值为0.

b. 较为可行的css reset:
{% highlight vim %}
*{
    margin:0;
    padding:0;
    border:0;
    outline:0;
    vertical-align:baseline;
    font-family:inherit;
    font-weight:inherit;
    font-style:inherit;
    font-size:100%;
}
{% endhighlight %}
上述css reset较为简单实用。对边框、边距、字体等进行初始化。

c.yahoo(YUI) css reset

    body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,form,fieldset,input,textarea,p,blockquote,th,td{
        margin:0;
        padding:0;
    }
    table{
        border-collapse:collapse;
        border-spacing:0;
    }
    fieldset,img{
        border:0;
    }
    address,caption,cite,code,dfn,em,strong,th,var{
        font-weight:normal;
        font-style:normal;
    }
    ol,ul{
        list-style:none;
    }
    caption,th{
        text-align:left;
    }
    h1,h2,h3,h4,h5,h6{
        font-weight:normal;
        font-size:100%;
    }
    q:before, q:after{
        content:"";
    }
    abbr,acronym{
        border:0;
    }


d.看看大型网站淘宝网css reset
```
html{
    color:#000;
    background-color:#fff;
}
body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,code,form,fieldset,logend,input,button,textarea,p,blockquote,th,td{
    margin:0;
    padding:0;
}
table{
    border-collapse:collapse;
    border-spacing:0;
}
fieldset,img{
    border:0;
}
address,caption,cite,code,dfn,em,strong,th,var{
    font-style:normal;
    font-weight:normal;
}
li{
    list-style:none;
}
caption,th{
    text-align:left;
}
h1,h2,h3,h4,h5,h6{
    font-size:100%;
    font-weight:normal;
}
q:before,q:after{
    content: '';
}
abbr,acronym{
    border:none;
    font-variant:normal;
}
sup{
    vertical-align:text-top;
}
sub{
    verticala-align:text-bottom;
}
input,button,textarea,select{
    font-family:inherit;
    font-size:inherit;
    font-weight:inherit;
}
input,button,textarea,select{
    *font-size:100%;
}
legend{
    color:#000;
}
del,ins{
    text-decoration:none;
}
small{
    font-size:100%;
}
```

#### 6.小结
总之，css reset能够很好地处理不同浏览器显示效果相统一。
