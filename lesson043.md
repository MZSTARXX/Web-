可以将各个边界侧的样式控制在更精细的水平。例如，如果我们只想更改`width`底部边框，我们可以使用以下代码：

```
div {
  border-bottom-width: 12px;
}
```

这些特殊的写法可以使边框属性更确切。`top`，`right`，`bottom`，`left`-然后是`width`，`style`或者`color`取决于所需要的性质。

#### 边界半径

当我们查看边界及其不同的属性时，我们需要检查`border-radius`属性，这使我们能够改变元素的角。

`border-radius`属性接受长度单位，包括百分比和像素，用于标识元素的角被输入的半径。单个值将改变元素的四个角;两个值将按顺序围绕`top-left`/`bottom-right`和`top-right`/`bottom-left`角;四个值将圆的`top-left`，`top-right`，`bottom-right`，`bottom-left`依次改变。

当考虑其中多个值被施加到所述顺序`border-radius`特性（以及在`margin`和`padding`属性），它们以顺时针方式移动并开始于一个元件的左上角。

```
div {
  border-radius: 5px;
}
```

该`border-radius`属性也可以允许我们改变元素各个角的半径。这些`border`纵向属性从角落的垂直位置（`top`或`bottom`

）和角落的水平位置（`left`或`right`）开始，然后以半径结束。例如，要更改a的右上角半径，

可以使用`border-top-right-radius`属性。

```
div {
  border-top-right-radius: 5px;
}
```

### 盒子大小

到目前为止，盒子模型一直是添加剂设计。如果设置了`width`一个元素，以`400`像素，然后添加像素为20padding和border的元素，每边像素为10。实际宽变`460`像素。请记住，我们需要将,,和属性值一起添加`width`，以获得元素的实际宽度paddingborder。

但是，可以更改盒子模型以支持不同的计算。CSS3引入了`box-sizing`属性，它允许我们准确地改变盒子模型的工作方式以及如何计算元素的大小。三个主要的属性值-`content-box`，`padding-box`和`border-box`-每个都具有在盒子的大小是如何计算的略微不同的影响。

#### 内容框

该`content-box`值是默认值，将盒子模型作为添加剂设计。如果我们不使用该`box-sizing`属性，这将是所有元素的默认值。一个元件的尺寸始于`width`和`height`属性，然后任何`padding`，`border`或`margin`属性值从那里加入上。

```
div {
  -webkit-box-sizing: content-box;
     -moz-box-sizing: content-box;
          box-sizing: content-box;
}
```

#### 特定于浏览器的属性和值

不同的浏览器所用的前缀不同。

作为参考，这里概述了最常见的供应商前缀：

* 火狐浏览器：
  `-moz-`
* Microsoft Internet Explorer：
  `-ms-`
* Webkit（谷歌浏览器和Apple Safari）：
  `-webkit-`

#### 填充盒

该padding-box值通过width和height元素中包含任何属性值来更改框模型。当使用padding-box值，如果一个元件具有width为400像素和padding为20像素周围的每一个侧，实际宽度将保持400像素。随着任何padding值的增加，元素中的内容大小会按比例缩小。

如果我们添加一个border或者margin，那些值将被添加到width或height属性以计算整个框大小。如果我们添加border为10像素和padding为20像素。周围的元素的每个边width为400像素，实际全宽将成为420像素。

```
div {
  box-sizing: padding-box;
}
```

#### 填充框值已弃用

随着CSS规范的发展，该属性的padding-box值已被弃用，不应使用。

#### 边框

`border-box`值会更改框模型，以便任何`border`或`padding`属性值都包含在元素`width`和`height`元素中。当使用`border-box`值，如果一个元素的width为400像素，padding为20像素，且一个border为10像素周围的每一个侧，实际宽度将保持`400`像素。

如果我们添加a`margin`，则需要添加这些值以计算整个框大小。无论使用哪个`box-sizing`属性值，`margin`都需要添加任何值来计算元素的完整大小。

```
div {
  box-sizing: border-box;
}
```

![](https://learn.shayhowe.com/assets/images/courses/html-css/opening-the-box-model/box-sizing.png "CSS3盒子大小")

不同的box-sizing值允许从不同区域计算元素的宽度及其框

#### 挑选一个盒子大小

一般来说，最好的box-sizing使用是border-box。这个border-box使我们的数学变得更加容易。如果我们想要一个400像素宽的像素，那么400无论我们添加什么填充或边框值，它都将保持像素宽。

此外，我们可以轻松混合长度值。假设我们希望我们的盒子是40%的宽。添加padding为20像素和border为10元素在其周围的每一侧的像素并不困难，我们仍然可以保证实际width仍为40%，尽管在其他地方使用的像素值。

使用box-sizing属性的缺点是，作为CSS3规范的一部分，不是每个浏览器都支持它;它特别缺乏旧版浏览器的支持。随着新浏览器的发布，这种情况变得越来越少。

