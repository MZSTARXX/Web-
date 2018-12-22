## 清除和包含浮动

该float属性最初旨在允许内容环绕图像。图像可以浮动，然后围绕该图像的所有内容可以自然地围绕它流动。虽然这对于图像float非常有用，但该属性实际上并不是用于布局和定位，因此它带来了一些缺陷。

其中一个缺陷是，正确的样式不会总是呈现在它旁边的元素上，或者是浮动元素的父元素。当元素浮动时，它将从页面的正常流中取出，结果，浮动元素周围的元素样式可能会受到负面影响。

通常margin，padding属性值不能正确解释，导致它们混合到浮动元素中; 其他属性也会受到影响。

另一个缺陷是有时不需要的内容开始环绕浮动元素。从文档流中移除元素允许浮动元素周围的所有元素包裹并消耗浮动元素周围的任何可用空间。

之前的两列示例中，浮动了&lt;section&gt;和&lt;aside&gt;元素之后，在任何一个上设置width属性值之前，元素中的内容&lt;footer&gt;将包含在它上面的两个浮动元素之间，填充任何可用空间。因此，&lt;footer&gt;元素将位于元素&lt;section&gt;和&lt;aside&gt;元素之间的沟槽中，消耗可用空间。

## 清除浮动

清除浮动使用完成clear属性，它接受几个不同的值：最常用的值为所述left，right和both。

```
div {
  clear: left;
}
```

该left值将清除左浮动，而right值将清除右浮动。both但是，该值将清除左右浮动，通常是最理想的值。

回到我们前面的例子，如果我们使用的clear属性与价值both上的&lt;footer&gt;元素，我们可以清除浮动。重要的是，将此清除应用于浮动元素之后出现的元素，而不是之前，将页面返回到其正常流程。

```
footer {
  clear: both;
}
```

## 包含浮动

包含与清除的结果几乎相同，但是，包含浮动确实有助于确保我们的所有样式都能正确呈现。

要包含浮点数，浮动元素必须位于父元素中。父元素将充当容器，使文档流在其外部完全正常。

该元素的CSS由group下面的类表示，如下所示：

```
.group:before,
.group:after {
  content: "";
  display: table;
}
.group:after {
  clear: both;
}
.group {
  clear: both;
  *zoom: 1;
}
```

这里有很多内容，但基本上CSS正在做的是清除元素中的任何浮动元素，并将文档流恢复正常。

更具体地说，如第4课练习中所提到的，:before和:after伪元素是动态生成的元素，在元素的上方和下方具有group类。这些元素不包含任何内容，并显示为table级别元素，类似于块级元素。具有类的元素之后的动态生成元素group正在清除元素内的浮点数，类似于clear之前的类。最后，具有group类本身的元素也会清除可能出现在其上方的任何浮动，以防可能存在左浮动或右浮动。它还包括一些小技巧，让旧版浏览器可以很好地播放。

它比clear: both;单独声明更多的代码，但它可以证明是非常有用的。

从前面看我们的双列页面布局，我们可以使用父元素包装&lt;section&gt;和&lt;aside&gt;元素。然后，该父元素需要包含其自身的浮点数。代码如下所示：

###### HTML

```
<header>...</header>
<div class="group">
  <section>...</section>
  <aside>...</aside>
</div>
<footer>...</footer>
```

###### CSS

```
.group:before,
.group:after {
  content: "";
  display: table;
}
.group:after {
  clear: both;
}
.group {
  clear: both;
  *zoom: 1;
}
section {
  float: left;
  margin: 0 1.5%;
  width: 63%;
}
aside {
  float: right;
  margin: 0 1.5%;
  width: 30%;
}
```

#### 包含浮动演示的布局

此处显示的包含元素的技术称为“clearfix”，通常可以在类名为clearfix或的其他网站中找到**cf**。但是，我们选择使用类名group，因为它代表了一组元素，并且更好地表达了内容。

当元素浮动时，重要的是要记录它们如何影响页面流，并确保通过清除或包含浮动所需的页面流来重置页面流。无法跟踪浮动可能会导致相当多的麻烦，尤其是当页面开始有多行多列时。

## 在实践中 {#practice-1}

在Styles Conference网站试试浮动一些内容。

1. 首先，在我们开始浮动任何元素之前，让我们通过在CSS中添加clearfix来提供一种包含这些浮点数的方法。在main.css文件中，就在我们的网格样式下面，让我们在类名下面添加clearfix group。

   ```
   /*
     ========================================
     Clearfix
     ========================================
   */
   .group:before,
   .group:after {
     content: "";
     display: table;
   }
   .group:after {
     clear: both;
   }
   .group {
     clear: both;
     *zoom: 1;
   }
   ```

2. 现在我们可以包含浮点数，让我们&lt;h1&gt;将&lt;header&gt;元素浮动到元素左侧，并允许标题中的所有其他内容包含在它的右侧。

   为此，我们logo为&lt;h1&gt;元素添加一类。然后在我们的CSS中，让我们为主标题添加一个新的样式部分。在本节中，我们将选择&lt;h1&gt;带有logo类的元素，然后选择float左侧的元素。

   ###### HTML

   ```
   <h1 class="logo">
     <a href="index.html">Styles Conference</a>
   </h1>
   ```

   ###### CSS

   ```
   /*
     ========================================
     Primary header
     ========================================
   */

   .logo {
     float: left;
   }
   ```

3. 为徽标添加更多细节。我们首先在单词“Styles”和单词“Conference”之间放置一个&lt;br&gt;元素或换行符，以强制我们的徽标文本位于两行。

   在CSS中，让我们在徽标的顶部添加边框，并在垂直边缘添加边框，以便padding为徽标提供空间。

   ###### HTML

   ```
   <h1 class="logo">
     <a href="index.html">Styles <br> Conference</a>
   </h1>
   ```

   ###### CSS

   ```
   .logo {
     border-top: 4px solid #648880;
     padding: 40px 0 22px 0;
     float: left;
   }
   ```

4. 因为我们浮动了&lt;h1&gt;元素，我们想要包含它的float。元素中最接近&lt;h1&gt;的父元素是&lt;header&gt;元素，因此我们要将元素添加group到&lt;header&gt;元素中。这样做会将我们之前设置的clearfix样式应用于&lt;header&gt;元素。

   ```
   <header class="container group">
     ...
   </header>
   ```

5. 该&lt;header&gt;元素正在形成。就像我们对&lt;header&gt;元素所做的一样，我们将我们的版权浮动到&lt;small&gt;元素的左侧，让所有其他元素围绕它向右旋转。

   与&lt;header&gt;元素不同，我们不会直接在浮动元素上使用类。这次我们要将一个类应用于浮动元素的父级，并使用唯一的CSS选择器来选择元素然后浮动它。

   从将primary-footer添加到&lt;footer&gt;中开始。因为我们知道我们将在&lt;footer&gt;元素中浮动一个元素，所以我们也应该在处理它时添加group类。

   ```
   <footer class="primary-footer container group">
     ...
   </footer>
   ```

6. 既然类primary-footer在&lt;footer&gt;元素上，我们可以使用css中的类来对&lt;small&gt;进行预先限定。我们需要选择&lt;small&gt;并将其浮动到左侧。在main.css文件中为这些主要页脚样式创建一个新部分。

   ```
   /*
     ========================================
     Primary footer
     ========================================
   */

   .primary-footer small {
     float: left;
   }
   ```

   。

7. 最后，让我们放置padding在&lt;footer&gt;元素的顶部和底部，来将它与页面的其余部分分开一些。我们可以通过使用primary-footer带有类选择器的类来直接执行此操作。

   ```
   .primary-footer {
     padding-bottom: 44px;
     padding-top: 44px;
   }
   ```

对于&lt;header&gt;和&lt;footer&gt;元素的所有更改，我们必须确保在每个页面上创建它们，而不仅仅是index.html页面。

![](https://learn.shayhowe.com/assets/images/courses/html-css/positioning-content/practice-1.png "Styles Conference网站")

## 使用内联块定位 {#inline-block}

除了使用浮点数之外，我们可以通过将display属性与inline-block值结合来定位内容。内联块方法主要用于布局页面或将元素彼此相邻放置在一行中。

显示属性的内联块值将显示行内的元素，同时允许他们接受所有盒模型的性质，包括height，width，padding，border，和margin。使用内联块元素可以让我们充分利用盒子模型，而不必担心清除任何浮动。

### 内联块实践

我们来看看之前的三栏示例。我们首先要保持我们的HTML：

```
<header>...</header>
<section>...</section>
<section>...</section>
<section>...</section>
<footer>...</footer>
```

现在我们不是将我们的三个&lt;section&gt;元素浮动，而是将它们的display值更改为inline-block，margin并且width单独保留和属性。我们生成的CSS将如下所示：

```
section {
  display: inline-block;
  margin: 0 1.5%;
  width: 30%;
}
```

不幸的是，仅此代码并不能完全解决问题，最后一个&lt;section&gt;元素被推送到新行。请记住，因为内联块元素显示在彼此相同的行上，所以它们之间包含一个空格。当每个单独空间的大小添加到行中所有元素的width水平margin值时，总宽度变得太大，将最后一个&lt;section&gt;元素推送到新行。为了显示&lt;section&gt;同一行上的所有&lt;section&gt;元素，必须删除每个元素之间的空白区域。

### 删除内联块元素之间的空格

有许多方法可以删除内联块元素之间的空间，有些方法比其他元素更复杂。我们将关注两种最简单的方法，这两种方式都发生在HTML中。

第一种解决方案是将每个新&lt;section&gt;元素的开始标记放在与前一个&lt;section&gt;元素的结束标记相同的行上。结束与开始在同一行上，而不是为每个元素使用新行。

```
<header>...</header>
<section>
  ...
</section><section>
  ...
</section><section>
  ...
</section>
<footer>...</footer>
```

以这种方式编写内联块元素可确保HTML中的内联块元素之间的空间不存在;因此，在呈现页面时不会出现空格。

#### 没有空格演示的内联块元素

删除内联块元素之间的空格的另一种方法是在内联块元素的结束标记之后直接打开HTML注释。然后，在下一个内联块元素的开始标记之前关闭HTML注释。这样做允许内联块元素在单独的HTML行上开始和结束，并“注释掉”元素之间的任何潜在空间。生成的代码如下所示：

```
<header>...</header>
<section>
  ...
</section><!--
--><section>
  ...
</section><!--
--><section>
  ...
 </section>
 <footer>...</footer>
```

这些选项都不是完美的，但它们都很有帮助。我倾向于使用评论来更好地组织，但您选择哪个选项完全取决于您。

## 创建可重用布局 {#reusable-layouts}

在构建网站时，最好编写可在其他地方重用的模块化样式，并且可重用代码列表中的可重用布局很高。可以使用浮点数或内联块元素创建布局。

使用浮点数或内联块元素来布置页面结构是否更好是有争议的。我的方法是使用内联块元素来创建页面的网格或布局，然后在我希望内容环绕给定元素时使用浮点数（因为浮点数用于图像）。通常，我还发现内联块元素更易于使用。也就是说，使用最适合你的方法。目前在工作专用flex-和grid-基于属性中有新的CSS规范- 这将有助于解决如何最好地布局页面。这些方法开始浮出水面时要密切注意。

## 在实践中 {#practice-2}

凭借对可重复使用布局的深刻理解，现在是时候在我们的Styles Conference网站上实现一个。

1. 对于Styles Conference网站，我们将使用内联块元素创建三列可重用布局。我们这样做的方式允许我们有三列相等宽度或两列，总宽度在它们之间分开，三分之一在一列，三分之一在另一列。

   首先，我们将创建定义width这些列的类。我们将创建的两个类是col-1-3，col-2-3。在我们main.css文件的网格部分中，让我们继续并定义这些类及其相应的宽度。

   ```
   .col-1-3 {
     width: 33.33%;
   }
   .col-2-3 {
     width: 66.66%;
   }
   ```

2. 我们希望两列都显示为内联块元素。我们还需要确保它们的垂直对齐方式也设置为top每列的垂直对齐方式。

   让我们创建两个新的选择器，它们将共享显示和垂直对齐属性样式。

   ```
   .col-1-3,
   .col-2-3 {
     display: inline-block;
     vertical-align: top;
   }
   ```

   再看一下CSS，我们创建了两个类选择器，col-1-3与col-2-3用逗号分隔。第一个选择器末尾的逗号表示要跟随另一个选择器。第二个选择器后面是开始的花括号，{表示将遵循样式声明。通过逗号分隔选择器，我们可以一次将相同的样式绑定到多个选择器。

我们希望在每个列之间放置一些空格以帮助分解内容。我们可以通过padding来实现这一点。但是，当两列彼此相邻时，它们之间的空间宽度将是从外侧列到行边缘的空间宽度的两倍。为了平衡这一点，我们将所有列放在网格中，并将相同的填充从列添加到该网格。

让我们使用类名grid来标识我们的网格，然后让padding我们为网格col-1-3和col-2-3类标识相同的水平。用逗号分隔我们的选择器，我们的CSS看起来像这样：

`.grid,  
.col-1-3,  
.col-2-3 {  
  padding-left: 15px;  
  padding-right: 15px;  
}`

4. 当我们设置横向padding时，我们需要小心。在上一课中，我们创建了一个容器元素，由类container所知，将所有内容集中在一个960像素宽的元素内的页面上。目前，如果我们将一个具有grid的元素放置到一个有类container的元素中，它们的水平填充将相互叠加，并且我们的列将不会与页面其余部分的宽度成比例。

 我们不希望发生这种情况，因此我们必须与container规则集共享规则集中的一些样式grid。具体来说，我们需要共享width属性和值（以确保我们的页面保持固定在960像素宽）以及margin属性和值（以使页面上具有网格类的任何元素居中）。

 我们将通过将旧container规则集拆分为以下内容来实现此目的：

.`container,  
   .grid {  
     margin: 0 auto;  
     width: 960px;  
   }  
   .container {  
     padding-left: 30px;  
     padding-right: 30px;  
   }`

   现在，具有类\`container\`或网格的任何元素都将是\`960\`像素宽并且在页面上居中。此外，我们\`container\`通过将其移动到新的单独规则集中，为任何元素保留了现有的水平填充。

5.完成我们可重复使用的网格样式所需的所有繁重工作。现在是时候使用我们的HTML并查看这些类的执行情况了。

我们将从主页上的teasers开始，在我们的\`index.html\`文件中，将它们对齐成三列。目前，teasers包含在一个\`&lt;section&gt;\`类的元素中\`container\`。我们希望将该类更改为\`container\`，\`grid\`以便我们可以开始在其中放置列。

```
<section class="grid">
  ...
</section>
```

6. 接下来，我们将要添加一个\`col-1-3\`类到&lt;section&gt;元素与类的grid中的每个\`&lt;section&gt;\`元素中。

7. 最后，因为我们的每个列都是一个内联块元素，所以我们要确保删除它们之间的空白空间。我们将使用注释来执行此操作，并且我们将添加一些文档，注意每个即将发布的部分，同时我们将更好地组织代码。

```
  <section class="grid">
  
  <!-- Speakers -->
  
  <section class="col-1-3">
    ...
  </section><!--
  
  Schedule
  
  --><section class="col-1-3">
    ...
  </section><!--
  
  Venue
  
  --><section class="col-1-3">
    ...
  </section>

</section>
```

在第3行，我们会留下一条评论，标明“演讲者”部分。在第7行的末尾，我们在结束\`&lt;/section&gt;\`标记后立即打开注释。在该评论中，在第9行，我们确定了“计划”部分。然后，我们在第11行的开头关闭注释，就在开始\`&lt;section&gt;\`标记之前。这个相同的评论结构重新出现在两个\`&lt;section&gt;\`元素之间的第13到17行，就在“Venue”部分之前。总之，我们已经注释掉列之间的任何潜在空白，同时也使用这些注释来标识我们的部分。



我们现在有一个可重复使用的三列网格，支持多种排列，使用三分之一和三分之二宽度的列。我们的主页现在有三列，分解所有不同的部分。

## ![](https://learn.shayhowe.com/assets/images/courses/html-css/positioning-content/practice-2.png "Styles Conference website")独特的定位元素

我们偶尔会想要精确定位一个元素，但是浮点数或内联块元素不会起作用。浮动（从页面流中移除元素）通常会产生不需要的结果，因为周围元素围绕浮动元素流动。内联块元素，除非我们创建列，否则进入正确的位置可能相当尴尬。对于这些情况，我们可以将该\`position\`属性与box偏移属性结合使用。

该\`position\`属性标识\_如何\_元件被定位在页面上，以及是否将一个文件的正常流动内出现。这在与盒属性-偏移一起使用\`top\`，\`right\`，\`bottom\`，和\`left\`哪位准确识别\_，其中\_一个元件通过将在多个不同的方向上的移动元件被定位。

默认情况下，每个元素的\`position\`值都为\`static\`，这意味着它存在于文档的正常流中，并且它不接受任何框偏移属性。该\`static\`值最常用a\`relative\`或\`absolute\`value覆盖，我们接下来将对其进行检查。

### 相对定位

属性的\`relative\`值\`position\`允许元素出现在页面的正常流程中，为元素留出空间，而不允许其他元素在其周围流动;但是，它还允许使用框偏移属性修改元素的显示位置。例如，请考虑以下HTML和CSS：

###### HTML

```
<div>...</div>
<div class="offset">...</div>
<div>...</div>        
```

###### CSS

```
div {
  height: 100px;
  width: 100px;
}
.offset {
  left: 20px;
  position: relative;
  top: 20px;
}          
```

这里第二个\`&lt;div&gt;\`元素，即具有类的元素\`offset\`，具有\`position\`值\`relative\`和两个盒偏移属性，\`left\`和\`top\`。这样可以保留元素的原始位置，并且不允许其他元素移动到此空间。此外，该框偏移性重新定位元件，将它\`20\`从像素\`left\`和\`20\`像素从\`top\`其原始位置的。

### 相对定位

对于相对定位的元素，重要的是要知道框偏移属性标识元素从给定其原始位置移动的位置。因此，\`left\`具有\`20\`像素值的属性实际上将元素从左侧\`20\`像素向右推。然后，\`top\`具有\`20\`像素值的属性将元素从顶部\`20\`像素推向底部。

当我们使用框偏移属性定位元素时，元素与其下方的元素重叠，而不是像\`margin\`或\`padding\`属性那样向下移动该元素。

### 绝对定位

所述\`absolute\`的值\`position\`属性是从不同\`relative\`在于用的元件值\`position\`的值\`absolute\`的文件的正常流内将不会出现，并且绝对定位元素的原始空间和位置将不会被保留。

另外，绝对定位的元素相对于它们最接近的相对定位的父元素移动。如果不存在相对定位的父元素，则绝对定位的元素将相对于\`&lt;body&gt;\`元素定位。这是相当多的信息;让我们来看看它在一些代码中是如何工作的：

###### HTML

```
<section>
  <div class="offset">...</div>
</section>
```

###### CSS

```
section {
  position: relative;
}
div {
  position: absolute;
  right: 20px;
  top: 20px;
}
```

在此示例中，`<section>`元素相对定位但不包括任何框偏移属性。因此，它的立场不会改变。`<div>`具有类的元素`offset`包括`position`值`absolute`。因为`<section>`元素是与元素最接近的相对定位的父元素`<div>`，所以`<div>`元素将相对于`<section>`元素定位。

对于相对定位的元素，框偏移属性标识元素相对于其自身移动的方向。对于绝对定位的元素，框偏移属性标识元素将相对于其最近的相对定位的父元素移动的方向。

作为右侧和顶部框偏移属性的结果，所述`<div>`元件将出现`20`从像素`right`和`20`像素从`top`的`<section>`。

因为`<div>`元素是绝对定位的，所以它不会位于页面的正常流中，并且会与任何周围元素重叠。另外，`<div>`不保留原始位置，并且其他元素能够占据该空间。

通常，可以在不使用`position`属性和框偏移属性的情况下处理大多数定位，但在某些情况下，它们可能非常有用。

