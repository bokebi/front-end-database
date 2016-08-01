# 面试题目

## 关于标签
### 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？

CSS规范规定，每个元素都有默认的display值，如div的display默认值为“block”，则为“块级”元素；span默认display属性值为“inline”，是“行内”元素。

（1）行内元素有：a span img input select strong
（2）块级元素有：div ul ol li dl dt dd h1-h6 p
（3）常见的空元素：```<br> <hr> <img> <input> <link> <meta>```

HTML5中对块级、行内元素没有明确定义。

###	```<strong>，<em>和<b>，<i>```标签的区别
从表现形式上来看，```<em> 和<i>```都是表现为斜体，```<strong>和<b>```都是表现为加粗。
从意义上来看，```<b> <i>```是视觉要素，分别表示无意义的加粗，无意义的斜体。 ```<em> 和 <strong>``` 是表达要素(phrase elements)。```< em > ```（emphasized text）表示一般的强调文本，而 ```< strong >``` （strong emphasized text）表示比``` < em >``` 语义更强的的强调文本。

###	label标签的作用是什么？是怎么用的？
label标签来定义表单控件间的关系,当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。两种用法：
  
    <label for="Name">Number:</label>
    <input type=“text“name="Name" id="Name"/>
    
    <label>Date:<input type="text" name="B"/></label>
    
###iframe有哪些缺点？
是什么：iframe 元素会创建包含另外一个文档的内联框架（即行内框架）

缺点：
- iframe会阻塞主页面的Onload事件；
- iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载。

使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript动态给iframe添加src属性值，这样可以可以绕开以上两个问题。

##HTLM5
###	HTML5 为什么只需要写 <!DOCTYPE HTML>？
HTML5 不基于 SGML，因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照它们应该的方式来运行）；而HTML4.01基于SGML,所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型。

###html5有哪些新特性？

html5新增标签：article、section、aside、header、hgroup、footer、source、figure

			绘画 canvas ；用于媒介回放的 video 和 audio 元素
			本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失
			sessionStorage 的数据在浏览器关闭后自动删除
			语意化更好的内容元素，比如 article、footer、header、nav、section
			表单控件，email，url，number，range，search，color，meter，progress，
			calendar、date、time、email、url、search
			新的技术webworker, websocket, Geolocation
			拖放：draggable=”true”
			画布：canvas标签（与SVG矢量伸缩图形的区别）		
			地理定位：navigation.geolocation
			web存储：localStorage，sessionStorage
			应用缓存： Application Cache Manifest

Web Worker：当在 HTML 页面中执行脚本时，页面的状态是不可响应的，直到脚本已完成。web worker 是运行在后台的 JavaScript，独立于其他脚本，不会影响页面的性能。您可以继续做任何愿意做的事情：点击、选取内容等等，而此时 web worker 在后台运行。
			
websocket服务器发送事件：Server-Sent 事件–单向消息传递。Server-Sent 事件指的是网页自动获取来自服务器的更新。
			
表单：(1.Input类型：email、url、number、range、Date pickers、search、color)—>(2.表单元素：datalist、keygen、output)—>(3.表单属性：autocomplete、autofocus、form、min, max 和 step、multiple、pattern、placeholder、required)
###HTML5移除了那些元素？

- 纯表现的元素：basefont，big，center，font, s，strike，tt，u；
- 对可用性产生负面影响的元素：frame，frameset，noframes；

### 如何处理HTML5新标签的IE浏览器兼容问题？

IE8/IE7/IE6支持通过document.createElement方法产生的标签，
可以利用这一特性让这些浏览器支持HTML5新标签，浏览器支持新标签后，
还需要添加标签默认的样式。

当然最好的方式是直接使用成熟的框架、使用最多的是html5shim框架
<!--[if lt IE 9]>
<script> src="http://html5shim.googlecode.com/
svn/trunk/html5.js"</script>
<![endif]-->


###	HTML5的form如何关闭自动完成功能？
给不想要提示的 form 或下某个input 设置为 autocomplete=off。

###	对语义化的理解？
1. 去掉或者丢失样式的时候能够让页面呈现出清晰的结构
2. 有利于SEO：和搜索引擎建立良好沟通，有助于爬虫抓取更多的有效信息：爬虫依赖于标签来确定上下文和各个关键字的权重；
3. 方便其他设备解析（如屏幕阅读器、盲人阅读器、移动设备）以意义的方式来渲染网页；
4. 使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

HTML5中新增加的很多标签（如：```<article>、<nav>、<header>和<footer>```等）就是基于语义化设计原则。

## Doctype
### Doctype作用？标准模式与兼容模式各有什么区别?
（1）、<!DOCTYPE>声明位于HTML文档中的第一行，处于标签之前。告知浏览器的解析器用什么文档标准解析这个文档。DOCTYPE不存在或格式不正确会导致文档以兼容模式呈现。

（2）、标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。

###	你知道多少种Doctype文档类型？
该标签可声明三种 DTD 类型，分别表示严格版本、过渡版本以及基于框架的 HTML 文档。
- HTML 4.01 规定了三种文档类型：Strict、Transitional 以及 Frameset。
- XHTML 1.0 规定了三种 XML 文档类型：Strict、Transitional 以及 Frameset。
- Standards （标准）模式（也就是严格呈现模式）用于呈现遵循最新标准的网页，而 Quirks（包容）模式（也就是松散呈现模式或者兼容模式）用于呈现为传统浏览器而设计的网页。

