---
title: 丰富你的 hexo博客
date: 2019-02-13 16:06:37
tags:
    - 博客
    - hexo
categories: 博客搭建
comments: true
---
{% centerquote %}为自己的hexo博客添加评论系统、统计阅读量、二维码、本地搜索.....{% endcenterquote %}
<!-- more -->

## 前言
Next 主题github上使用人比较多 
试了几种评论系统  Valine最好用（来必力加载太慢）   

## 1. 主题

推荐Next  官方链接:[clik me](http://theme-next.iissnan.com/)
1. 按照官方指导 clone 下来 放在本地博客主题文件夹中 然后修改全局_config.yml文件
2. 主题里面配置选项非常多，在官网里查看

## 2. Leancloud统计文章阅读量

参考博文: [clik me](https://blog.csdn.net/weixin_39345384/article/details/80787998)

## 3. Hexo加上评论系统-Valine

参考博文: [clik me](https://blog.csdn.net/blue_zy/article/details/79071414)

## 4 . 文章末尾添加二维码
利用 NexT 主题自带的wechat_subscriber功能在文章末尾添加网站二维码。 
首先生成你网站的二维码，放到网站根目录下的images文件夹中，然后修改主题配置文件 _config.yml，添加如下内容：

```bash
# Wechat Subscriber
wechat_subscriber:
  enabled: true
  qcode: /images/wuxubj.png
  description: 扫一扫，用手机访问本站
```

## 5. 写博客时添加图片
参考博文: [clik me](https://www.jianshu.com/p/c2ba9533088a)

```bash
 npm install hexo-asset-image --save
```
## 6. 博客添加本地搜索
```bash
npm install hexo-generator-searchdb --save
```
修改主题配置文件_config.yml (一定要先执行上面命令，否则链接会一直转圈)

```bash
local_search:
  enable: true
```

## 7. Hexo博客搭建之引用站内文章

```bash
{% post_link 文章文件名（不要后缀） 文章标题（可选） %}
```

## 8. 如何设置「阅读全文」？

```bash
在文章中使用 <!-- more --> 手动进行截断，Hexo 提供的方式 推荐
```

内置标签设置：[click me](http://theme-next.iissnan.com/tag-plugins.html)

## 9. 取消“文章目录”对标题的自动编号？

打开next主题下的配置文件 修改 `toc：`下配置

```yaml
toc:

  enable: true

  \# Automatically add list number to toc.

  number: false

  \# If true, all words will placed on next lines if header width longer then sidebar width.

  wrap: false
```

## 10. 坑点

全局配置文件  中关于站点语言配置  language: zh-Hans（我的配置为zh-CN会出问题）