#### 边缘和填充声明

在CSS中，有多种方法可以为某些属性声明值。我们可以使用longhand，一个接一个地列出多个属性和值，其中每个值都有自己的属性。或者我们可以使用速记，使用一个属性列出多个值。并非所有属性都有速记替代，因此我们必须确保使用正确的属性和值结构。

`margin`和`padding`有两种手写和速记形式。当使用速记`margin`属性为元素的所有四边设置相同的值时，我们指定一个值：

```
div {
  margin: 20px;
}  
```

为设置一个值`top`及`bottom`用于和另一个值`left`和`right`元素的边，指定两个值：先设置top和bottom.然后设置left和right。

```
div {
  margin: 10px 20px;
}
```

要设置元素的所有四个侧面独自的值，顺时针指定这些值`top`，`right`，`bottom`，和`left`。top为10像素，right为20像素，bottom为0像素，left为15像素。

```
div {
  margin: 10px 20px 0 15px;
}
```

单独使用`margin`或`padding`属性，可以填任意数量的值。使用longhand，我们可以使用唯一属性，设置一侧的值。每个属性名称之后是一个短划线和盒的一侧到的值是要被施加：`top`，`right`，`bottom`，或`left`。例如，该`padding-left`属性只接受一个值，并将为该left元素设置填充;该`margin-top`属性只接受一个值，并将设置该`top`元素的边距。

```
div {
  margin-top: 10px;
  padding-left: 6px;
}
```

当我们只想识别一个`margin`或`padding`值时，最好使用速记属性。这样做可以使我们的代码明确，并帮助我们避免任何混乱。例如，当时我们真的要设置的`top`，`right`和`left`边缘元素的两侧`0`像素，还是我们真的只是想设置的bottom为10像素？在这里使用手写属性和值有助于明确我们的意图。但是，在处理三个或更多值时，速记非常有用。

#### 边距和填充颜色

在`margin`和`padding`性质是完全透明的，不接受任何颜色值。但是，透明，它们显示相对元素的背景颜色。对于边距，我们看到父元素的背景颜色，对于填充，我们看到`padding`应用元素的背景颜色。

### 边界

边框位于填充和边距之间，提供元素周围的轮廓。该`border`属性需要三个值：`width`，`style`，和`color`。在速记中border属性值赋给`width`，`style`，`color`。在普通写法，这三个值可被分解成的`border-width`，`border-style`和`border-color`特性。这些手写属性对于更改或覆盖单个边框值非常有用。

在`width`和`color`边界可以用长度和颜色的共同CSS单元进行定义，如在第3章中讨论。

边框可以有不同的外观。最常见的样式值是`solid`，`double`，`dashed`，`dotted`，和`none`，但也有一些其他选择。

这是一个`6`像素宽的实心灰色边框的代码：

```
div {
  border: 6px solid #949599;
}
```



