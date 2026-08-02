---
title: 2024最新Hexo＋butterfly添加和风天气插件
date: 2024-01-28 13:00:00
tags:
  - Hexo
categories:
  - 技术
---

## 前言

看到网上有很多butterfly主题添加天气插件的教程，不过都是老版本了，最新版本的butterfly主题代码相比之前有很多的改动，再加上添加插件的过程因为一些小问题导致添加不成功，所以本人决定将出一个最新的保姆级教程。本篇文章记录将介绍【hexo：7.0.0 butterfly：4.12.0】版本添加天气插件的教程以及过程中可能出现的问题。

### 效果展示

![c1](/images/pages/c1.png)

![c2](/images/pages/c2.png)

## 详细教程

1.打开和风天气创建天气[链接](https://widget.qweather.com/create-simple?token=b737d157078546a4a5031ec1f8cce6a1&lang=zh)（没有注册账号的要先注册账号，登录之后再进链接，刷新一下就可以创建了）

![c3](/images/pages/c3.png)

这里名称随意，除了底部的固定在浏览器中选择**否**，其他参数你可以随意配置，个人建议天气图标小2个像素，背景透明，两个水平居中。（后面生成后你可以根据实际微调）一键生成代码。

![c4](/images/pages/c4.png)

2.打开你的博客目录-themes-butterfly-source-js中创建一个weather.js文件，将上面红色框内的代码粘贴进去，注意对齐。

![c5](/images/pages/c5.png)

3.在主题配置的文件`_config.butterfly.yml`中找到`inject`的`bottom`处引入下面两个JS文件,其实就是一个插件样式和一个调用官方的接口。

```js
- <script src="https://widget.qweather.net/simple/static/js/he-simple-common.js?v=2.0"></script>
- <script src="/js/weather.js"></script>
```

![c6](/images/pages/c6.png)

**注意对齐**

4.打开你的博客目录-themes-butterfly-layout-header-nav.pug，将#he-plugin-simple粘贴进去，注意对齐上面的span标签。

```markdown
#he-plugin-simple
```

![c7](/images/pages/c7.png)

**sty和其他不用改。**

## 结尾

保存，hexo c && hexo g && hexo s就能看到效果，可以在weather.js微调一下位置和样式，满意的话hexo d

## 可能存在的问题

### 修改主题样式上传博客后没有任何变化？

解决办法:

①到你的butterfly主题文件夹，把里面的.git文件夹删除即可（你的所有博客文件中只能存在一个.git，就是你的博客主目录的，如果主题中也有.git文件的话，里面的文件是不会上传到github的，非常重要的一点！困扰了作者好几天mmp）

②检查博客根目录的\_config.yml中的deploy，“:”后面要有一个空格。

③删除博客根目录的.deploy\_git文件。（不用担心这个，hexo g会重新生成的）

### 远程仓库没有变化？

解决办法:

git bash中执行下面代码，一个一个来

```plaintext
npm un hexo-deployer-git
npm i hexojs/hexo-deployer-git
git rm --cache themes/butterfly（第三条非必要，根据实际情况更改路径或者不执行，意思就是删掉缓存）
```

最后记住：如果有问题可以去github上hexo的issues上查找解决办法或者提问[直达链接](https://github.com/hexojs/hexo/issues)

### 完结撒花~

![c8](/images/pages/c8.gif)
