---
title: 使用Markdown、LaTeX和Shortcodes编写内容
date: 2023-07-04
authors:
  - admin
  - Love Astro

tags:
  - Markdown
  - LaTeX
  - Shortcodes

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
   1.1 A sub-item
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

### 6. 图片
&emsp;&emsp;要交叉引用图形，请为其提供ID，例如，`{{< figure src="image.jpg" id="wowchemy" >}}`。 现在可以通过表单中的链接交叉引用该图`[A Figure](#figure-wowchemy)`。

### 7. 标签和类别
&emsp;&emsp;使用`{{< list tags >}}`提供链接标签的列表，或者使用`{{< list categories >}}`提供链接类别的列表。




