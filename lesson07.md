# 设置背景和渐变

在CSS中，元素背景可以是纯色，图像，渐变或这些的组合。

## 添加背景颜色 {#background-color}

向元素添加背景的最快方法是使用background or background-color属性添加单色背景。该background属性接受简写形式的色彩和图像，而background-color属性是严格用于设置固体的背景色。

```
例：div {background-color: #b2b2b2;}
```

## 添加背景图像 {#background-image}

除了为元素添加背景颜色外，我们还可以添加背景图像。背景图像与背景颜色类似;然而，它们提供了一些额外的属性来精细化图像。和以前一样，我们可以使用background具有简写值的属性，或者我们可以background-image直接使用该属性。无论我们使用哪个属性，都必须使用url\(\)函数识别图像源。

该url\(\)函数值将背景图片的路径，以及用于创建超链接路径的熟悉规则适用于此。留意不同的目录，并确保准确显示图像所在的位置。路径将放在括号内并引用。

```
div {background-image: url("alert.png");}
```

### 背景重复

默认情况下，除非另有说明，否则背景图像将无限制地垂直和水平重复。如果重复，则可以使用background-repeat属性来改变背景图像重复的方向。

```
例：div {background-image: url("alert.png");
     background-repeat: no-repeat;}
```

该background-repeat属性接受四个不同值：repeat，repeat-x，repeat-y，和no-repeat。重复值是默认值，将垂直和水平重复背景图像。

该repeat-x值将水平重复背景图像，而repeat-y值将垂直重复背景图像。最后，该no-repeat值将告诉浏览器一次显示背景图像 - 也就是说，根本不重复它。

### 背景位置

默认情况下，背景图像位于元素的左上角。但是，通过使用该background-position属性，我们可以精确控制背景图像相对于该角落的放置位置。

```
例：div {
  background-image: url("alert.png");
  background-position: 20px 10px;
  background-repeat: no-repeat;
}
```

该background-position属性需要两个值：水平偏移（第一个值）和垂直偏移（第二个值）。如果仅指定了一个值，则该值用于水平偏移，垂直偏移将默认为50%。

因为我们正在从元素的左上角移动背景图像，所以长度值将特别与该角相关。

要设置一个background-position值，我们可以使用top，right，bottom，left，和center关键字，像素，百分比，或任何长度测量值。关键字和百分比的工作方式非常相似关键字值left top与百分比值相同0 0，这将使图像位于元素的左上角。关键字值right bottom与百分比值相同，百分比值100% 100%将图像放置在元素的右下角。

### 简写背景图像值

background-color，background-image，background-position，和background-repeat属性可以被卷成对于单独的背景属性的速记值。这些性质作为简写的次序background属性值可能会发生变化，但它通常落在如background-color，background-image，background-position，然后background-repeat。

```
div {
  background: #b2b2b2 url("alert.png") 20px 10px no-repeat;
}
```

## 设计渐变背景 {#gradient-backgrounds}

我们可以使用background或background-image属性创建渐变，就像常规背景图像一样。渐变背景的属性值取决于我们想要的渐变类型，线性或径向。

**PS:**不同的浏览器所需要的前缀不同，虽然大多数浏览器已经取消了这一要求，但这一问题仍然需要我们注意。

### 线性渐变背景

通过使用linear-gradient\(\)属性中的background or background-image 来标识线性渐变。该函数linear-gradient\(\)必须包含两个颜色值，第一个颜色值是起始颜色值，第二个颜色值是结束颜色值。然后，浏览器将处理两种颜色之间的过渡。

在识别任何渐变背景之前，我们还将放入background一个纯色的默认属性。如果浏览器不支持渐变背景，则纯色将用作后备。

```
例：div {
  background: #466368;
  background: -webkit-linear-gradient(#648880, #293f50);
  background:    -moz-linear-gradient(#648880, #293f50);
  background:         linear-gradient(#648880, #293f50);
}
```

### 更改渐变背景的方向

默认情况下，线性渐变背景从元素的顶部移动到底部，在第一个颜色值和第二个颜色值之间平滑过渡。然而，可以使用在任何颜色值之前陈述的关键字或度数值来改变该方向。

例如，如果我们希望渐变从元素的左侧移动到右侧，我们可以使用关键字值to right来标识线性渐变应该前进的方向。关键字值也可以组合。如果我们希望渐变从元素的左上角移动到右下角，我们可以使用关键字值ofto right bottom。

```
例：div {
  background: #466368;
  background: linear-gradient(to right bottom, #648880, #293f50);
}
```

### 径向渐变背景

虽然线性梯度对于从一个方向移动到另一个方向的梯度是完美的，但是通常需要径向梯度。径向背景渐变就像线性渐变一样工作，并共享许多相同的值。对于径向渐变，而不是使用linear-gradient\(\)的内功能background或background-image属性，我们将使用radial-gradient\(\)功能。

径向渐变从元素的内部到外部工作。因此，在radial-gradient\(\)函数内识别的第一种颜色将位于元素的绝对中心，第二种颜色将位于元素的外部。然后，浏览器将创建两种颜色之间的过渡。

```
例：div {
  background: #466368;
  background: radial-gradient(#648880, #293f50);
}
```

### 渐变颜色停止

渐变背景至少会从一种颜色过渡到另一种颜色;但是，我们可以为渐变添加多种颜色，并在所有渐变之间进行浏览器转换。要做到这一点，我们将为给定的渐变函数添加颜色停止，用逗号分隔每个颜色停止与下一个颜色停止。

```
例：div {
  background: #648880;
  background: linear-gradient(to right, #f6f1d3, #648880, #293f50);
}
```

默认情况下，浏览器会将每个颜色停止位置与下一个颜色停止位置相等，并相应地在它们之间进行转换。如果希望更多地控制颜色的定位，则可以为每个颜色停止识别沿着梯度的位置。该位置应声明为长度值，并应落在颜色值之后。

```
例：div {
  background: #648880;
  background: linear-gradient(to right, #f6f1d3, #648880 85%, #293f50);
}
```

## 使用多个背景图像 {#multiple-background-images}

在最长的时间内，允许元素一次只有一个背景图像，这在设计页面时产生了很多约束。幸运的是，使用CSS3，我们现在可以通过逗号分隔元素background或background-image属性中的多个背景值，在元素上使用多个背景图像。

首先出现的背景图像值将是最前面的背景图像，最后列出的背景图像将是最后面的背景图像。第一个和最后一个之间的任何值都将相应地位于中间地带。

以下&lt;div&gt;是使用三个背景图像的元素的CSS示例：

```
例：div {
  background:  url("foreground.png") 0 0 no-repeat, url("middle-ground.png") 0 0 no-repeat, url("background.png") 0 0 no-repeat;
}
```

上述代码使用background属性的简写值，将多个背景图像值链接在一起。这些速记值也可以分解成横跨逗号分隔的值background-image，background-position和background-repeat特性。

## 探索新的背景属性 {#css3-background-properties}

随着渐变背景和多背景图片，CSS3也推出了三款新的CSS属性：background-size，background-clip，和background-origin。

该background-size属性允许我们更改背景图像的大小，而background-clip和background-origin属性允许我们控制背景图像的裁剪位置以及元素中包含背景图像的位置（例如，在边框内或填充内部）。

### CSS3背景大小

该background-size属性允许我们指定背景图像的大小。该属性接受一些不同的值，包括长度和关键字值。

使用长度值时，我们可以使用两个以空格分隔的值来指定宽度和高度值。第一个值将设置背景图像的宽度，而第二个值将设置背景图像的高度。重要的是要注意百分比值与元素的大小有关，而不是背景图像的原始大小。

因此，设置宽度background-size属性100%将使背景图像占据元素的整个宽度。如果在宽度之后未标识第二个值，则将自动设置高度值以保留背景图像的宽高比。

关键字值auto可以用作宽度或高度值以保持背景图像的宽高比。例如，如果我们想要75%在保持图像宽高比的同时将背景图像的高度设置为元素的高度，我们可以使用background-size属性值auto75%。

```
例：div {
  background: url("shay.jpg") 0 0 no-repeat;
  background-size: auto 75%;
  border: 2px dashed #9799a7;
  height: 240px;
  width: 200px;
}
```

### 覆盖和包含关键字值

除了长度背景大小属性值之外，还有用于背景大小属性的覆盖和包含关键字值。覆盖关键字值指定背景图像的大小将完全覆盖元素的宽度和高度。背景图像的原始纵横比将被保留，但是图像将根据需要拉伸或收缩以覆盖整个元素。

通常，当使用封面关键字值时，背景图像的一部分被切断，以便图像占据元素的全部可用空间。另一方面，contain关键字值指定背景图像的大小将被调整为完全包含在元素的宽度和高度内。这样做将保留背景图像的原始纵横比，但是图像将根据需要拉伸或收缩以保持在元素的宽度和高度内。

与封面关键字值相比，contain关键字值将始终显示完整的背景图像；然而，它通常不会占用元素的全部可用空间。封面和包含关键字值都可能导致稍微失真的背景图像，特别是当图像被拉伸到超过其原始尺寸时。在使用这些值时，我们要注意这一点，以确保结果样式令人满意。

### CSS3背景剪辑和背景来源

背景剪辑属性指定背景图像将覆盖的表面区域，背景原点属性指定背景位置应该从哪里开始。这两个新属性的引入与三个新关键字值的引入相对应：边框、填充框和内容框。这三个值中的每一个都可以用于背景剪辑和背景来源属性。

```
例：div {
  background: url("shay.jpg") 0 0 no-repeat;
  background-clip: padding-box;
  background-origin: border-box;
}
```

默认情况下，背景剪辑属性值设置为边框，允许背景图像扩展到与任何边界相同的区域。同时，默认情况下，背景原点属性值被设置为填充框，允许背景图像的开始扩展到元素的填充中。











