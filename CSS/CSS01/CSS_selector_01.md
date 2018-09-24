# css选择器01

## 概述

在 CSS 中，选择器（ `Selector` ）是一种模式，用于选择需要添加样式的元素。

## css基础选择器

#### 1. 标签选择器

一个完整的HTML页面是有很多不同的标签组成，而标签选择器，则是决定哪些标签采用相应的CSS样式，写法如下：

```
div  { width:  300px; height: 300px; background-color: red; }
p    { text-indent: 2em; color: blue; }
span { letter-spacing: 5px; font-size: 20px; }

```

#### 2. 类选择器

类选择器（ *“class 选择器”* ）根据类名来选择，而这个类名是自定义的，但我们在定义这个类名的时候也应该尽量能反应被设置元素的实际功能。同一个类名的选择器理论上可以被任意多的标签元素使用。在CSS中，定义类名选择器应该以 `.` 作为开头，否则，浏览器将视为你自定义的标签名，写法如下：

```
.box  { width:  300px; height: 300px; background-color: red; }
p.des { text-indent: 2em; color: blue; }

```

需要注意的是，由于类名可以被任意多的标签元素使用，因此当你需要为特定标签类名设置样式的时候，可以在 `.` 之前指定标签名，这样就可以选中你要设置的对应的标签名中拥有该class的元素了，如上述示例中的 *“p.des { … }”* 即表示选择所有p标签中类名为`des`的元素。

#### 3. id选择器

ID 选择器即根据元素的ID属性值来选取元素，和类选择器类似，但值得注意的是，ID表示唯一标识符，即同一个页面只能出现一个ID。定义一个ID选择器以`#` 开头，如下所示：

```
#box { width:  300px; height: 300px; background-color: red; }
#des { text-indent: 2em; color: blue; }

```

#### 4. 通用选择器

通用选择器使用 `*` 表示，它的作用是选择页面中所有的标签元素。但业内很多Web前端优化师都认为该选择符存在性能问题，而且它一旦使用后父选择器与后代选择器的搭配容易出现浏览器不能解析的情况，所以一般在高质量的Web页面中基本是看不到该选择符的，就算是平时也不推荐大家使用。

#### 5. 后代选择器

后代选择器是对某元素所嵌套的指定元素进行选择，每个选择符之间用 **空格** 进行分割，多个嵌套层次应该以多个空格进行分割。如下所示：

```
<div class="container">
    <article>
        <h1>Napoléon Bonaparte</h1>
        <p>Adversity is the midwife of genius.</p>
    </article>
</div>

/*index.css*/
.container article { text-align: center; }
.container h1 { color: #000000; }
.container p  { color: #008800; }
```