---
layout: post
published: true
title: "DNS Prefetch"
---

-----------------------------------------------------------

#### 1.DNS�Ľ���
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DNS��Domain Name System������ϵͳ��������������Ϊ������IP��ַ�໥ӳ���һ���ֲ�ʽ���ݿ⣬�ܹ�ʹ�û�������ķ��ʻ�������������ȥ��ס�ܹ�������ֱ�Ӷ�ȡ��IP������ͨ�������������յõ�����������Ӧ��IP��ַ�Ĺ��̽�����������������������������DNSЭ��������UDPЭ��֮�ϣ�ʹ�ö˿ں�53����RFC�ĵ���RFC 2181��DNS�й淶˵����RFC 2136��DNS�Ķ�̬���½���˵����RFC 2308��DNS��ѯ�ķ��򻺴����˵�������԰ٶȰٿƣ���DNS�Ĺ�����ʵ��ӳ�䣬����������IP��ַ��ӳ�������֣���̬ӳ�䣬��̬ӳ�䡣������Ϣ�ɰٶȡ�

#### 2.ʲô��DNS Prefetch��
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;����DNSʵ�ֵ���������IP��ӳ�䣬���ͨ����������վ�㣬������DNS������Ŀǰÿ��DNS������ͨ����200ms���¡����DNS������ʱ���⣬һЩ�����ͨ��DNS Prefetch ����߷��ʵ������ԡ� DNS Prefetch ��һ��DNS Ԥ�������������������ҳʱ����������ڼ�����ҳʱ����ҳ�е��������н������棬�������㵥����ǰ��ҳ�е�����ʱ���������DNS�Ľ����������û��ȴ�ʱ�䣬����û����顣

#### 3.DNS Prefetch��ʵ��
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ͨ��meta��ǩ��Ϣ����֪�����, ��ǰҳ��Ҫ��DNSԤ����:
    
    <meta http-equiv="x-dns-prefetch-control" content="on" />
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;��ҳ��head��ǩ��ʹ��link��ǩ��ǿ�ƶ�DNSԤ����: 
    
    <link rel="dns-prefetch" href="http://bdimg.share.baidu.com" />
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;���Ҫ������������Ƿ����������Ԥ����������ͨ��Http header ��x-dns-prefetch-control ���Խ��п��ơ�

#### 4.DNS Prefetchʹ�õĻ���
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;��ҳ���ظ�DNSԤ�����������ظ�DNS��ѯ��������ȻDNSԤ���������������վǰ��ҳ���Ż����飬��Ҳ������վ�����DNS��ѯ��
