---
layout: post
published: true
title: " window安装kali系统之后如何找回windows引导"
---


------------------------------------------------------    
 
####背景####       
当我们window安装kali系统之后发现window引导找不到，虽然我们仍可以通过window启动盘来找回，但怎是觉得有点不爽。其实有一种不错的方法可以试试：

####操作###
{% highlight vim %}
	>>>gedit /boot/grub/grub.cfg
{% endhighlight %}
   打开grub.cfg文件后找到### BEGIN /etc/grub.d/40_custom ###这里.在根据我下面的注释来修改引导项
{% highlight vim %}                          
    menuentry "windows8-by hacklang.me" {                                    
    insmod part_msdos
    insmod ntfs
    set root='(hd0,msdos1)'                             //这个地方改为你windows所在的分区注意windows7以上版本要改为那个200MB的分区
    search --no-floppy --fs-uuid --set=root 3802386C0238316C    //这个地方有些人没有set=root所以要自己修改,后面跟着的是UUID
    chainloader +1}
{% endhighlight %}

查看分区UUID可以在终端命令输入 sudo blkid
{% highlight vim %}                    
    root@neo:~# sudo blkid
    /dev/sda1: UUID="3802386C0238316C" TYPE="ntfs" 
    /dev/sda2: UUID="02C2CDABC2CDA2F1" TYPE="ntfs" 
    /dev/sda5: UUID="748EA05D8EA01A1E" TYPE="ntfs" 
    /dev/sda6: UUID="F21EAF051EAEC249" TYPE="ntfs" 
    /dev/sda7: UUID="8454092554091B94" TYPE="ntfs" 
    /dev/sda9: UUID="ae39760a-4f3d-492a-95fa-586060fcf3e5" TYPE="swap" 
    /dev/sda8: UUID="e0aeb499-e7b7-4efe-9b6c-8e8883790e96" TYPE="ext4" 
    root@neo:~# 
{% endhighlight %}
然后在你的set=root代码后写上你set root='(hd0,msdos1)' 里面所写分区的UUID并保存在重启.
grub启动界面选windows项,是不是找回你的window项。