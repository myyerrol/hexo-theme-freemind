# hexo-theme-freemind

![screenshots](http://wzpan.github.io/hexo-theme-freemind-blog/images/screenshots.png)

Freemind aims at fully taking advantages of Bootstrap.

- [Demo](http://hahack.com/hexo-theme-freemind-blog/)
- [Q&A](http://hahack.com/hexo-theme-freemind-blog/2014/03/16/qna/)
- [Tag Plugins](http://hahack.com/hexo-theme-freemind-blog/2014/03/16/tag-plugins/)
- [Color Themes](http://hahack.com/hexo-theme-freemind-blog/2016/01/30/color-themes/)
- [README in Chinese](./README_zh-cn.md)

## Requirements

- Hexo >= 3.0
- [hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap) >= 0.0.8 (optional)
- [hexo-generator-search](https://github.com/paichyperiondev/hexo-generator-search) (optional)
- [hexo-wordcount](https://github.com/willin/hexo-wordcount) (optional)

## Features

- **Bootstrap** - Get the power of Twitter Bootstrap with minimal hassle.
- **2 columns layout** - The most traditional and comfortable blog layout.
- **Tag plugins** - Luxuriant Bootstrap tag plugins, provided by wzpan another project [hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap). Including:
  - textcolor - A paragraph of text with specified color.
  - button - A button with target links, text and specified color.
  - label - A label with text and specified color.
  - badge - A badge with text.
  - alert - Alert messages with text and specified color.
- **Local Search Engine** - A built-in local search engine, with the help of wzpan another project [hexo-generator-search](https://github.com/paichyperiondev/hexo-generator-search).
- **Color Themes** - Luxuriant Bootswatch color themes for choice.
- **Pin to top** - Able to pin any article to the top of the first index page.
- **Built-in Comment System** - A comment system based on wzpan another project [comment.js](https://github.com/wzpan/comment.js).
- **Word Count** - Implement the word count of articles and  prediction of minutes to reading.

![color themes](http://wzpan.github.io/hexo-theme-freemind-blog/images/color-themes.gif)

## Install

1) Install theme:

``` sh
$ git clone https://github.com/myyerrol/hexo-theme-freemind.git themes/freemind
```

2) Install [hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap) (*optional*):

``` sh
$ npm install hexo-tag-bootstrap --save
```

3) Install [hexo-generator-search](https://github.com/paichyperiondev/hexo-generator-search) (*optional*):

``` sh
$ npm install hexo-generator-search --save
```

4) Install [hexo-wordcount](https://github.com/willin/hexo-wordcount) (*optional*):

```sh
$ npm install hexo-wordcount --save
```

If **node.js <= 7.6.0**, please use following commands:

```sh
$ npm install hexo-wordcount@2 --save
```

5) Create pages

Freemind offers you the customized Categories, Tags and About pages. But you need to manually create these page at your `source` folder.

For example, to create a `Categories` page, you may create a `index.html` file at `source/categories/` folder with the following contents:

```
title: Categories
layout: categories
---
```

Tags and About pages are created in a similar way, except that the layouts are `tags` and `page` respectively.

Alternatively you can create About page using the following command:

``` sh
$ hexo new page about
```

Note that only About page can be created in that way.

## Enable

Modify `theme` setting in your `_config.yml` to `freemind`.

## Update

``` sh
$ cd themes/freemind
$ git pull
```

## Configuration

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

- **slogan** - Slogan display at the index page.
- **theme** - Which color theme to use.
- **inverse** - Whether to use inverse navbar color.
- **menu** - Navigation menu.
- **links** - Reference links at the links widget.
- **widgets** - Widgets displaying in sidebar.
- **rss** - RSS link.
- **fancybox** - Enable [Fancybox](http://fancyapps.com/fancybox/).
- **duoshuo_shortname** - DuoShuo ID, if you prefer to use duoshuo instead of Disqus.
- **analytics** - Analytics ID. Supports both Google Analytics and Baidu Tongji.
- **swiftype_key** - Swifttype key to enable local searching. Leave it blank or comment this line if you want to use build-in local search engine.
- **bdshare** - Baidu share button at the bottom of article.
- **jiathis** - Jiathis share button at the bottom of article.
- **comment_js** - Settings for [comment.js](http://github.com/wzpan/comment.js):
  - `type`: The site as the backend. Currently supports Github and OSChina.
  - `user`: Your site's user account.
  - `repo`: Your repo for comment issue tracking.
  - `client_id`(optional but recommended): The client id of your OAuth App.
  - `client_secret`(optional but recommended): The client secret of your OAuth App.
  - `count`(optional): The maximize length of the comment list. Default value is 5.

If you prefer to use disqus, the setting of disqus should be placed at your **root** `_config.yml`:

```
# Disqus
disqus_shortname:
```

## Front-Matter

There are some new front-matter settings in Freemind that you can use to decorate your articles.

- **description** - A short description about the articles that will be display at the top of the post.
- **feature** - Sets a feature image that will be show at the index page.
- **toc** - Renders a table of contents.
- **top** - Pin the article to top if it is set to `true`.
- **issue_id** - Comment.js `issue_id` for explicitly point out which Github issue should be connect to your post. For most situations you don't need it unless the post doesn't link to the issue you want.

For example:

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

## License

This theme is provided under [MIT License](http://opensource.org/licenses/MIT).

## People Using Freemind

See [Examples](https://github.com/wzpan/freemind/wiki/Examples).

## Credits

- The theme is built based on [Twitter-Bootstrap 3.1.1](getbootstrap.com/3.1.1/);
- The beautiful icons are from [Font Awesome](http://fortawesome.github.io/Font-Awesome/icons/).
- Build-in color themes are from [Bootswatch](bootswatch.com).
