# css选择器02

#### 6. 子类选择器

子选择器区别于后代选择器的地方就是，后代选择器可以选择嵌套在标签内部任意层级的标签元素，而子选择器只能选择当前标签往内一层的元素，即直接子元素。每个选择符之间用 `>` 进行分割，如下示例：

```
<header>
	<img src="images/logo.png" alt="logo">
	<nav>
		<ul class="menu-list">
			<li><a href="javascript:;">首页</a></li>
			<li><a href="javascript:;">新闻</a></li>
			<li><a href="javascript:;">科技</a></li>
			<li><a href="javascript:;">社会</a></li>
		</ul>
	</nav>
</header>
```

```
/*index.css*/
header > img { width:  80px; height: 30px; }
header > nav > ul.menu-list { list-style: none; }

```

#### 7. 伪类选择器

伪类选择器和其它选择器有所不同，它是通过触发一定的事件来实现效果，也就是说如果不进行任何操作是看不到该选择器的CSS样式设置的。以Google Chrome浏览器开发者工具为例，要想看到所设置的伪类选择器样式需通过：点击 **Element** 选项栏下 **Style** 选项栏中的 **:hov** 按钮，然后勾选需要查看的操作事件进行样式查看。目前支持的操作事件有，“hover”, “active”，“visited”和“focus”:

- link：表示链接在正常情况下（即页面刚加载完成时）显示的颜色。
- visited：表示链接被点击后显示的颜色。
- hover：表示鼠标悬停时显示的颜色。
- focus：表示元素获得光标焦点时使用的颜色，主要用于文本框输入文字时使用（鼠标松开时显示的颜色,可以使用input来查看）。
- active：表示当所指元素处于激活状态（鼠标在元素上按下还没有松开）时所显示的颜色。

```
a { text-decoration: none; }		
a:hover { text-decoration: underline;}


      a:link{
            color: red;
        }
        a:visited{
            color: green;
        }
        a:hover{
            color: red;
        }
        a:focus{
            color:black;
        }
        a:active{
            color: yellow;
        }
```