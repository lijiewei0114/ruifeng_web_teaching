# HTML补充拓展 

## iframe 框架

1. 通过使用框架，你可以在同一个浏览器窗口中显示不止一个页面。 语法：

   ```

   ```

name：设置iframe的名称

width：设置iframe的宽度，值可以为像素（不用添加“px”单位）和百分数

height：设置iframe的高度，值可以为像素（不用添加“px”单位）和百分数

src：设置iframe元素内需要显示页面或文件的URL地址，该属性的值可以由与之关联的a标签点击设置（通过将a标签的“target”属性的值设置为该iframe的“name”属性的值进行关联）

frameborder：设置是否显示边框（0 表示不显示边框/ 1 表示要显示边框）

scrolling：设置是否允许滚动（auto/yes/no）

```
​```
	<iframe src="demo_iframe.htm" name="iframe_a" scrolling="yes"></iframe>

​```
```

## 布局标签/语义化标签

HTML 提供了一系列标签用于布局，主要包括一下标签：

```
<div>
```

布局标签（通用容器）

```
<article>

```

用于文章、新闻或博客，表示文档、页面、应用或一个独立的容器，article可以嵌套article，只要里面的article与外面的article是部分与整体的关系。

```
<section>

```

章节标签，表示具体相似主题的一组内容，比如网站的主页可以分成介绍、新闻条目、联系信息等条块。

```
<aside>

```

指定附注栏，包括引述、侧栏、指向文章的一组链接、广告、友情链接、相关产品列表等。

```
<header>

```

页眉，通常包括网站标志，主导航，全站链接及搜索框，也适合对页面内部一组介绍性或导航性内容进行标记。

```
<footer>

```

页脚，通常包括网站版权信息等。

```
<nav>

```

标记导航，仅对文档中重要的链接使用。HTML5规范不推荐对辅助性页脚使用nav，除非页脚再次显示顶级全局导航，或者包含招聘信息等重要链接。

```
<small>

```

指定细则，输入免责声明、注解、署名、版权。只适用于短语，不要用来标记“使用条款”、“隐私政策”等长的法律声明。

```
<figure>
```

创建图（默认有40px左右margin）。

```
<figcaption>

```

figure的标题，必须是figure内嵌的第一个或者最后一个元素。

```
<time>

```

标记时间。

```
<main>

```

页面主要内容，一个页面只能使用一次。如果是web应用，则包围其主要功能。

## HTML 格式化标签

#### 概述

1. HTML 使用标签 b(“bold”) 与 i("italic”) 对输出的文本进行格式, 如：粗体 or 斜体 这些HTML标签被称为格式化标签
2. 通常标签 strong 替换加粗标签 b 来使用, em 替换 i标签使用。 然而，这些标签的含义是不同的：
   1. b 与 i 定义粗体或斜体文本。
   2. strong 或者 em意味着你要呈现的文本是重要的,所以要突出显示。现今所有主要浏览器都能渲染各种效果的字体。不过，未来浏览器可能会支持更好的渲染效果。
   3. em strong更加语义化

| 标签     | 描述     |
| ------ | ------ |
| b      | 粗字体    |
| em     | 着重     |
| i      | 斜体字    |
| small  | 定义小号子  |
| strong | 表示加重语气 |
| sub    | 下标字    |
| sup    | 上标字    |
| ins    | 插入字    |
| del    | 删除字    |

## html全局属性

### 概述

HTML全局属性是可以应用于几乎所有（部分属性有一定的应用范围限制）的HTML标签的属性，现在已知的属性有16个，其中有一半左右是HTML5标准后出现的，很多属性在我们之前的学习中都已经接触过了的，能熟练地记识这些属性能够给我们之后的Web开发带来很多便利，减少开发中所犯的一些低级错误。作为一个Web前端工程师，能够准确地区分全局属性和特殊属性也是一项重要的基本功。接下来我们就来看看在HTML中哪些属性能够作为并为大部分主流浏览器所兼容的全局属性。

### 全局属性

#### 1.id

该属性能用于所有的HTML元素，为HTML元素指定一个唯一的标识符，用于CSS设置，JavasSript进行操作或其它脚本语言及服务器端语言进行设置操作。

```
​```

<p id="des"></p>
<b id="title"></b>

​```

```

#### 2. class

该属性可以用于所有HTML元素，为元素添加一个或多个类名。通常是用于CSS设置或配合JavaScript进行操作设置，多个类名以空格符进行分隔，多个元素可以使用同一个类名。

```
​```
<section class="box fr"></section>
<section class="box"></section>

​```

```

#### 4. title

该属性可以用于所有HTML元素，通过设置它的值，可以让用户鼠标悬浮在该元素上显示出“title”属性中所设置的值。如之前提到的 ![img]() 标签。

```
​```
<img src="1.jpegv" alt="图片加载失败..." title="Ferrari">
​```

```

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/html/html_basic/1.jpeg)

该属性在现在PC端中的Web开发非常常用，由于现在Web设计的趋势是简洁化、扁平化设计，页面上的元素也需要极力地简洁，很多常用的按钮甚至都没有文字，而是采用一个图标进行替代。但这样的设计会让有些用户不清楚按钮的实际用途，这个时候 title 就能起到一个补充说明的作用。

#### 5. lang

该属性用于设置元素的语言类型，不支持的标标有<base>，<br>，<frame>，<frameset>，<hr>，<iframe>，<param> 及 <script>，但通常的使用方式是直接给标签设置该属性，如：<html lang="zh-cn">、<html lang="zh">、<html lang="en">这样的形式，分别表示将语言类型设置为“简体中文”、“中文”、“英文”。

## 利用超链接下载指定文件

<a href="文件" download>下载

在a标签对中 添加download属性

## HTML5实用标签

1.<datalist>下拉列表

<datalist> 标签规定了 <input> 元素可能的选项列表。

<datalist> 标签被用来在为 <input> 元素提供"自动完成"的特性。用户能看到一个下拉列表，里边的选项是预先定义好的，将作为用户的输入数据。

请使用 <input> 元素的 list 属性来绑定 <datalist> 元素。

```
<datalist id="browsers">
  <option value="Internet Explorer">
  <option value="Firefox">
  <option value="Chrome">
  <option value="Opera">
  <option value="Safari">
</datalist>
```



2.<output>标签

执行计算然后在 <output> 元素中显示结果：

```
<form oninput="x.value=parseInt(a.value)+parseInt(b.value)">0
   <input type="range" id="a" value="50">100
   +<input type="number" id="b" value="50">
   =<output name="x" for="a b"></output>
</form> 
```

3.<mark>标签

突出显示部分文本:

```
<p>Do not forget to buy <mark>milk</mark> today.</p>
```



4.<meter>标签

使用 meter 元素来度量给定范围（gauge）内的数据：

```
<meter value="3" min="0" max="10">十分之三</meter>

<meter value="0.6">60%</meter> 
```



5.<progress>标签

标记下载进度:

```
对象的下载进度：
<progress>
<span id="objprogress">85</span>%
</progress>
```



6.<audio>标签

一段HTML音频:

```
<audio src="someaudio.wav">
您的浏览器不支持 audio 标签。
</audio>
```



7.<video>标签

HTML视频:

```
<video src="movie.ogg" controls="controls">
您的浏览器不支持 video 标签。
</video>
```





