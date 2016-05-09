---
title: httpЭ��
date: 2016-05-09 15:45:24
tags: [���,Э��]
---

�����У�����Ϊ�˻�ȡ������Ҫ����Ϣ��Դ��ͨ�������browser���һ��������ַ����ô�����е�ʵ�ֻ�������ô�����أ�
��ʵ�������/������(B/S)�ܹ��ǻ���httpЭ��ģ�����ѧϰ���Э��������������������ϲ�������а�����
����������python��д���������ʱ��ͻ��漰��������Ӧ�룬cookie��session������ѧϰhttp�Ǻ��б�Ҫ�ģ�����

<!--more-->

## ʲô��HTTPЭ��

����Э����ָ�����ͨ����������̨�����֮�����ͨ�������빲ͬ���ص�`�涨�����`�����ı�����Э��(HTTP)��һ��ͨ��Э�飬���������ı��������(HTML)�ĵ���Web���������͵��ͻ��˵������

     ��Ŀǰ����ʹ�õ���HTTP/1.1 �汾
------

## Web������������������������

���������Ǵ���������ڵ�ַ��������URL��Ȼ�����ǾͿ�������ҳ�� ԭ�����������أ�

����ʵ������������URL�����ǵ��������Web������������һ��**Request**, Web�������ӵ�Request����д���������Ӧ��Response��Ȼ���͸�������� ���������**Response**�е�HTML,�������ǾͿ�������ҳ����������ͼ��ʾ

![photo](http://ww4.sinaimg.cn/mw690/006rmJyDgw1f3p5bh4i7dj30l209tjuc.jpg)

�������ǵ�Request �п����Ǿ����˴�������������ŵ���Web�������ġ�

������������ͼ��ʾ

![photo2](http://ww1.sinaimg.cn/mw690/006rmJyDgw1f3p5bhoxd4j30m109p41w.jpg)

�����������������������Ϣ����תվ����ʲô�����أ�

����1. ��߷����ٶȣ� ������Ĵ�����������л��湦�ܡ�

����2. ͻ�����ƣ� Ҳ���Ƿ�ǽ��

����3. ������ݡ�

-------

## URL���
��ʵ��λһ����Դ����Ҫ�ľ���URI�ˣ���URL��URN��URL�������Ӽ���
ͨ��������ϰ��ֱ����URL������URI��

    URI ��Uniform Resource Identifier��ͳһ��Դ��ʶ����
    URL��Uniform Resource Locator��ͳһ��Դ��λ����
    URN��Uniform Resource Name��ͳһ��Դ���ơ�
����URL(Uniform Resource Locator) ��ַ��������һ�������ϵ���Դ��  ������ʽ����

    schema://host[:port#]/path/.../[;url-params][?query-string][#anchor]

����scheme               ָ���Ͳ�ʹ�õ�Э��(���磺http, https, ftp)

����host                   HTTP��������IP��ַ��������

����port#                 HTTP��������Ĭ�϶˿���80����������¶˿ںſ���ʡ�ԡ����ʹ���˱�Ķ˿ڣ�����ָ�������� http://www.cnblogs.com:8080/

����path                   ������Դ��·��

����url-params

����query-string       ���͸�http������������

����anchor-             ê

###��URL ��һ������

    http://www.mywebsite.com/sj/test;id=8079?name=sviergn&x=true#stuff

    Schema: http

    host: www.mywebsite.com

    path: /sj/test

    URL params: id=8079

    Query String: name=sviergn&x=true

    Anchor: stuff
---

## HTTPЭ������״̬��

����httpЭ����`��״̬`�ģ�ͬһ���ͻ��˵����������ϴ�������û�ж�Ӧ��ϵ����http��������˵��������֪����������������ͬһ���ͻ��ˡ� Ϊ�˽��������⣬ Web����������`Cookie`������ά��״̬.
## HTTP��Ϣ�Ľṹ

�����ȿ�`Request`��Ϣ�Ľṹ��Request��Ϣ��Ϊ3���֣���һ���ֽ������У� �ڶ����ֽ�http header, ����������body. header��body֮���и����У� �ṹ����ͼ

![photo3](http://ww3.sinaimg.cn/mw690/006rmJyDgw1f3p5bhx4jkj30by05e3ye.jpg)

������һ���е�Method��ʾ���󷽷�������"POST"��"GET"��  Path-to-resoure��ʾ�������Դ�� Http/version-number ��ʾHTTPЭ��İ汾��

������ʹ�õ���"GET" ������ʱ�� body��Ϊ�յ�

�����������Ǵ򿪲���԰��ҳ��request ����

    GET http://www.cnblogs.com/ HTTP/1.1

    Host: www.cnblogs.com

����������Fiddler ��׽һ������԰��¼��Request Ȼ����������Ľṹ�� ��Inspectors tab����Raw�ķ�ʽ���Կ���������Request����Ϣ��   ����ͼ

![photo4](http://ww1.sinaimg.cn/mw690/006rmJyDgw1f3p5bibqmhj30qu0lk3zl.jpg)
����
���������ٿ�`Response`��Ϣ�Ľṹ�� ��Request��Ϣ�Ľṹ����һ���� ͬ��Ҳ��Ϊ�����֣���һ���ֽ�request line, �ڶ����ֽ�request header������������body. `header��body֮��Ҳ�и�����`��  �ṹ����ͼ

![photo6](http://ww2.sinaimg.cn/mw690/006rmJyDgw1f3p5bj9aeij30by05ejr9.jpg)

����HTTP/version-number��ʾHTTPЭ��İ汾�ţ�  status-code ��message �뿴�½�[״̬����]����ϸ����.

����������Fiddler ��׽һ������԰��ҳ��ResponseȻ����������Ľṹ�� ��Inspectors tab����Raw�ķ�ʽ���Կ���������Response����Ϣ��   ����ͼ

![photo4](http://ww3.sinaimg.cn/mw690/006rmJyDgw1f3p5bjmfbvj30rm0kowft.jpg)

----

## Get��Post����������

����HttpЭ�鶨���˺ܶ�������������ķ��������������4�֣��ֱ���GET,POST,PUT,DELETE. һ��URL��ַ��������һ�������ϵ���Դ����HTTP�е�GET, POST, PUT, DELETE�Ͷ�Ӧ�Ŷ������Դ�Ĳ飬�ģ�����ɾ4�������� ��������ľ���GET��POST�ˡ�GETһ�����ڻ�ȡ/��ѯ��Դ��Ϣ����POSTһ�����ڸ�����Դ��Ϣ.

�������ǿ���GET��POST������

����1. GET�ύ�����ݻ����URL֮����?�ָ�URL�ʹ������ݣ�����֮����&��������EditPosts.aspx?name=test1&id=123456.  POST�����ǰ��ύ�����ݷ���HTTP����Body��.

����2. GET�ύ�����ݴ�С�����ƣ���Ϊ�������URL�ĳ��������ƣ�����POST�����ύ������û������.

����3. GET��ʽ��Ҫʹ��Request.QueryString��ȡ�ñ�����ֵ����POST��ʽͨ��Request.Form����ȡ������ֵ��

����4. GET��ʽ�ύ���ݣ��������ȫ���⣬����һ����¼ҳ�棬ͨ��GET��ʽ�ύ����ʱ���û��������뽫������URL�ϣ����ҳ����Ա�������������˿��Է�����̨�������Ϳ��Դ���ʷ��¼��ø��û����˺ź�����.




----------------

><span style="font-size:12px">���ı���: <a href="{{ permalink }}">{{ title }}</a>
>��������: <a href="http://tgsx.github.io/">�����</a>  
>���Э��: <img alt="֪ʶ�������Э��" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png" /><a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">?����-������-��ͬ��ʽ���� 4.0</a></span>