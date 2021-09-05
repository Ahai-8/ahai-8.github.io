---
layout: post
---
## jekyll 简介

jekyll 可以批量生成静态网页，非常适用于个人博客。

而且 Gihub Pages 内置支持 jekyll，用户无需下载运行 jekyll，直接在 repo 里存入源文件，网站就可以在 Github 服务器上自动生成。

这个博客 [阿海的呓语](https://ahai-8.github.io/) 就是用 jekyll 生成，源文件存储在 [Ahai/ahai.github.io](https://github.com/Ahai-8/ahai-8.github.io) ，喜欢这个主题可以直接 fork 过去改。

## 最基本的 jekyll 文件结构

```
|__ _includes
|   |__ controlbar.html
|__ _layouts
|   |__ default.html
|   |__ index.html
|   |__ post.html
|__ _posts
|   |__ post1.md
|   |__ post2.md
|   |__ post3.md
|__ _config.yml
|__ styles.css
|__ index.md
```

_includes：模块文件夹，用 `include` 语句嵌入其他模板（后文详细介绍）。

_layouts：模板文件夹，存放生成 html 时套用的模板。

_posts：博文文件夹。

_config.yml：网站属性设置。

style.css：网站的样式表，不是一篇文章能讲清楚的，请找其他教程，或者直接复制修改别人做好的表。

index.md：网站首页。

## 变量、语句和过滤器

### 变量

变量使用双大括号包括：`{\{ variable }\}`

### 语句

语句使用大括号和百分号包括起来：`{\% statement %\}`

最常见的 `include`，选择语句 `if..else..`，迭代器 `for .. in ..`

### 过滤器

双大括号包括，竖线前填处理内容，竖线后填处理方法：`{\{ content | method }\}`
```

## 两种嵌套

### 1. include

通过 `include` 语句可以在模板中引入模块。

比如，在 _inludes 文件夹下新建 controlbar.html 文件，写入以下内容：

```
<div>
    <a href="{\{ '/' }\}">返回</a>
</div>
```

而后，在模板 post.html 中使用 `include` 语句：

```
{\% include controlbar.html %\}
<p>正文内容</p>
{\% include controlbar.html %\}
```

### 2. layout 与 content

`{\{ content }\}`


## 发布文章

标签分类，搜索——可以，但没必要。
