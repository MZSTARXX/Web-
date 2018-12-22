# 了解ＨＴＭＬ

为了开始构建网站，我们需要了解哪些HTML元素最适合用于显示不同类型的内容。了解元素在网页上的可视化显示方式以及不同元素在语义上的含义也很重要。

## 没有语意的两个元素

**＜ｄｉｖ＞**和**＜ｓｐａｎ＞**在ＨＴＭＬ中并没有什么实际的意义。在网页设计时，只是作为一种容器来使用。`<div>`是块级元素，通常用于标识大量内容，有助于构建网页的布局和设计。`<span>`是通常用于在块级元素内识别文本的较小的分组的行内元素。

## 块级元素和内联元素

块级元素从一个新行开始，将一个层叠在另一个的顶部，并占用任何可用的宽度。块级元素可以彼此嵌套，并且可以包含内联级元素。我们最常见的是用于较大内容的块级元素，例如段落。

内联级元素不会在新行上开始。它们落入文档的正常流程中，一个接一个地排列，并且只保持其内容的宽度。内联级元素可以彼此嵌套;但是，它们无法包装块级元素。我们通常会看到具有较小内容的内联级元素，例如几个单词。

## 注释

在ＨＴＭＬ和ＣＳＳ中都有 用来注释的方式。

ＨＴＭＬ中用＜！－－．．．．－－！＞来注释。

ＣＳＳ中用`/*。。。。。。*/`来注释。

## 标题

标题是块级元素，以及他们在六个不同的排名，`<h1>`通过`<h6>`。标题有助于快速分解内容并建立层次结构，它们是用户阅读页面的关键标识符。它们还可以帮助搜索引擎索引和确定页面上的内容。

标题应按照与页面内容相关的顺序使用。页面或部分的主标题应被标记了一个`<h1>`元件，以及随后的标题应该使用`<h2>`，`<h3>`，`<h4>`，`<h5>`，和`<h6>`元件是必要的。

## 段落

用**＜ｐ＞**来定义段落。

是段落中的内容变粗可以使用**＜ｓｔｒｏｎｇ＞**

```
例如：＜ｓｔｏｒｎｇ＞．．．．．．＜／ｓｔｒｏｎｇ＞
```

强调文本中的内容（变成斜体）可以使用＜ｅｍ＞

```
例如：＜ｅｍ＞．．．．．＜／ｅｍ＞
```


