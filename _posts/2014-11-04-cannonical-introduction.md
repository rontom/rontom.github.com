---
layout: post
published: true
title: "标签link的属性rel的值为cannonical介绍"
---

----------------------------------------------

### cannonical介绍
&nbsp;&nbsp;&nbsp;&nbsp;此处cannonical是指来自：
>&lt;link rel="cannonical" href="http://www.hacklang.me">

中的"cannonical.它由 Google、Yahoo、Microsoft等搜索引擎一起推出的一个标签属性值，主要是用来解决由于网址形式不同内容相同而造成的内容重复问题，有助于搜索引擎能够可选择性抓取你想要强调的内容。

### 举例
&nbsp;&nbsp;&nbsp;&nbsp;举个例子，假设有如下的网址：   

>http://hacklang.me/2014/07/   
>http://hacklang.me/2014/07/02/rontom-hack.html?comments=true   
>http://hacklang.me/2014/07/11/research-can.html?id=34&submit=true

可以看出三个网址是不一样，假设打开它们网站的内容却是相同的，这样搜索引擎很难分辨出来哪个才是网站主想要强调的网址，这样会直接造成搜索引擎在你的站里面收录到大量重复的内容，，为了把第一个网址给搜索引擎来进行显示，我们可以通过 canonical 标签就可以解决，设定第一个网址为主要强调的。设置如下：
>&lt;link rel="cannonical" href="http://hacklang.me/2014/07/">