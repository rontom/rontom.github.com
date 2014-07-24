###Python代码编写出现的错误###

####python默认编码错误SyntaxError:Non-ASCII character '\xe5'之解决方法####

在编写python时，当使用中文输出或注释时运行脚本，会提示错误信息：	
SyntaxError:Non-SACII character '\xe5' in file......

解决方法：python的默认编码文件用的是ASCII码，你将文件保存为UTF-8，解决方法很简单，在文件开头加入
\#-*-coding:utf-8-*- 或者是\#coding=utf-8
