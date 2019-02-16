---
title: 丰富你的 hexo博客
date: 2019-02-13 16:06:37
top: 1
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

## 10.博客添加点击爱心效果

[参考博客](https://asdfv1929.github.io/2018/01/26/click-love/)

## 11.hexo next 配置 DaoVoice 实现在线聊天功能

[参考博客](https://hoxis.github.io/hexo-next-daovoice.html)

## 12.网站底部字数统计

- 安装hexo插件，切换到根目录：

```
npm install hexo-wordcount --save
```

- 在`Blog/themes/next/layout/_partials/footer.swig`末尾添加代码：

```javascript
<div class="theme-info">
  <div class="powered-by"></div>
  <span class="post-count">博客全站共{{ totalcount(site) }}字</span>
</div>
```

## 13. 坑点1--全局语言配置

全局配置文件  中关于站点语言配置  language: zh-Hans（我的配置为zh-CN会出问题）

## 14. 坑点2 --百度分享功能实现

```yaml
baidushare:
type: slide
baidushare: true
```

[解决百度分享https无法使用](https://hoxis.github.io/hexo-next-daovoice.html)

## 15.NexT Pisces主题内容区宽度更改

直接在`source/css/_variables/custom.styl`中使用Scheme `Gemini` 的参数即可

```javascript
$main-desktop                   = 75%
$content-desktop                = calc(100% - 252px)
```

## 16 hexo页脚添加访客人数和总访问量

[参考博客](https://www.jianshu.com/p/c311d31265e0)

[不蒜子访问统计官网](http://busuanzi.ibruce.info/)

## 17 hexo 代码高亮问题

在站点的配置文件中，搜索`hightlight`:

```yaml
highlight:
  enable: true
  line_number: true
  auto_detect: true
  tab_replace:
```

文字自动检测默认不启动，所以改成true使其起作用。

再到主题的配置文件：

`highlight_theme: normal`，注释显示有五种显示主题可用，分别是：

- normal
- night
- night eighties
- night blue
- night bright

包裹代码块方式 

> \`\`\`java      代码块      \`\`\`      注意C# 是无效的的  一定要 csharp

## 18 代码拷贝功能实现

[代码块复制功能](https://www.jianshu.com/p/3e9d614c1e77)

