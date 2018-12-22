# 使用排版

## 一、Typeface 与 Font

**typeface：**就是我们所看到的。它是文本的外观、感觉和阅读的艺术印象。

**font：**font是包含typeface的文件。使用font的计算机上允许计算机访问的typeface。

## 二、向文本添加颜色

构建网站时要做出的第一个决定是选择要使用的主要字体和文本颜色。设置文本颜色所需的唯一属性是color属性。该color属性接受一种颜色值，但有许多不同的格式。

```
例：html {color: #555;}
```

## 三、更改字体属性

CSS提供了许多不同的属性来编辑页面上文本的外观。这些属性分为两类：基于字体的属性和基于文本的属性。大多数这些属性将以**font-\***或中的任何一个开头**text-\***。

### 1、基于字体的属性

#### 字体系列

font-family属性用于声明应使用哪种字体以及哪种后备或替换字体来显示文本。该font-family属性的值包含多个字体名称，所有字体都以逗号分隔。

从左侧开始，第一个声明的字体是主要的字体选择。如果第一个字体不可用，则从左到右依次按优先顺序声明替代字体。

由两个或多个单词组成的字体名称需要用引号括起来。此外，最后一个字体应该是一个关键字值，它将使用指定类型的系统默认字体，最常见的是sans-serif或serif。

```
例：body {font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;}
```

#### 字体大小

该font-size属性提供了使用常用长度值设置文本大小的功能，包括像素，em单位，百分比，点或font-size关键字。

```
例：body {font-size: 14px;}
```

#### 字体样式

要将文本更改为斜体，或者为了防止文本被斜体化，我们将使用该font-style属性。该font-style属性接受四个关键字值：normal，italic，oblique，和inherit。在这四个中，最常用的是italic（将文本设置为斜体）和normal（将文本返回到其正常样式）。

```
例：.special {font-style: italic;}
```

#### 字体粗细

我们希望将文本设置为粗体或更改字体的特定粗细。对于这些情况，我们将使用该font-weight属性。

关键字值包括normal，bold，bolder，lighter，和inherit。在这些关键字值中，建议主要使用normal和bold将文本从正常更改为粗体，反之亦然。而不是使用关键字值，bolder或者lighter更好地使用数值来进行更具体的控制。

```
例：.daring {font-weight: 600;}
```

#### 行高

行高，两行文本之间的距离（通常称为行首）是使用line-height属性声明的。该line-height属性接受所有常规长度值。

```
例：body {line-height: 22px;}
```

#### 简写字体属性

前面列出的所有基于字体的属性可以组合并滚动到一个字体属性和简写值中。字体属性可以接受多个基于字体的属性值。这些属性值的顺序应该如下，从左到右：字体样式、字体变体、字体权重、字体大小、行高和字体系列。

作为简写值，这些属性值是从左到右列出的，不使用逗号（除了字体名，因为字体族属性值使用逗号）。在字体大小和行高属性值之间需要一个正斜杠/，分隔符。

当使用这个简写值时，除了字体大小和字体族属性值之外，每个属性值都是可选的。也就是说，如果愿意，我们只能在简写值中包括字体大小和字体族属性值。

```
例：html {font: italic small-caps bold 14px/22px "Helvetica Neue", Helvetica, Arial, sans-serif;}
```

#### CSS伪类

**:hover ** 当用户将鼠标悬停在该元素上时，伪类会为元素设置样式。当与&lt;a&gt;元素一起使用时，如此处所示，所有&lt;a&gt;元素在悬停时都将获得独特的样式。

### 2、应用文本属性

学会如何对齐，修饰，缩进，转换和空格文本。

#### 文字对齐

对齐文本是在页面上构建节奏和流动的重要部分;我们使用该text-align属性执行此操作。

text-align有五个值：left，right，center，justify，和inherit。它们将文本对齐到左侧，右侧或中心，或者它们对齐文本。

**PS: **text-align的值left和right将一个元素的左侧或右侧中的文本对齐，而float值left和right将移动整个元件。

#### 文字装饰

该text-decoration属性提供了一些修饰文本的方法。它接受的关键字值none，underline，overline，line-through，和inherit。

```
例：.note {text-decoration: underline;}
```

#### 文字缩进

该text-indent属性可用于缩进元素中的第一行文本。此属性可以使用所有常用长度值，包括像素，点，百分比等。正值将向内缩进文本，而负值将向外缩进文本。

```
例：p {text-indent: 20px;}
```

#### 文字阴影

该text-shadow属性允许我们为文本添加阴影或多个阴影。该属性通常需要四个值，所有值都从左到右依次列出。前三个值是长度，最后一个值是颜色。在三个长度值中，第一个值确定阴影的水平偏移，第二个值确定阴影的垂直偏移，第三个值确定阴影的模糊半径。第四个也是最后一个值是阴影的颜色，可以是color属性中使用的任何颜色值。

```
例：p {text-shadow: 3px 6px 2px rgba(0, 0, 0, .3);}
```

#### 盒子阴影

ext-shadow属性专门在元素的文本上放置阴影。如果我们想在整个元素上放置阴影，我们可以使用该box-shadow属性。

box-shadow属性就像text-shadow属性一样，接受水平和垂直偏移的值，模糊和颜色。

box-shadow属性还接受在颜色值之前的可选第四长度值，用于阴影的扩散。作为正长度值，展开将使阴影扩大到大于其应用的元素的大小，并且作为负长度值，展开将缩小阴影以使其小于其应用的元素的大小。

最后，box-shadow属性可以在inset值的开头包含可选值，以将阴影放置在元素内而不是元素外部。

#### 文字转换

当font-variant属性查找字体的替代变体时，该text-transform属性将更改内联文本而无需替换字体。该text-transform属性接受五个值：none，capitalize，uppercase，lowercase，和inherit。

```
例：p {text-transform: uppercase;}
```

#### 字母间距

使用该letter-spacing属性，我们可以调整页面上字母之间的空间（或跟踪）。正长度值将推动字母彼此远离，而负长度值将字母拉得更近。关键字值none将使字母之间的空格返回其正常大小。

使用letter-spacing属性的相对长度值将有助于确保font-size在文本更改时保持字母之间的正确间距。

```
例：p {letter-spacing: -.5em;}
```

#### 单词间距

与letter-spacing属性非常相似，可以使用word-spacing属性调整元素中单词之间的空间。该word-spacing属性接受与属性相同的长度值和关键字letter-spacing。但是，不是将字母分开，而是word-spacing在单词之间应用这些值。

```
例：p {word-spacing: .25em;}
```

## 四、引文

&lt;cite&gt;：用于引用广告素材作品，作者或资源

&lt;q&gt;：用于简短的内联引用

&lt;blockquote&gt;：用于更长的外部引文

### 引用创意作品

&lt;cite&gt;元素必须包含作品的标题，作者的名称或作品的URL引用。默认情况下，&lt;cite&gt;元素中包含的内容将在浏览器中以斜体显示。

```
例：<p>The book <cite><a href="http://www.amazon.com/Steve-Jobs-Walter-Isaacson/dp/1451648537">Steve Jobs</a></cite> is truly inspirational.</p>
```

### 对话与散文引文

&lt;q&gt;元素在语义上表示引用的对话或散文，不应用于任何其他目的。

包含在&lt;q&gt;元素上的可选属性是cite属性，该cite属性充当URL的形式引用。此属性不会改变元素的外观;它只是为屏幕阅读器和其他设备增加了价值。由于该属性在浏览器中不可查看，因此在实际报价旁边提供指向此源的超链接也很有帮助。

```
<p><a href="http://www.businessweek.com/magazine/content/06_06/b3970001.htm">Steve Jobs</a> once said, <q cite="http://www.businessweek.com/magazine/content/06_06/b3970001.htm">One home run is much better than two doubles.</q></p>
```

### 外部引文

要引用来自外部源并跨越多行的大块文本，我们将使用该&lt;blockquote&gt;元素。这&lt;blockquote&gt;是一个块级元素，可能包含嵌套在其中的其他块级元素，包括标题和段落。

```
例：<blockquote>
  <p>&#8220;In most people&#8217;s vocabularies, design is a veneer. It&#8217;s interior decorating. It&#8217;s the fabric of the curtains, of the sofa. But to me, nothing could be further from the meaning of design. Design is the fundamental soul of a human-made creation that ends up expressing itself in successive outer layers of the product.&#8221;</p>
    </blockquote>
```

&lt;blockquote&gt;元素中使用的较长引号通常包括引用。该引用可以包括cite属性和&lt;cite&gt;元素。该cite属性可以包含在&lt;blockquote&gt;元素上 - 与&lt;q&gt;之前在元素上使用的方式相同- 以URL的形式提供引用。

&lt;cite&gt;元素可以落在实际报价本身之后，以指定报价的原始来源.





















































































