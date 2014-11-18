---
layout: post
published: true
title: "系统管理的基本命令"
---

----------------------------------

#### 0.文件查找命令 ####
文件查找命令主要有find,locate,whereis,which,type,grep等.
00. 在目录或其子目录下查找文件或目录名:find dir -name file   
示例 : find ./ -name 2013-01-11.md
01. 查找文件组或目录组: find dir -name 'file glob'   
示例: find /etc/ -name '*~'
