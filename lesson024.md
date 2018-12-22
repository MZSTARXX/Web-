## 实践

我们的样式会议网站缺乏真实的结构和内容。我们花一些时间来充实我们的主页。

使用现有的index.html文件，添加一个`header`元素。我们的`header`元素应该包含现有的`h1`元素；再添加一个`h3`元素作为标语来支持我们的`h1`元素。

`<header>`

`  <h1>Styles Conference</h1>`

`  <h3>August 24&ndash;26th &mdash; Chicago, IL</h3>`

`</header>`

在`header`元素之后，使用引入我们会议的`section`元素添加一组新内容。我们将使用新的`h2`元素开始本节，并以现有段落结束。

`<section>`

`  <h2>Dedicated to the Craft of Building Websites</h2>`

`  <p>Every year the brightest web designers and front-end developers descend on Chicago to discuss the latest technologies. Join us this August!</p>`

`</section>`

在此之后，添加另一组内容来梳理我们将要添加的几个页面，特别是演讲者、日程表和场地页面。我们整理的每个页面也应该位于相应的部分中，并包含支持文本。我们将结果分组到`section`元素中，单独的梳理也将包含在`section`元素中。 总之，我们在另一个`section`元素中有三个`section`元素。

`<section>`

`  <section>`

`    <h5>Speakers</h5>`

`    <h3>World-Class Speakers</h3>`

`    <p>Joining us from all around the world are over twenty fantastic speakers, here to share their stories.</p>`

`  </section>`

`</section>`

 最后，让我们在末尾的`footer`元素中添加我们的版权。为此，我们使用`small`元素，它在语义上代表了侧面注释和小版本，

 通常，`small`元素中的内容将呈现为小，但我们的CSS重置将阻止这种情况发生。

`<footer>`

`  <small>&copy; Styles Conference</small>`

`</footer>`

## 编码特殊字符

`header`元素中的`h3`元素，以及`footer`元素中的`small`元素，都会有一些有趣的事情发生。具体地说，这些元素中的特殊字符正在编码。

 特殊字符包括各种标点符号、重音字母和符号。 直接输入HTML时，它们可能会被误认为是错误的字符，因此需要对它们进行编码。

 **每个编码字符以＆符号开头，以分号结尾。＆符号和分号之间的区别是字符的唯一编码，无论是名称还是数字编码。**

 例如，将“resumé”这个词编码为resum＆eacute;。 在我们的标题中，我们编码了en和em，在页脚中，我们编码了版权符号。

随着主页的形成，让我们来创建超链接，以便添加其他页面并构建我们网站的其余部分。

## 创建超链接

超链接也是互联网的核心组件之一，它提供从一个网页或资源链接到另一个网页或资源的能力。使用锚点`<a>`（内联元素）建立超链接。为了创建从一个页面（或资源）到另一个页面（或资源）的链接，需要href属性（称为超链接引用）。href属性值标识链接的目标。

例如，单击文本“Shay”，其中包含href属性值为http:/ /shayhowe.com的anchor元素，将用户带到相应网站。

&lt;a href="http://shayhowe.com"&gt;Shay&lt;/a&gt;

##  用锚点包含块级元素

 本质上，锚元素`<a>`是内联元素，并且根据Web标准，内联元素不会包含块级元素。但是，随着HTML5的引入，锚元素特别具有包装块，内联或任何其他级别元素的权限。这是对标准约定的中断，但使页面上的整个内容块成为链接是允许的。

## 相对和绝对路径

两种最常见的链接类型是指向同一网站的其他页面的链接，以及指向其他网站的链接。这些链接由其href属性值标识，也称为其路径。

指向同一网站的其他页面的链接具有相对路径，该路径不包括href属性值中的域（.com，.org，.edu等）。由于链接指向同一网站上的另一个页面，href属性值只需要包含链接到的页面的文件名：about.html。

如果链接的页面在不同的目录或文件夹中，则href属性值也需要反映这一点。假设about.html页面位于pages目录中，相对路径将是pages / about.html。

链接到当前网站之外的其他网站需要绝对路径，其中href属性值必须包括完整域。指向Google的链接需要http:/ /google.com的href属性值，从http开始并包含域名.com。

例如，点击“关于”文本，将打开浏览器中的about.html页面。单击文本“Google”将在我们的浏览器中打开http:/ /google.com/。

`<!-- Relative Path -->`

`<a href="about.html">About</a>`

`<!-- Absolute Path -->`

`<a href="http://www.google.com/">Google</a>`

##  链接电子邮件地址

有时我们可能想要创建一个指向电子邮件地址的超链接，例如，“Email Me”的超链接文本，当点击该文本时，会打开用户的默认电子邮件客户端，并预先填充部分电子邮件。至少填充发送电子邮件的电子邮件地址，还可以包括诸如主题行和正文的其他信息。

要创建电子邮件链接，href属性值需要以mailto：开头，后跟邮件将发送到的电子邮件地址。例如，要创建到shay@awesome.com的电子邮件链接，href属性值将为mailto：shay@awesome.com。

另外，可以填充电子邮件的主题、正文和其他信息。要添加主题行，我们要在电子邮件地址后面加上subject =参数。电子邮件地址后面的第一个参数必须以问号“？”开头，以将其绑定到超链接路径。主题行中的多个单词要求使用％20对空格进行编码。

添加正文文本的方式与主题相同，使用href属性值中的body =参数。因为我们将一个参数绑定到另一个参数，所以我们需要使用＆符号来分隔两者。与主题一样，空格必须使用％20进行编码，并且必须使用％0A对换行符进行编码。

总而言之，链接到shay@awesome.com的主题为“伸出”和正文“你好吗”需要一个href属性值：

mailto:shay@awesome.comsubject=Reaching%20Out&body=How%20are%20you.

这是完整的细分：

`<a href="mailto:shay@awesome.com?subject=Reaching%20Out&body=How%20are%20you">Email Me</a>`

##  在新窗口中打开链接

超链接可用的一个功能是确定单击时链接打开的位置。 通常，链接在同一网页打开，但是，链接也可以在新窗口中打开。

要在新窗口中打开链接，请使用值为\\_blank的target属性。target属性确切地确定了链接的显示位置，\\_ blank属性指定了一个新窗口。

要在新窗口中打开http:/ /shayhowe.com/，代码将如下所示：

`<a href="http://shayhowe.com/" target="_blank">Shay Howe</a>`

##  链接到同一页面的部分

我们经常看到链接到同一页面部分的超链接。这些相同页面链接的常见示例是“返回顶部”链接，用于将用户返回到页面顶部。

我们可以通过在我们希望链接到的元素上设置id属性，然后在anchor元素的href属性中使用该id属性的值来创建页面链接。

以“回到顶部”链接为例，我们可以在`<body>`元素上放置一个id属性值top。 现在我们可以创建一个href属性值为＃top，pound sign和all的锚元素，以链接到`<body>`元素的开头。

我们这个同页链接的代码如下所示：

`<body id="top">`

`   <a href="#top">Back to top</a>`

`</body>`

超链接非常有用，并彻底改变了我们使用互联网的方式。到目前为止，我们已经介绍了如何链接到其他页面或网站，以及如何创建电子邮件链接和指向同一页面部分的链接。让我们创建一些自己的链接。

## 实践中

现在是时候将样式会议从单页网站带到一个包含多个页面的成熟网站，所有这些网站都将使用超链接链接在一起。

 我们首先在我们的`<header>`元素链接中的`<h1>`元素内部创建“样式会议”文本到index.html页面。

 因为我们已经在index.html页面上，所以这看起来有点奇怪，但这是正确的。当标题在其他页面上复制时，链接回主页将是有意义的。

`<h1>`

`  <a href="index.html">Styles Conference</a>`

`</h1>`

为了浏览所有不同的页面，我们将在`<header>`元素中使用`<nav>`元素添加导航菜单。我们将创建扬声器、时间表、地点和注册页面，与我们的主页一起使用，因此我们应该为所有这些页面创建链接。

`<header>`

`  <nav>`

`    <a href="index.html">Home</a>`

`    <a href="speakers.html">Speakers</a>`

`    <a href="schedule.html">Schedule</a>`

`    <a href="venue.html">Venue</a>`

`    <a href="register.html">Register</a>`

`  </nav>`

`</header>`

 方便起见，我们还将`<header>`元素中的相同导航菜单添加到`<footer>`元素中。

`<footer>`

`  <nav>`

`    <a href="index.html">Home</a>`

`    <a href="speakers.html">Speakers</a>`

`    <a href="schedule.html">Schedule</a>`

`    <a href="venue.html">Venue</a>`

`    <a href="register.html">Register</a>`

`  </nav>`

`</footer>`

 在介绍会议的`<section>`元素中，标题下方还应该包含一个注册会议的链接。在段落下方放置一个链接。

`<section>`

` <a href="register.html">Register Now</a>`

`</section>`

 不要忘记添加指向我们其他页面的所有部分的链接。在每个部分中，让我们将&lt;h3&gt;和&lt;h5&gt;元素包含在链接到正确页面的锚元素中。

  我们要确保相应地为每个部分执行此操作。

`<section>`

`  <section>`

`    <a href="speakers.html">`

`      <h5>Speakers</h5>`

`      <h3>World-Class Speakers</h3>`

`    </a>`

`    <p>Joining us from all around the world are over twenty fantastic speakers, here to share their stories.</p>`

`  </section>`

`</section>`

现在我们需要创建一些新页面。 让我们创建speakers.html，schedule.html，venue.html和register.html文件。这些文件应该与index.html文件位于同一文件夹中，并且，因为保存在同一文件夹中，所以所有的链接都应该按预期工作。
为了确保所有页面看起来都一样，这些新文件都应该具有相同的文档结构，&lt;header&gt;和&lt;footer&gt;元素作为index.html文件。

这是官方的，我们不再使用单页，而是一个完整的网站。







