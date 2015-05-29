---
layout: post
published: true
title: "网页设计中文本如何垂直居中备案录"
---

--------------------------------------------------- 

###问题来袭
我在网页设计中，常常出现如何使文本块居中所在的区域块？我知道有一个标签属性<code>vertical-align</code>可以设置，但每次都无法另外满意。即使能够得到最终的结果。于是我从网上找了找，发现一些方法可以使用。

###针对单行文本
对于单行文本的，顾名思义得进行<code>line-height</code>设置。方法：把文本块的段落高度<code>line-height</code>与其所在区域块高度<code>height</code>设为一致。   
<b>案例：</b>
<pre>
&lt;!DOCTYPE html>
&lt;html lang="zh-cn">
&lt;head>
  	&lt;meta charset="utf-8">
  	&lt;meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1.0, user-scalable=no">
  	&lt;meta http-equiv="X-UA-Compatible" content="IE=edge">
  	&lt;title>学无止境，静水流深</title>
  	&lt;meta name="description" content="">
	&lt;!-- Favicons -->
	&lt;!-- CSS -->
&lt;/head>
&lt;body>
   &lt;div style="height:68px ; line-height:68px;">&lt;/div>
&lt;/body>
&lt;/html>
</pre>

###针对多行文本
对于多行，由于无法确定多行的高度，因此固定设定高度是不适合的。对所含区域高度得进行自适应设定，然后通过 <code>padding</code>属性进行设置。但是这样去进行设定其实是有一定要求的，你的<code>padding</code>值得根据上下内容进行操作。   
<b>案例：</b>
<pre>
&lt;!DOCTYPE html>
&lt;html lang="zh-cn">
&lt;head>
  	&lt;meta charset="utf-8">
  	&lt;meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1.0, user-scalable=no">
  	&lt;meta http-equiv="X-UA-Compatible" content="IE=edge">
  	&lt;title>学无止境，静水流深</title>
  	&lt;meta name="description" content="">
	&lt;!-- Favicons -->
	&lt;!-- CSS -->
&lt;/head>
&lt;body>
   &lt;div style="padding:200px 200px; height:600px;width:600px; ">&lt;/div>
&lt;/body>
&lt;/html>
</pre>

### 浏览器居中设定
浏览器居中设定相对来说比较简单，把属性<code>position</code>的属性值市委绝对，然后<code>top</top>的属性值为（50%-width/2）,同理<code>left</code>的属性值为(50%-width/2).这样就完成了设置。   
<b>案例：</b>
<pre>
&lt;!DOCTYPE html>
&lt;html lang="zh-cn">
&lt;head>
  	&lt;meta charset="utf-8">
  	&lt;meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1.0, user-scalable=no">
  	&lt;meta http-equiv="X-UA-Compatible" content="IE=edge">
  	&lt;title>学无止境，静水流深</title>
  	&lt;meta name="description" content="">
	&lt;!-- Favicons -->
	&lt;!-- CSS -->
&lt;/head>
&lt;body>
   &lt;div style="position:absolute;top:40%;left:40%; height:20%;width:20%; ">&lt;/div>
&lt;/body>
&lt;/html>
</pre>

### 区域块文本垂直居中
上述三种方法很难很好地处理区域块文本垂直居中。通过标签嵌套进行。
<pre>
 &lt;div class="one">
     &lt;div class="two">
    &lt;/div>
&lt;/div>
</pre>
设置.one 和.two的css样式为：   
<pre>
.one{
    display:table;
    width:100%;
    height:400px;
    overflow:hidden;
    background:#ccc;
}
.two{
    display:table-cell;
    verital-align:middle;
    margin-left:30%;
}
</pre>

.one中<code>display</code>的属性值设为table，表示此元素作为块级表格来显示（类似\<table>）,表格前后带有换行符。.two中<code>display</code>的属性值设为table-cell，表示此元素作为表格单元显示（类似\<td>和\<th>）。那么上面文本块相当于一个单元表格中的文本块。   
<b>注释</b>：如果规定了<code>!DOCTYPE</code>,则Internet Explorer 8(以及更高版本)可以支持"table-cell"属性值。对于< IE 8 的其实还有一种不错方法进行。   
<pre>
 &lt;div class="one">
     &lt;div class="two">
         &lt;div class="three">
          &lt;/div>   
    &lt;/div>
&lt;/div>
</pre>


设置.one , .two, .three的css样式如下：
<pre>
.one{
    position:relative;
}
.two{
    position:absolute;
    top:50%;
}
.three{
     position:relatvie;
     top:-50%;
}
</pre>

这样就完美的解决了。

### 小结
上述无疑是对<code>position</code>和<code>display</code>的属性进行相应设置而得出的所需效果。