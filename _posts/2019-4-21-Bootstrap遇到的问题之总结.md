---
layout:     post   				    # 使用的布局（不需要改）
title:      bootStrap遇到的问题之总结 				# 标题
subtitle:    bootStrap #副标题
date:       2019/4/21 				# 时间
author:     wdy						# 作者
header-img: #img/post-bg-2015.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - bootstrap
---
## 关于html文件引入bootStrap顺序

最近又一次遇到了bootstrap上以前犯过的问题，今天总结一下，争取以后不再犯

bootStrap官网这样写的
>使用 BootCDN 提供的免费 CDN 加速服务（同时支持 http 和 https 协议）
  Bootstrap 中文网 为 Bootstrap 专门构建了免费的 CDN 加速服务，访问速度更快、加速效果更明显、没有速度和带宽限制、永久免费。BootCDN 还对大量的前端开源工具库提供了 CDN 加速服务，请进入BootCDN 主页查看更多可用的工具库。
  
 ``<!-- 最新版本的 Bootstrap 核心 CSS 文件 --><link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@3.3.7/dist/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">``
 
 `` <!-- 可选的 Bootstrap 主题文件（一般不用引入） --> <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@3.3.7/dist/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">``
 
``<!-- 最新的 Bootstrap 核心 JavaScript 文件 --><script src="https://cdn.jsdelivr.net/npm/bootstrap@3.3.7/dist/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>``



这里引入bootstrap的js 文件需要在jquery文件引入之后，因为部分功能是由jquery的方法实现的。
如果先调用就会引起部分功能失灵，这个东西编译器不会报错，文件网页也是正常接收。

不注意又以为我代码哪里冲突了。。。

##### 总结：由于bootstrap的js文件部分功能的实现前提是jquery功能的基础上实现的，所以要先引用jquery的文件。ㄟ( ▔, ▔ )ㄏ。。。