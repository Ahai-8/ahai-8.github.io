---
layout: post
---
## jekyll 简介

jekyll 可以批量生成静态网页，非常适用于个人博客。

而且 Gihub Pages 内置支持 jekyll，用户无需下载运行 jekyll，直接在 repo 里存入源文件，网站就可以在 Github 服务器上自动生成。

这个博客 [阿海的呓语](https://ahai-8.github.io/) 就是用 jekyll 生成，如果文章没有看懂，可以翻翻存储在 [Ahai/ahai.github.io](https://github.com/Ahai-8/ahai-8.github.io) 的源文件。

>接下来的阅读过程中，如果喊出“我不想努力了”，可通过以下途径解决：
>
>1. 直接把仓库 fork 到自己的账号，或者下载解压 zip；
>2. 修改 index.md 这个文件（首页的内容），修改 _config 文件夹里的 `title` 后面的属性为自己的博客名；
>3. 清空 _post 文件夹，把自己写的 markdown 博文放进去，每篇文章记得加以下前缀：
>    ```
>    ---
>    layout: post
>    ---
>    ```
>4. 坐一会，喝口水，给自己（的仓库）一点时间和空间；

## 最简单的 jekyll 源文件结构

```
|__ _includes           # 模块文件夹
|   |__ controlbar.html
|__ _layouts            # 模板文件夹
|   |__ default.html
|   |__ index.html
|   |__ post.html
|__ _posts              # 文章文件夹
|   |__ post1.md
|   |__ post2.md
|   |__ post3.md
|__ _config.yml         # 网站属性
|__ styles.css          # 样式表
|__ index.md            # 网站首页
```

## 变量、语句和过滤器

### 变量

变量使用双大括号包括：
```
{% raw %}
{{ variable }}
{% endraw %}
```

### 语句

语句使用大括号和百分号包括起来

```
{% raw %}
{% statement %}
{% endraw %}
```

最常见的 `include`，选择语句 `if..else..`，迭代器 `for .. in ..`

### 过滤器

双大括号包括，竖线前填处理内容，竖线后填处理方法：

```
{% raw %}
{{ content | method }}
{% endraw %}
```

## 两种嵌套

### 1. include

通过 `include` 语句可以在模板中引入模块。

比如，在 _inludes 文件夹下新建 controlbar.html 文件，写入以下内容：

```
{% raw %}
<div>
    <a href="{{ "/" }}">返回</a>
</div>
{% endraw %}
```

而后，在模板 post.html 中使用 `include` 语句：

```
{% raw %}
{% include controlbar.html %}
<p>正文内容</p>
{% include controlbar.html %}
{% endraw %}
```

### 2. layout 与 content

```
{% raw %}
{{ content }}
{% endraw %}
```

## 发布文章

标签分类，搜索——可以，但没必要。
