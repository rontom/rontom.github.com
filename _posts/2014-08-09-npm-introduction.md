---
layout: post
published: true
title: "NPM介绍及使用"
---

------------------------------------------------------    
 
####NPM的介绍####       

NPM是Node Package Manager,是一个NodeJS包管理和分发工具，相当于ruby的gem，Python的pypi、setuptools，PHP的pear。是非官方的发布Node模块（包）的标准。能解决NodeJS代码部署上的很多问题。目前NodeJS已经集成了NPM。可以命令行输入“npm -v”查看是否安装成功。

####NPM的常用命令####

NPM提供了许多命令，如install和publish，可使用npm help查看所有命令。下面是一些常用的命令：
 
 > * npm help \<command> 可查看某条命令的详细帮助，例如npm help install
 > * npm install \<package name> -g 对包进行全域安装，全域安装包通常只是为了执行运行而已。例如 npm install express -g 。如果包安装在不同项目中。使用 npm install \<package name>。
 > * npm uninstall \<package name> -g 卸载全域包。
 > * npm search \<package name> 搜寻包。例如 npm search  express
 > * npm ls -g 列出全域包。npm ls -gl 列出全域包详细信息。列出某项目包的方法，先进入该项目所在目录， npm ls -l。
 > * npm update -g 更新全域包。进入项目的所在目录，npm update。
 >* npm config  配置包。 npm config set registry https://registry.npm.taobao.org
 >* npm explore . --git pull origin master .更新当前的 git 资源库。
 >* npm edit 编辑当前包或模块的所有依赖模块。
 >* npm docs \<package name> 打开\<package name>模块的文档。
 >* npm outdated \<package name>查看\<package name>是否有新版本。
 > * npm cache clear 清空NPM本地缓存，用于对付使用相同版本号发布新版本代码的人。
 > * npm publish \<package name>@\<version> 发布版本代码。
 > * npm unpublish \<package name>@\<version>
 > * npm adduser 进行注册发布。这时需要进行编辑package.json。package.json一般类似如下：
    
    {
    "name": "express",           # 包名，在NPM服务器上须要保持唯一
    "version": "1.0.0",            # 当前版本号
    "dependencies": {              # 第三方包依赖，需要指定包名和版本号
        "argv": "0.0.2"
      },
    "main": "./lib/echo.js",       # 入口模块位置
    "bin" : {
        "node-echo": "./bin/node-echo"      # 命令行程序名和主模块位置
      }
    }
    

####国内NPM镜像使用####

淘宝npm镜像
> 搜索地址：http://npm.taobao.org/   
> registry地址：http://registry.npm.taobao.org/

cnpmjs镜像

> 搜索地址：http://cnpmjs.org/   
registry地址：http://r.cnpmjs.org/

npm镜像使用    
 
 1.临时使用   
> npm --registry https://registry.npm.taobao.org install express         

2.永久使用   
>  npm config set registry https://registry.npm.taobao.org  // 配置后可通过下面方式来验证是否成功  
npm config get registry
// 或   
npm info express
 