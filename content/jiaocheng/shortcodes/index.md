---
title: 使用Markdown、LaTeX和Shortcodes编写内容
date: 2023-07-04
authors:
  - admin
  - Love Astro

tags:
  - Linux
  - sherpa

categories:
  - html
  - Wowchemy
---
&emsp;&emsp;可以使用Markdown、LaTeX math和Shortcodes在Wowchemy中编写丰富的内容。本文概述了最常见的格式化选项，包括Wowchemy独有的功能。
<!--more-->
## 一、副标题
&emsp;&emsp;在页面标题、标题1之后，我们可以在页面正文中设置子标题的格式：
```markdown
## Heading 2
### Heading 3
#### Heading 4
```
## 二、强调
### 1. 粗体，斜体，划线
&emsp;&emsp;斜体加下划线：
```markdown
Italics with _underscores_.

Bold with **asterisks**.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough with ~~two tildes~~.
```
&emsp;&emsp;斜体加下划线；加粗加上星号；用星号和下划线组合强调；划两个波浪。
### 2. 文字颜色
&emsp;&emsp;将样式为{style="color: red"}的HTML color属性添加到Markdown块后的行。例如，将一段涂成红色：
```markdown
Red colored text
{style="color: red"}
```
Red colored text
{style="color: red"}

## 三、块引用
```markdown
> This is a blockquote.
```
> This is a blockquote.

## 四、高光引用
```markdown
This is a {{< hl >}}highlighted quote{{< /hl >}}.
```
## 五、列表
### 1. 有序列表
```markdown
1. First item
   1. A sub-item
2. Another item
```
1. First item
   1. A sub-item
2. Another item
### 2. 无序列表
```markdown
- First item
  - A sub-item
- Another item
```
- First item
  - A sub-item
- Another item

## 六、待办事项
通过使用标准Markdown语法，可以在Wowchemy中编写待办事项列表
```markdown
- [x] Write math example
  - [x] Write diagram example
- [ ] Do something else
```
上面这个例子的输出为；则输出为

- [x] Write math example
  - [x] Write diagram example
- [ ] Do something else

## 七、切换列表
向页面添加切换列表，以便在单击切换按钮后显示文本，例如问题的答案。有用的常见问题，剧透，或隐藏答案时，教学在线课程。
```markdown
{{< spoiler text="Click to view the spoiler" >}}
You found me!
{{< /spoiler >}}
```
上面这个例子的输出为；则输出为
{{< spoiler text="Click to view the spoiler" >}}
You found me!
{{< /spoiler >}}

## 八、友情链接
### 1. 网页链接
```markdown
[I'm an external link](https://www.google.com)
[A post]({{< relref "/post/my-page-name" >}})
[A publication]({{< relref "/publication/my-page-name" >}})
[A project]({{< relref "/project/my-page-name" >}})
[A relative link from one post to another post]({{< relref "../my-page-name" >}})
[Scroll down to a page section with heading *Hi*](#hi)
```

上面这个例子的输出为；则输出为

[I'm an external link](https://www.google.com)
[A post]({{< relref "/post/my-page-name" >}})
[A publication]({{< relref "/publication/my-page-name" >}})
[A project]({{< relref "/project/my-page-name" >}})
[A relative link from one post to another post]({{< relref "../my-page-name" >}})
[Scroll down to a page section with heading *Hi*](#hi)

还可以在除Widget Pages(主页)之外的任何页面的页眉中创建按钮链接。

### 2. 链接到文件

可以在除Widget Pages(主页)之外的任何页面的页头中创建指向文件的按钮链接。另外，要链接到内容**正文**中的文件，例如pdf，请将文件放在`static/uploads/`文件夹中，然后使用以下表单链接到它：
```markdown
{{% staticref "uploads/cv.pdf" "newtab" %}}Download my CV{{% /staticref %}}
```
`staticref`的可选参数`"newtab"`将导致链接在新选项卡中打开。
上面这个例子的输出为；则输出为

{{% staticref "uploads/cv.pdf" "newtab" %}}Download my CV{{% /staticref %}}

### 3. 引用
要引用页面或出版物，可以使用引用短代码，引用你创建的文件夹和页面名称：
```markdown
{{< cite page="/publication/preprint" view="citation" >}}
```
其中`view`对应于整个Wowchemy中使用的可用列表视图之一：

- Stream
- Compact
- Card
- Citation

传统的学术引文，通过`params.yaml`中的`citation_style`设置进行配置，如果不指定视图，则默认为`Compact`视图。

### 4. 目录
目录可以帮助用户浏览冗长的页面。粘贴`{{< toc >}}`短代码在您希望的任意页面中显示目录。您可能还希望考虑使用`book layout`，它在大屏幕的右侧栏中显示内置的目录。

在使用`book layout`时，您可能仍然希望添加一个页内目录，该目录仅在隐藏右侧栏时显示。您可以使用`{{< toc hide on="xl" >}}`来完成此操作。
### 5. 脚注
```markdown
I have more [^1] to say.

[^1]: Footnote example.
```
上面这个例子的输出为；则输出为

I have more [^1] to say.

[^1]: Footnote example.

### 6. 图片
要交叉引用图形，请为其提供ID，例如，`{{< figure src="image.jpg" id="wowchemy" >}}`。 现在可以通过表单中的链接交叉引用该图`[A Figure](#figure-wowchemy)`。

### 7. 标签和类别
使用`{{< list tags >}}`提供链接标签的列表，或者使用`{{< list categories >}}`提供链接类别的列表。


