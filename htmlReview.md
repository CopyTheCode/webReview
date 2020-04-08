# hello-html

> - [前端html的面试总结](https://github.com/CopyTheCode/webReview)
>
>   整理笔记如下

------

#### 1.HTML5新增语义化如何理解，为什么要语义化？

1，去掉或者丢失样式的时候能够让页面呈现出清晰的结构
2，有利于SEO：和搜索引擎建立良好沟通，有助于爬虫抓取更多的有效信息：爬虫依赖于标签来确定上下文和各个关键字的权重；
3，方便其他设备解析（如屏幕阅读器、盲人阅读器、移动设备）以意义的方式来渲染网页；
4，便于团队开发和维护，语义化更具可读性，是下一步吧网页的重要动向，遵循W3C标准的团队都遵循这个标准，可以减少差异化。



#### 2.写HTML代码时应注意什么？

尽可能少的使用无语义的标签div和span；

在语义不明显时，既可以使用div或者p时，尽量用p, 因为p在默认情况下有上下间距，对兼容特殊终端有利；

不要使用纯样式标签，如：b、font、u等，改用css设置。

需要强调的文本，可以包含在strong或者em标签中（浏览器预设样式，能用CSS指定就不用他们），strong默认样式是加粗（不要用b），em是斜体（不用i）；

使用表格时，标题要用caption，表头用thead，主体部分用tbody包围，尾部用tfoot包围。表头和一般单元格要区分开，表头用th，单元格用td；

表单域要用fieldset标签包起来，并用legend标签说明表单的用途；

每个input标签对应的说明文本都需要使用label标签，并且通过为input设置id属性，在lable标签中设置for=someld来让说明文本和相对应的input关联起来。



#### 3.附加语义化标签归纳：

###### ![](C:\Users\Administrator\Desktop\webReview\assets\html2.png)



#### 4.HTML5新增了哪些语义标签？

**<header>元素**

用于定义页面的介绍展示区域，通常包括网站logo、主导航、全站链接以及搜索框。也适合对页面内部一组介绍性或导航性内容进行标记

**<nav>元素**

定义页面的导航链接部分区域，不是所有的链接都需要包含在<nav>中，除了页脚再次显示顶级全局导航、或者包含招聘信息等重要链接。

**<main>元素**

定义页面的主要内容，一个页面只能使用一次。如果是web应用，则包围其主要功能。

 **<article>元素**

定义页面独立的内容，它可以有自己的header、footer、sections等，专注于单个主题的博客文章，报纸文章或网页文章。article可以嵌套article，只要里面的article与外面的是部分与整体的关系。

**<section>元素**

元素用于标记文档的各个部分，例如长表单文章的章节或主要部分。

 **<aside>元素**

定义与主要内容相关的内容块。通常显示为侧边栏。

**<footer>元素**

定义文档的底部区域，通常包含文档的作者，著作权信息，链接的使用条款，联系信息等



![](C:\Users\Administrator\Desktop\webReview\assets\html.jpg)

#### 5.什么是HTML？

HTML：HyperText Markup Language超文本标记语言



#### 6.页面导入样式时，使用link和@import有什么区别？

（1）作用不同：link属于XHTML标签，除了加载CSS外，还能用于 定义rel连接属性等作用；
而@import是CSS提供的，只能用于加载CSS;
（2）加载不同：页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
（3）兼容不同：import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;



#### 10.什么是锚点?

```html
 锚点就是网页中一个记号，可以通过超级链接跳转到该记号位置处。
 1.定义锚点
    1.使用a标记的name属性定义锚点
      <a name="锚点名称"></a>
    2.使用任意标记的id属性定义锚点
      <ANY id="锚点名称"></ANY>
 2.链接到锚点
      <a href="#锚点名称">本页面</a>
      <a href="url#锚点名称">其它页面</a>
```



#### 11.行内元素有哪些？块级元素有哪些？ 

首先：CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值，如div的display默认值为“block”，则为“块级”元素；span默认display属性值为“inline”，是“行内”元素。
（1）行内元素有：a b span img input select
（2）块级元素有：div p ul ol li dl dt dd h1-h6
（3）常见的空元素：br-换行，hr-水平分割线  link 等



#### 12.Label的作用是什么？是怎么用的？

label标签来定义表单控制间的关系,当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。

```html
<label for="Name">Number:</label>
<input type=“text“name="Name" id="Name"/>
<label>Date:<input type="text" name="B"/></label>
```



#### 13.简述一下src与href的区别?

src用于替换当前元素，href用于在当前文档和引用资源之间确立联系。



#### 14.清除浮动的方法有哪些？

第一种：clear:both

在父元素的里面添加一个空的clear的div（跟浮动的子级同级），然后再为这个类添加属性值clear:both;便可以清除浮动。

第二种：overflow：hidden

在父元素的样式中添加overflow: hidden;也可以清除浮动，如下css代码，但不提倡使用这个方法，overflow: hidden;还有一个意思就是隐藏超出的部分，处理不好还是会给页面带来麻烦。

第三种：clearfix(推荐使用)

1.在父集元素类名中添加 clear-fix
2.写伪类样式

```html
<style>  
.clear-fix::after {
   content:""; 
   display: block; 
   clear:both; 
}
</style>

<div class="header-line clear-fix">
            <div class="header-logo">
                <a class="logo"href=" https://www.meisaas.com/index.html">样式方案</a>
            </div>
</div>
```



#### 14.常见的浏览器内核有哪些，介绍一下你对浏览器内核的理解?

```html
Trident 内核：IE   (IE浏览器)
Gecko 内核：NETSCAPE6 及以上版本，火狐  (火狐浏览器)

Presto 内核：Opera7 及以上。[Opera 内核原为：Presto，现为：Blink;]  (opear浏览器)

Webkit内核：Safari，Chrome等。[Chrome的：Blink（WebKit的分支）]  (苹果浏览Safari)
```



#### 15.描述一下 cookie，sessionStorage 和 localStorage 的区别?

[补充离线存储]: https://segmentfault.com/a/1190000006984353)

![](C:\Users\Administrator\Desktop\webReview\assets\htm3.png)



#### 16.表单提交中Get和Post方式的区别？

1. `Get` 一般用于从服务器上获取数据，`Post` 向服务器传送数据
2. `Get` 传输的数据是拼接在Url之后的，对用户是可见的；`Post` 的传输数据对用户是不可见的
3. `Get` 传送的数据量较小，不能大于 `2KB`。`Post` 传送的数据量较大，一般被默认为不受限制
4. `Get` 安全性非常低，`Post` 安全性较高
5. 在 `FORM` 提交的时候，如果不指定 `Method`，则默认为 `Get` 请求



#### 17、img 标签的title和alt有什么区别？

title是global attributes之一，用于为元素提供附加的advisory information。通常当鼠标滑动到元素上的时候显示。
alt是<img>的特有属性，是图片内容的等价描述，用于图片无法加载时显示、读屏器阅读图片。可提图片高可访问性，除了纯装饰图片外都必须设置有意义的值，搜索引擎会重点分析。



#### 18.meta viewport 是做什么用的，怎么写？

```html
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
作用：控制移动端页面不要再重新缩放。

因为手机屏幕的分辨率已经越来越高，高像素但是屏幕尺寸却没有发生太大变化，那就意味着一个物理像素点实际上塞入了好几个像素。

所以在做移动端开发时，为了使移动端的页面在不同的手机上同样的大小来显示，我们可以将页面的宽度固定，然后获取设备的宽度，得到页面宽度与设备宽度的比例，再使用HTML5新增的viewport来对页面进行缩放，并固定不允许用户再重新缩放。
```

[补充canvas]: https://zhuanlan.zhihu.com/p/43700110



#### 19.实现不使用 border 画出1px高的线，在不同浏览器的Quirksmode和CSSCompat模式下都能保持同一效果?

```html
<div style="height:1px;overflow:hidden;background:red"></div>
```



##### [PS：以上内容收集网络，麻烦点个Star](https://github.com/CopyTheCode/webReview)

