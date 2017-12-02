# hexo-theme-freemind

![screenshots](http://wzpan.github.io/hexo-theme-freemind-blog/images/screenshots.png)

Freemind的目标是尽可能出发挥Bootstrap的全部优势。

- [演示](http://hahack.com/hexo-theme-freemind-blog/)
- [问题和回答](http://hahack.com/hexo-theme-freemind-blog/2014/03/16/qna/)
- [标签插件](http://hahack.com/hexo-theme-freemind-blog/2014/03/16/tag-plugins/)
- [颜色主题](http://hahack.com/hexo-theme-freemind-blog/2016/01/30/color-themes/)

## 需要

- Hexo >= 3.0
- [hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap) >= 0.0.8（可选）
- [hexo-generator-search](https://github.com/paichyperiondev/hexo-generator-search)（可选）
- [hexo-wordcount](https://github.com/willin/hexo-wordcount)（可选）

## 特点

- **Bootstrap** - 基于Bootstrap 3.1.1。
- **标签插件** - 专门编写了一系列的Bootstrap tag plugins，以最大程度的发挥 Bootstrap的威力。包括：
  - textcolor - 插入一段带有特殊颜色标记的文本。
  - button - 插入一个按钮，并允许为其指定超链接、文本及颜色。
  - label - 插入一个标签，并为其指定文本和样式。
  - badge - 插入一个徽章，并为其指定文本。
  - alert - 插入一段警报文本信息，并为其指定样式。
- **本地搜索** - 自带一个 本地搜索引擎，基于wzpan的另一个项目[hexo-generator-search](https://github.com/paichyperiondev/hexo-generator-search)。
- **颜色主题** - 内置多套颜色主题。总有一套符合你的口味。
- **文章置顶** - 将重要文章置于首页顶部。
- **内置评论系统** - 内置的评论系统，基于wzpan的另一个项目[comment.js](https://github.com/wzpan/comment.js)。
- **字数统计** - 实现文章字数统计和阅读时长预测。

![color themes](http://wzpan.github.io/hexo-theme-freemind-blog/images/color-themes.gif)

## 安装

1) 安装主题：

``` sh
$ git clone https://github.com/myyerrol/hexo-theme-freemind.git themes/freemind
```

2) 安装[hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap)（*可选*）：

``` sh
$ npm install hexo-tag-bootstrap --save
```

3) 安装[hexo-generator-search](https://github.com/paichyperiondev/hexo-generator-search)（*可选*）：

``` sh
$ npm install hexo-generator-search --save
```

4) 安装[hexo-wordcount](https://github.com/willin/hexo-wordcount)（*可选*）：

```sh
$ npm install hexo-wordcount --save
```

如果node.js的版本小于7.6.0，请使用下面的命令：

```sh
$ npm install hexo-wordcount@2 --save
```

5) 创建页面

Freemind预先定义了Categories（分类）、Tags（标签）和About（关于）页面，要使用它们，你需要先在你的博客的`source`目录中添加相应页面。

例如，要创建`Categories`页面，你可以在`source/categories/`下创建一个`index.html`文件，内容如下：

```
title: Categories
layout: categories
---
```
Tags页面和About页面与此类似，不同的是layout分别为`tags`和`page`。

另外，你可以使用下面的命令创建About页面：

``` sh
$ hexo new page about
```
记住只有About页面可以使用上面的方法进行创建。

## 启用

修改`_config.yml`文件里的`theme`选项为`freemind`即可。

## 更新

``` sh
$ cd themes/freemind
$ git pull
```

## 配置

```
slogan: xxx.

theme: bootstrap
inverse: true

menu:
  - title: Archives
    url: archives
    intro: All the articles.
    icon: fa fa-archive
  - title: Categories
    url: categories
    intro: All the categories.
    icon: fa fa-folder
  - title: Tags
    url: tags
    intro: All the tags.
    icon: fa fa-tags
  - title: About
    url: about
    intro: About me.
    icon: fa fa-user

links:
  - title: xxx
    url: xxx
    intro: xxx.
    icon: fa fa-xxx

widgets:
- search
- recent_comments
- category
- tagcloud
- recent_posts
- links

rss:
favicon:
fancybox: true
duoshuo_shortname:

# Analytics
google_analytics:
  enable: false
  siteid:
baidu_tongji:
  enable: false
  siteid:

# Search
swiftype_key:

# Share button
bdshare: false
jiathis: false

# Built-in comment system
comment_js:
  type: "github"
  user: "your-account"
  repo: "your-repo"
  client_id: "xxxxxx"
  client_secret: "xxxxxx"
  count: 5
```

- **slogan** - 修改显示在博客首页的个性签名。
- **theme** - 要使用的颜色主题。
- **inverse** - 是否反正颜色。
- **menu** - 导航菜单。
- **links** - 修改links小挂件的推荐链接。
- **widgets** - 在博客边栏显示的挂件列表。
- **rss** - RSS链接。
- **fancybox** - 是否启用[Fancybox](http://fancyapps.com/fancybox/)
- **duoshuo_shortname** - 多说ID，如果希望使用多说取代Disqus做评论系统。
- **analytics** -  统计ID，支持Google Analytics和百度统计。
- **swiftype_key** - Swifttype是站内搜索的key。如果希望使用内置的搜索引擎，则可以保留为空，而不去配置它。
- **bdshare** - 百度分享按钮。
- **jiathis** - Jiathis分享按钮。
- **comment_js** - [comment.js](http://github.com/wzpan/comment.js)的配置：
  - `type`：要作为后端的站点。目前支持Github和OSChina。
  - `user`：您的Github用户名。
  - `repo`：您用作评论后端的仓库名。
  - `client_id`（可选但建议）：您注册的OAuth App的client id。
  - `client_secret`（可选但建议）：您注册的OAuth App的client secret。
  - `count`（可选）：列表的最大长度，默认值是5。

如果希望使用disqus，则应该在站点的**根**`_config.yml`中设置：

```
# Disqus
disqus_shortname:
```

## Front-Matter

Freemind主题额外提供了一些新的front-matter的选项，利用这些选项可以更好的装饰你的文章：

- **description** - 在文章顶部插入一段简短的摘要信息。
- **feature** - 为文章添加一张feature图片，这张图片将展示在主页的文章列表中。
- **toc** - 生成文章目录。
- **top** - 是否要将本文置顶。
- **issue_id** - comment.js的`issue_id`，用于显式地指定Github上的哪个issue与本文相对应。通常情况下你并不需要手动设置这个，因为comment.js会根据文章标题自动寻找匹配的issue，当文章没有和你要的issue对应的时候你才需要设置它。

示例：

```
title: Tag Plugins
date: 2014-03-16 10:17:16
tags: plugins
categories: Docs
description: Introduce tag plugins in freemind.
feature: images/tag-plugins/plugins.jpg
toc: true
---
```

## 协议

该主题发布在[MIT License](http://opensource.org/licenses/MIT)下。


## 示例

请看[Examples](https://github.com/wzpan/freemind/wiki/Examples)。

## 参考

- 主题基于[Twitter-Bootstrap 3.1.1](getbootstrap.com/3.1.1/)进行构建的。
- 漂亮的图表来源于[Font Awesome](http://fortawesome.github.io/Font-Awesome/icons/)。
- 内置的颜色主题来源于[Bootswatch](bootswatch.com)。
