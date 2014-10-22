---
layout: post
published: true
title: "Python中sys.argv用法"
---


------------------------------------------------------    
 
####介绍####       

sys.argv变量是一个字符串（包含了命令行参数）列表，即使用命令行传递给你的程序的参数。也包括python脚本名本身。其中sys为python标准模块，直接import sys插入使用，这是sys.argv[]能够使用的条件。argv是argument vector的简写，即参数指针。sys.argv[0]代表代码本身文件路径。sys.argv[1]代表地一个参数，依此类推。

####举例说明####
{% highlight python %}
    >>>import sys
    >>>python ×××.py  langoft.com for you to choose.  #sys.argv[0] 代表你运行的代码本身，即本例中'×××.py',而sys.argv[1]为第一个参数即'langoft.com',sys.argv[2]为'for'。
    >>>import os ,sys
    >>>os.system(sys.argv[1])
    >>>python ×××.py vim  #os.system是用来执行命令行的。因此该程序会接受到第一个参数为'vim'，即执行vim,这样你将打开vim编辑界面了。
{% endhighlight %}
####应用实例####
<pre>
{% highlight python %}
\#!/usr/bin/env python
\# -*- coding: utf-8 -*-
\# A revised example from A Byte of Python
\# sys-argv1.py

import sys
def readfile(filename):         #从文件中读出文件内容
        '''Print a file to the standard output.'''   
        f=open(filename)	#可使用file()代替
        while True:
                line=f.readline() #readline()文件内容单行读取，而read(),readlines()是整个文件内容读取
                if len(line)==0:
                        break
                print line     #分别输出每行内容
''' 上面一段代码可以更改如下：
	while True:
          		for line in  f.readlines():
	   		if not len(line) or len(line)==0:	#其实not len(line) 和len(line)==0表达的意思差不多
	  			break
	 		print line
'''
        f.close()

\# Script starts from here
if len(sys.argv)<2:
        print 'No action specified.'
        sys.exit()
if sys.argv[1].startswith('--'): 
        option=sys.argv[1][2:]
        if option=='version':   #当命令参数为--version，显示版本号
                print'Version 1.2'
        elif option=='help':    #当命令参数为--help时，显示相关帮助内容
                print'''

This program prints files files to the standart output.
Any number of files can be specified.
Options include:
--version:Prints hte version number
--help   :Display the hellp'''
        else:
                print 'Unknow option.'
        sys.exit()
else:
        for filename in sys.argv[1:]:   #当参数为文件名时，传入readfile，读出其内容。
                readfile(filename)

{% endhighlight %}
</pre>
