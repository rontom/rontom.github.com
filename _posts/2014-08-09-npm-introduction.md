---
layout: post
published: true
title: "NPM���ܼ�ʹ��"
---

------------------------------------------------------    
 
####NPM�Ľ���####       

NPM��Node Package Manager,��һ��NodeJS������ͷַ����ߣ��൱��ruby��gem��Python��pypi��setuptools��PHP��pear���Ƿǹٷ��ķ���Nodeģ�飨�����ı�׼���ܽ��NodeJS���벿���ϵĺܶ����⡣ĿǰNodeJS�Ѿ�������NPM���������������롰npm -v���鿴�Ƿ�װ�ɹ���

####NPM�ĳ�������####

NPM�ṩ����������install��publish����ʹ��npm help�鿴�������������һЩ���õ����
 
 > * npm help \<command> �ɲ鿴ĳ���������ϸ����������npm help install
 > * npm install \<package name> -g �԰�����ȫ��װ��ȫ��װ��ͨ��ֻ��Ϊ��ִ�����ж��ѡ����� npm install express -g ���������װ�ڲ�ͬ��Ŀ�С�ʹ�� npm install \<package name>��
 > * npm uninstall \<package name> -g ж��ȫ�����
 > * npm search \<package name> ��Ѱ�������� npm search  express
 > * npm ls -g �г�ȫ�����npm ls -gl �г�ȫ�����ϸ��Ϣ���г�ĳ��Ŀ���ķ������Ƚ������Ŀ����Ŀ¼�� npm ls -l��
 > * npm update -g ����ȫ�����������Ŀ������Ŀ¼��npm update��
 >* npm config  ���ð��� npm config set registry https://registry.npm.taobao.org
 >* npm explore . --git pull origin master .���µ�ǰ�� git ��Դ�⡣
 >* npm edit �༭��ǰ����ģ�����������ģ�顣
 >* npm docs \<package name> ��\<package name>ģ����ĵ���
 >* npm outdated \<package name>�鿴\<package name>�Ƿ����°汾��
 > * npm cache clear ���NPM���ػ��棬���ڶԸ�ʹ����ͬ�汾�ŷ����°汾������ˡ�
 > * npm publish \<package name>@\<version> �����汾���롣
 > * npm unpublish \<package name>@\<version>
 > * npm adduser ����ע�ᷢ������ʱ��Ҫ���б༭package.json��package.jsonһ���������£�
    
    {
    "name": "express",           # ��������NPM����������Ҫ����Ψһ
    "version": "1.0.0",            # ��ǰ�汾��
    "dependencies": {              # ����������������Ҫָ�������Ͱ汾��
        "argv": "0.0.2"
      },
    "main": "./lib/echo.js",       # ���ģ��λ��
    "bin" : {
        "node-echo": "./bin/node-echo"      # �����г���������ģ��λ��
      }
    }
    

####����NPM����ʹ��####

�Ա�npm����
> ������ַ��http://npm.taobao.org/   
> registry��ַ��http://registry.npm.taobao.org/

cnpmjs����

> ������ַ��http://cnpmjs.org/   
registry��ַ��http://r.cnpmjs.org/

npm����ʹ��    
 
 1.��ʱʹ��   
> npm --registry https://registry.npm.taobao.org install express         

2.����ʹ��   
>  npm config set registry https://registry.npm.taobao.org  // ���ú��ͨ�����淽ʽ����֤�Ƿ�ɹ�  
npm config get registry
// ��   
npm info express
 