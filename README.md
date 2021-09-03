# 边建边写

## 文件结构

`_congfig.yml`，配置文件

`_includes`，html 格式的小模块，用标签 `{% include file.html %}` 包含到其他文件

`_layouts`，布局模板

`_posts`，文章文件夹

`assets`，自己建的，一个项目怎么能没有 assets 文件夹？（doge

Doc 里提到但我没创建的：

`_sites`，生成的 html 储存位置，直接上 github page 就不用。

`_drafts`，草稿文件夹，鸡肋，不加。


## Liquid 模板语言

三大主要组件：

- Object：输出预定义的变量到页面，用 `{{` 和 `}}` 包括。
- Tags：逻辑和控制语句，用 `{%` 和 `%}` 包括。
- Filters：改变 Liquid 对象的输出，例如 `{{ "Hello World!" | downcase }}` 会输出小写的 hello world！


## Front Matter

YAML 的又一应用，设置页面变量。
- 
- 
## layout

布局，在 markdown 文件的 front matter 里写上要应用的布局，生成网页时就会套上相应的布局模板。

## include

用来写一些可以复用的网页组件，可以套到 layout 里。

## .yml

在 yml 文件里可以设置对象（比如这个站点 `site`）的属性，然后可以在 object 组件里调用。

`_config.yml`里设置的为站点属性，使用 `site.name` 调用。

在`_data`文件夹下设置的属性通过 `site.data.name` 调用。


