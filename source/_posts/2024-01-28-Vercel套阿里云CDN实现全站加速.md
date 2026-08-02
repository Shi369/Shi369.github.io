---
title: Vercel套阿里云CDN实现全站加速
date: 2024-02-05 13:00:00
updated: 2024-02-05 13:00:00
cover: https://img.watech.top/blog/202402182245156.webp
tags:
  - Hexo
categories:
  - 技术
---

## 前言

众所周知，Vercel能免费托管并且全球加速我们的网站，虽然在国外某些国家可以达到1ms秒开，但是在国内的访问速度懂得都懂，有时候速度快，有时候直接卡在加载页面，让人火冒三丈。嗯…只能它说可以用。

今天看到一个大佬的文章，跟着操作成功实现了Vercel的cdn套阿里的cdn，不得不佩服这位大佬，让我领悟到只要能想到，就没有做不到的，本篇文章记录了实现的过程。

## 效果预览

### 添加前测速

![image-20240205144202676-1707134073969-1](/images/pages/image-20240205144202676-1707134073969-1.png)

### 添加后测速

![image-20240205185926567](/images/pages/image-20240205185926567.png)

## 详细教程

首先Vercel里面的设置不需要动，如下图所示，推荐设置watech.top为308永久定向指向 [www.watech.top](http://www.watech.top/) ，**我们需要在阿里云加速的域名也是 [www.watech.top](http://www.watech.top/)** ，如下图所示。

![image-20240205191336156](/images/pages/image-20240205191336156.png)

之后在阿里云的全站加速中添加 [www.watech.top](http://www.watech.top/) 域名，设置CNAME，（具体配置下面会讲）如下图所示：

![image-20240205192030615](/images/pages/image-20240205192030615.png)

新增源站，源站域名填写cname.vercel.com或者cname-china.vercel.com，然后下面选择443端口。

![image-20240205192131229](/images/pages/image-20240205192131229.png)

回源Host填写加速域名

![image-20240205192317502](/images/pages/image-20240205192317502.png)

最后配置一下ssl证书就ok了，如下图所示

![image-20240205192433899](/images/pages/image-20240205192433899.png)

## 原理剖析

![rt5](/images/pages/rt5.jpg)

## 修正

    次日发现偶尔还是会卡顿，尤其是在夜间，流量的高峰期；ping了网站之后，仔细看了下，有大概才3成的国内CDN节点，7成的都是Vercel位于美国的节点，加速了，但效果不佳！一番苦找，恍然大悟，CDN1和CDN2共同指向了Vercel的cname地址，导致了两个CDN和用户抢分发节点加速！

    究极解决办法：停用加速域名 [www.watech.top](http://www.watech.top/) 的cname解析，再ping一次，此时CDN全部变为国内~（个人理解：加速域名回源到了加速域名的cname解析地址，就相当于CDN1为加速域名进行了Vercel官方的cname解析）

    此外，发现使用jsdeliver加速的图片资源，显示加载非常慢，如同龟速，上传到github后直接引用链接，恢复正常。这让我想起来一句话，cdn套cdn可能会让你的网站速度变得越来越慢……

    最后QQ、微信、各大浏览器打开本站秒开啦~
