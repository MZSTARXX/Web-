## 实践





`<header>

`  <h1>Styles Conference</h1>

`  <h3>August 24&ndash;26th &mdash; Chicago, IL</h3>

`</header>

在`header`元素之后，使用引入我们会议的`section`元素添加一组新内容。我们将使用新的`h2`元素开始本节，并以现有段落结束。

`<section>

`  <h2>Dedicated to the Craft of Building Websites</h2>

`  <p>Every year the brightest web designers and front-end developers descend on Chicago to discuss the latest technologies. Join us this August!</p>

`</section>



`<section>

`  <section>

`    <h5>Speakers</h5>

`    <h3>World-Class Speakers</h3>

`    <p>Joining us from all around the world are over twenty fantastic speakers, here to share their stories.</p>

`  </section>

`</section>

 最后，让我们在末尾的`footer`元素中添加我们的版权。为此，我们使用`small`元素，它在语义上代表了侧面注释和小版本，

 通常，`small`元素中的内容将呈现为小，但我们的CSS重置将阻止这种情况发生。

`

`  <small>&copy; Styles Conference</small>

`</footer>`

## 编码特殊字符

`header`元素中的`h3`元素，以及`footer`元素中的`small`元素，都会有一些有趣的事情发生。具体地说，这些元素中的特殊字符正在编码。

 特殊字符包括各种标点符号、重音字母和符号。 直接输入HTML时，它们可能会被误认为是错误的字符，因此需要对它们进行编码。

 **每个编码字符以＆符号开头，以分号结尾。＆符号和分号之间的区别是字符的唯一编码，无论是名称还是数字编码。

 例如，将“resumé”这个词编码为resum＆eacute;。 在我们的标题中，我们编码了en和em，在页脚中，我们编码了版权符号。



## 创建超链接



例如，单击文本“Shay”，其中包含href属性值为http:/ /shayhowe.com的anchor元素，将用户带到相应网站。

&lt;a href="http://shayhowe.com"&gt;Shay&lt;/a&gt;

##  用锚点包含块级元素

 本质上，锚元素`<a>`是内联元素，并且根据Web标准，内联元素不会包含块级元素。但是，随着HTML5的引入，锚元素特别具有包装块，内联或任何其他级别元素的权限。这是对标准约定的中断，但使页面上的整个内容块成为链接是允许的。

## 相对和绝对路径











`

`<a href="about.html">About</a>

`

`<a href="http://www.google.com/">Google</a>

##  链接电子邮件地址















`<a href="mailto:shay@awesome.com?subject=Reaching%20Out&body=How%20are%20you">Email Me</a>

##  在新窗口中打开链接







`

##  链接到同一页面的部分









`<body id="top">

`   <a href="#top">Back to top</a>

`</body>

超链接非常有用，并彻底改变了我们使用互联网的方式。到目前为止，我们已经介绍了如何链接到其他页面或网站，以及如何创建电子邮件链接和指向同一页面部分的链接。让我们创建一些自己的链接。

## 实践中





 因为我们已经在index.html页面上，所以这看起来有点奇怪，但这是正确的。当标题在其他页面上复制时，链接回主页将是有意义的。

`

`  <a href="index.html">Styles Conference</a>

`</h1>

为了浏览所有不同的页面，我们将在`<header>`元素中使用`<nav>`元素添加导航菜单。我们将创建扬声器、时间表、地点和注册页面，与我们的主页一起使用，因此我们应该为所有这些页面创建链接。

`

`

`    <a href="index.html">Home</a>

`    <a href="speakers.html">Speakers</a>

`    <a href="schedule.html">Schedule</a>

`    <a href="venue.html">Venue</a>

`    <a href="register.html">Register</a>

`  </nav>

`

 方便起见，我们还将`<header>`元素中的相同导航菜单添加到`<footer>`元素中。



`

`    <a href="index.html">Home</a>

`    <a href="speakers.html">Speakers</a>

`    <a href="schedule.html">Schedule</a>

`    <a href="venue.html">Venue</a>

`    <a href="register.html">Register</a>

`  </nav>

`

 在介绍会议的`<section>`元素中，标题下方还应该包含一个注册会议的链接。在段落下方放置一个链接。



` <a href="register.html">Register Now</a>

`

 不要忘记添加指向我们其他页面的所有部分的链接。在每个部分中，让我们将&lt;h3&gt;和&lt;h5&gt;元素包含在链接到正确页面的锚元素中。

  我们要确保相应地为每个部分执行此操作。



`

`    <a href="speakers.html">

`      <h5>Speakers</h5>

`      <h3>World-Class Speakers</h3>

`    </a>

`    <p>Joining us from all around the world are over twenty fantastic speakers, here to share their stories.</p>

`  </section>

`

现在我们需要创建一些新页面。 让我们创建speakers.html，schedule.html，venue.html和register.html文件。这些文件应该与index.html文件位于同一文件夹中，并且，因为保存在同一文件夹中，所以所有的链接都应该按预期工作。
为了确保所有页面看起来都一样，这些新文件都应该具有相同的文档结构，&lt;header&gt;和&lt;footer&gt;元素作为index.html文件。








