---
layout: post
published: true
title: "在Python中列表、元组、集合、字典的比较"
---

###在Python中列表、元组、集合、字典的比较###
-------------------------------------------      

####列表####   

列表是任意对象的序列。把值放在方括号中就可以创建列表。从该定义可以看出在列表方括号可以是数值、字符集、函数、元组、集合、字典以及列表等。如下所示：   
{% highlight vim %}
nums=[3,4,2,6]    
names=['Rontom','Sarbi','Wharti','Kawoyi']   
objs=[('rontom',100,10.23),('www.langoft.com',80),(whatis,yourname,yourphone)]
{% endhighlight %}   
既然最为序列，那必须可以进行索引。列表使用是从0开始的整数索引，同时可以使用索引运算符访问及修改列表中的选项。如下：
{% highlight vim %}
n = names[2]	#names来自上述中的列表.n的返回值为‘Wharti’
names[0]='Hacker'	#此时将该names中的第一项，即列表names=['Hacker','Sarbi','Wharti','Kawoyi']
{% endhighlight %}   
列表具有追加、插入、替换、删除元素等功能，同时具有提取和连接列表的功能,此外还具有构建功能（列表包含）。   
创建一个空列表有两中方式：   
{% highlight vim %}   
names=[]
names=list()
{% endhighlight %}   

#### 元组 ####   

元组是一组值通过圆括号(即使没有，Python也是可识别出的)打包在一个的对象中的数据结构。例如：   
{% highlight vim %}   
  hacker=('Stivem','Rontom','rontom')   
  website=('www.chinadream.me',80,'www.hacklang.me',4000) 
{% endhighlight %}   
 对于0个和1个的元素的元组，语法有点特殊:
{% highlight vim %}
hacker = ()   
hacker_age = (58,)
{% endhighlight %}

#### 集合 ####

集合是一组无序不能重复元素组成的对象。由于集合是无序的，无法通过数字进行索引。可使用set()函数创建一个集合。例如：
{% highlight vim %}
>>> test=set('ttttttttttttest')
>>> test
{'s', 'e', 't'}
>>> 
{% endhighlight %}
集合跟数学所说的集合差不多。支持一系列的标准操作。包括并集、交集、差集和对称差集，例如：
{% highlight vim %}
>>> act=set('aaaaaaaaaaaaaact')
>>> act | test
{'a', 'c', 'e', 't', 's'}
>>> act & test
{'t'}
>>> act - test
{'a', 'c'}
>>> act ^ test
{'a', 'c', 's', 'e'}
>>> 
{% endhighlight %}
集合也可以进行增项(**add()**、**update()**）、删项（**remove()**）操作。

      