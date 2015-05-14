---
layout: post
published: true
title: "DNS Prefetch"
---

-----------------------------------------------------------

#### 1.DNS的介绍
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DNS（Domain Name System，域名系统），因特网上作为域名和IP地址相互映射的一个分布式数据库，能够使用户更方便的访问互联网，而不用去记住能够被机器直接读取的IP数串。通过主机名，最终得到该主机名对应的IP地址的过程叫做域名解析（或主机名解析）。DNS协议运行在UDP协议之上，使用端口号53。在RFC文档中RFC 2181对DNS有规范说明，RFC 2136对DNS的动态更新进行说明，RFC 2308对DNS查询的反向缓存进行说明（来自百度百科）。DNS的功能是实现映射，由主机名到IP地址的映射有两种：静态映射，动态映射。更多信息可[百度](http://www.baidu.com)搜索。

#### 2.什么是DNS Prefetch？
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;由于DNS实现的是域名到IP的映射，如果通过域名访问站点，必须做DNS解析。目前每次DNS解析，通常在200ms以下。针对DNS解析耗时问题，一些浏览器通过DNS Prefetch 来提高访问的流畅性。 DNS Prefetch 是一种DNS 预解析技术，当你浏览网页时，浏览器会在加载网页时对网页中的域名进行解析缓存，这样在你单击当前网页中的连接时就无需进行DNS的解析，减少用户等待时间，提高用户体验。

#### 3.DNS Prefetch的实现
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;通过meta标签信息来告知浏览器, 当前页面要做DNS预解析:
    
    <meta http-equiv="x-dns-prefetch-control" content="on" />
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在页面head标签中使用link标签来强制对DNS预解析: 
    
    <link rel="dns-prefetch" href="http://www.chinadream.me" />
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;如果要控制浏览器端是否对域名进行预解析，可以通过Http header 的x-dns-prefetch-control 属性进行控制。

#### 4.DNS Prefetch使用的坏处
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;多页面重复DNS预解析会增加重复DNS查询次数。虽然DNS预解析有利用提高网站前端页面优化体验，但也加重网站自身的DNS查询。
