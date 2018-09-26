# 盒模型

## 概述

所谓盒子模型，即是将网页布局中的元素（行内/行内块元素）进行拟物化的比喻，一个盒子由内容（content）、内间距（padding）、边框（border）以及外边距（margin）组成。如下图所示：

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/css/IMGS/box-model.jpeg)

想象一个盒子，它有：外边距（margin）、边框（border）、内边距（padding）、内容（content）四个属性；

让我们俯视这个盒子，它有上下左右四条边，所以每个属性除了内容（content），都包括四个部分：上下左右；这四部分可同时设置，也可分别设置；内边距可以理解为盒子里装的东西和边框的距离，而边框有厚薄和颜色之分，内容就是盒子中间装的东西，外边距就是边框外面自动留出的一段空白。

需要注意，与现实生活中盒子不同的是，现实生活中的东西一般不能大于盒子，否则盒子会被撑坏，而CSS盒子具有弹性，里面的东西大过盒子本身最多把它撑大，但它不会损坏的。

## 提示：只有 `块级元素` 与 `行内块元素` 具备盒子模型。

## 盒子类型

CSS盒子模型的类型主要有两个：

- IE浏览器盒子模型：`box-sizing:border-box;`
- 标准（W3C，其它主流浏览器）盒子模型（默认）：`box-sizing:content-box;`

由于一些“客观”的原因，IE盒子模型和标准盒子模型有一定的差异，具体表现在：IE盒子模型的宽度/高度包含了`content`、`padding`以及 `border`；而标准盒子模型的宽度/高度仅仅包含了`content`。意思也就是说，假设我设置一个元素的宽高为160px，然后设置边框为 5px，内间距为 15px 。对于IE盒子模型而言，整个元素的宽度还是160px，但是内容由于设置了5px 的边框 和 15px 的内间距之后会被压缩，因此内容只有 120px。而对于标准盒子模型而言，宽高属性值设置的仅仅只是内容的大小，因此，即使你设置了边框和内间距，并不会压缩内容的大小，而是把盒子撑大，这样，整个元素在页面上呈现的宽度就会变大，为200px。

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/css/IMGS/boxsizing_ie.png)

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/css/IMGS/boxsizing_w3c.png)

一方面为了兼容IE浏览器，另一方面是IE的盒子模型在实际的布局中的确更容易控制。所以我们在实际的开发工作中，都是将标准的盒子模型转换为IE的盒子模型。

## 盒子属性

#### 1. 宽度

`width` 属性用于设置元素的宽度，你需要注意的是，通过该属性设置的宽度有的时候未必就是元素真实的宽度，这是由于盒子模型类型的影响，IE盒子模型的 *width = content + padding + boder*，而标准盒子模型的 *width = content*。

`width` 属性最常用的两种设置方式为“像素（px）”设置和“百分比（%）”设置。他们的特点如下：

- 像素设置

  优点：该方式去设置宽度更为的稳定，也就是说当一个元素是通过像素去设置元素宽度的时候，该元素的内容，特别是用像素去设置的文本内容也相对稳定，不会因为设备分辨率的不同而在排版显示上有所不同。

  ​

  缺点：在不同设备上，需要对元素宽度进行修改才能得到最佳的布局效果。如一个在PC端宽度为“960像素”的元素，在手机端就会出现右半部分，甚至右大半部分的显示都会被裁切的情况（如“iphone 4”的浏览器显示分辨率为“320*480”）。

- 百分比设置

  优点：能对不同显示分辨率做出更好的适应。最外层的标签元素（<body>的子节点）若宽度设为“100%”，那无论是在具有“*4K*”显示分辨率的高清投影大屏幕上，还是在分辨率在几百像素的移动设备上，都能横向占满整个屏幕。现在有人将“百分比布局”称作“流式布局”，是一种应对“移动浪潮”布局的新趋势。

  ​

  缺点：若采用百分比布局的方式，很多因素难以控制，如采用默认大小的表单元素，HTML5的功能标签，都会给这种布局方式带来麻烦,若是采用多列布局的页面，这种布局方式在移动端上的效果绝对是“灾难性”的。特别是对于缺乏前端开发经验的开发人员而言，这种布局方式经常会出现一些布局效果在意料之外的情况。

  > tips：百分比设置的布局有一个“相对性”的特点，也就是它的百分比是对于父级元素而言的。

- inherit：继承

#### 2. 高度

`height` 属性用于设置元素的高度，它绝大部分特征、度量单位和盒子模型的计算方式基本上和 `width` 属性一样。

`width` 属性的表现和 `height` 属性的差异在于，在同样不设置<html>或<body>宽高的条件下，任意“块级元素”和“行内块级元素”在不考虑盒子模型的前提下使用 `widht` 属性设置百分比（%）单位都能达到预期的效果，而 `height` 则不然，除非父级元素设置 `height` 属性，否则无论用多少的百分比去设置元素的高度，该元素的高度都始终为 `0` 。

```
html, body {
    height: 100%;
}

```

#### 3. 内间距

`padding` 属性用于设置盒子内容与边框之间的间距，即内间距（填充）。它有四个分支属性：

- **padding-top**：设置该元素的边界与自身的内容在上方的间距。
- **padding-right**：设置该元素的边界与自身的内容在右方的间距。
- **padding-bottom**：设置该元素的边界与自身的内容在下方的间距。
- **padding-left**：设置该元素的边界与自身的内容在左方的间距。

`padding` 可以接收的值为：像素（px）、百分比（%）、inherit（继承）以及auto（浏览器自计算）。我们也可以使用组合值的形式直接设置四个方向的间距，如下所示：

- `padding: 10px;` -> 即将元素边界与内容四个方向“padding-top”、“padding-right”、“padding-bottom”和“padding-left”的间距都设置为10像素。
- `padding: 10px 20px;` -> 即将元素边界与内容上下两个方向“padding-top”、“padding-bottom”的间距都设置为10像素，与内容左右两个方向“padding-left”和“padding-right”的间距都设置为20像素。
- `padding: 10px 20px 15px;` -> 即将元素边界与内容上方“padding-top”的间距设置为10像素，与内容左右两个方向“padding-left”和“padding-right”的间距都设置为20像素，与内容下方“padding-top”的间距设置为15像素。
- `padding: 10px 20px 15px 30px;` -> 即将元素边界与内容上方、右方、下方以及左方的间距分别设置为10像素、20像素、15像素及30像素。

#### 4. 外间距

`margin` 属性主要用于设置某元素相对于同级元素和父级元素的一个距离值，常用单位像素“px”。该属性对文本类元素（即“行内元素”）标签是无效的。和 `padding` 一样，其拥有4个分支属性：

- **margin-top**

  距离上方同级元素在垂直方向的距离，若上方元素含有“margin-bottom”，则会重叠该值，并且取较大值作为间距值。

  若该元素为父元素内的首个子元素，则是设置父元素距离上方元素的距离（解决方案：父级元素添加 `overflow:hidden;`），若上方元素含有“margin-bottom”，则同样会重叠该值，取较大值作为间距值。

- **margin-right**

  距离父级元素右边框的距离，若父元素有内间距“padding-right”，则还需要加上该值。

  距离右方同级元素在水平方向的距离，若右方元素含有“margin-left”，则会和该值相加，取两个元素之间间距值的和作为间距值。

- **margin-bottom**

  距离下方同级元素在垂直方向的距离，若下方元素含有“margin-top”，则会重叠该值，并且取较大值作为间距值。若该元素是DOM内最后一个元素，则相当于是给父元素设置了一个下间距（padding-bottom），若父元素已经设置了“padding-bottom”，则与父元素的该值相加取和作为与页面底部的间距。

- **margin-left**

  距离父级元素左边框的距离，若父元素有内间距“padding-left”，则还需要加上该值。

  距离左方同级元素在水平方向的距离，若左方元素含有“margin-right”，则会和该值相加，取两个元素之间间距值的*和*作为间距值。

  ​

同样的，“margin” 也可以以组合值的形式出现，其单位及设值方法和“padding”一致，在设置值的时候从顶部顺时针（即上右下左的顺序）设置。

#### 5. 边框

`border` 属性的作用是为设定该属性的元素添加边框。在“标准盒子模型”中，该属性的分支属性“border-width”所设置的值会增加元素的实际宽度和高度，而在“IE盒子模型中”该属性的分支属性“border-width”所设置的值会和“padding”（若设置或标签自带该属性）共同占据内容的空间。该属性能对任何显示类型的元素设置，包括“行级元素（inline）”。

该属性有三个分支属性：

1）、border-width

设置边框宽度，单位为像素。设定边框的宽度。可以为Web技术中常用的度量单位，通常为像素“px”。

2）、border-style

设置边框的类型，主要有以下可以设定的值：

| 属性值    | 描述     |
| ------ | ------ |
| none   | 无边框    |
| solid  | 实线边框   |
| dotted | 点线边框   |
| dashed | 虚线边框   |
| double | 双线边框   |
| groove | 3D凹槽边框 |
| ridge  | 3D凸槽边框 |
| inset  | 内浮雕边框  |
| outset | 外浮雕边框  |

边框效果如下图所示：

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/css/IMGS/border-style.png)

示例代码：

```
<div class="wrap">
    <section class="box none">none</section>
    <section class="box solid">solid</section>
    <section class="box dotted">dotted</section>
    <section class="box dashed">dashed</section>
    <section class="box double">double</section>
    <section class="box groove">groove</section>
    <section class="box ridge">ridge</section>
    <section class="box inset">inset</section>
    <section class="box outset">outset</section>
</div>

```

```
.wrap {
    width:  800px;
    height: 300px;
    border: 1px solid #808080;
    border-radius: 5px;

    /*flex：弹性布局*/
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
}
.box {
    width: 100px;
    height: 60px;

    display: inline-block;
    margin: 0 10px;

    color: #fff;
    letter-spacing: 2px;
    text-align: center;
    line-height: 60px;
    background-color: orange;
    border: 5px none purple;
}

.none   { border-style: none;   }
.solid  { border-style: solid;  }
.dotted { border-style: dotted; }
.dashed { border-style: dashed; }
.double { border-style: double; }
.groove { border-style: groove; }
.ridge  { border-style: ridge;  }
.inset  { border-style: inset;  }
.outset { border-style: outset; }

```

3）、border-color

设置边框颜色，支持英文单词、十六进制以及rgb颜色。

4）、border

同样地，你也可以通过 `border` 属性直接设置四个方向的边框样式，其语法形式为：

```
border：border-width border-style border-color;

```

当然 `border` 属性的各个分支属性也能单独地对某个方向上的值进行设置。

- border-top：设置上边框
- border-right：设置右边框
- border-bottom：设置下边框
- border-left：设置左边框
- border-top-width：设置上边框宽度
- border-top-style：设置上边框样式
- border-top-color：设置上边框颜色
- border-right-width：设置右边框宽度
- border-right-style：设置右边框样式
- border-right-color：设置右边框颜色
- border-bottom-width：设置下边框宽度
- border-bottom-style：设置下边框样式
- border-bottom-color：设置下边框颜色
- border-left-width：设置左边看宽度
- border-left-style：设置左边看样式
- border-left-color：设置左边看颜色

```
<!-- HTML 部分 -->
<div class="box"></div>

<!-- CSS 部分 -->
<style type="text/css">
    .box {
        width:  160px;
        height: 100px;

        border-top: 10px dotted #CC0066;
        border-right: 15px double #CCCC00;
        border-bottom: 20px ridge #9933FF;

        border-left-width: 8px;
        border-left-style: inset;
        border-left-color: #CC9900;
    }
</style>

```

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/css/IMGS/border.png)

## 盒子圆角

`border-radius` 属性可以设置边框圆角，该属性虽然带了一个 `border` 字样，同样也是用来设置元素的边界，但它和“border”并无太大的关系，它是对元素的“左上”、“右上”、“右下”和“左下”四个角的“圆度”进行设置。该属性能对任何显示类型的元素设置，包括“行级元素（inline）”。

`border-radius` 实现的原理是根据该属性所设置的值，在元素内建立一个以该值为半径的“看不见的圆”，并以该圆的边缘形状来设置边角的圆度。

`border-radius` 单位可以是像素或百分比，如果采用百分比如 50%，并且元素宽高相等，则会呈现一个正圆，否则会呈现出一个椭圆。使用百分比时，其上限值为50%，增加这个值并不会出现任何效果。

设值时，你也可以设置两个值，如：`border-radius: 100px/120px`，用 “`/`” 符号进行分割，第一个值表示水平方向圆的半径，第二个表示垂直方向圆的半径。

`border-radius` 属性除了能统一对元素的边角进行设置，还能分别对一个矩形元素的四个角分别进行设置，如：

- border-top-left-radius：左上角
- border-top-right-radius：右上角
- border-bottom-left-radius：左下角
- border-bottom-right-radius：由下角

```
<div class="wrap">
	<section class="t1"></section>
	<section class="t2"></section>
	<section class="t3"></section>
	<section class="t4"></section>
	<section class="t5"></section>
</div>

```

```
div.wrap > section {
    width:  100px;
    height: 100px;
    background-color: purple;

    display: inline-block;
    margin: 0 10px;
}

.t1 { border-radius: 50%; }
.t2 { border-radius: 10px/50px; }
.t3 {
    border-top-right-radius: 30%;
    border-top-left-radius: 100px;
    border-bottom-left-radius: 30%;
    border-bottom-right-radius: 100px;
}
.t4 {
    border-top-right-radius: 50%;
    border-bottom-right-radius: 50%;
}

```

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/css/IMGS/border-radius.JPEG)

## 元素轮廓

`outline` 属性用于设置一个元素的轮廓线，和 `border` 不一样，`outline` 无论在什么“盒子模型”下，都不会占据页面的空间，并且它不能分别去设置各个方向的值，即不能对“top”、“right”、“bottom”和“left”方向的“outline”进行分别设置，只能进行统一设置。在使用“*webkit*（老版本Chrome浏览器、Safari浏览器以及iOS和Android系统自带浏览器）”内核或 “*blink*（以新版的Chrome浏览器和Opera浏览器为代表）”内核的浏览器中，该属性会在表单元素在获得焦点后自动出现，本意是让用户获得更好的交互体验，但该设定很多时候反而会影响我们对“Web”页面的风格设置，这个时候我们都是将它的值设置为“none”。另外，“outline”属性并不受圆角属性“border-radius”的影响。

和 “border” 属性大体一致，“outline” 有以下分支属性：

- **outline-width**：设置轮廓线的宽度，能为Web技术中常用的度量单位，最常用的为像素“px”。
- **outline-style**：设置轮廓线的样式，和“border-style”一致，这里就不在赘述。
- **outline-color**：设置轮廓线的颜色，和“border-color”一样支持Web的四种“颜色模式”。
- **outline-offset**：设置轮廓线相对元素边界的距离，通常以像素“px”为单位。

## 元素阴影

`box-shadow` 属性能够让元素获得一个“阴影”效果，根据颜色的不同，有时候也可以叫做“发光”效果。`box-shadow` 属性没有分支属性，它的值是以“组合值”的形式设置的，它最多允许6个值的组合，按值的顺序分别代表：

- **H-Skwing**：阴影在水平方向的偏移，负数是向左偏移，正数是向右偏移，单位为“px”。
- **V-Skwing**：阴影在垂直方向的偏移，负数是向上偏移，正数是向下偏移，单位为“px”。
- **blur**：阴影的“模糊距离”或“模糊程度”，单位为“px”。
- **spread**：阴影的扩展范围，若将“blur”设为“0”，该值则相当于一个可以进行位置偏移但不具备“outline-offset”的“outline”，单位为“px”。
- **color**：阴影的颜色，支持Web技术中的常用颜色模式：“颜色英文单词”、“HEX”、“RGBa”、“HSLa”。
- **inset**：将默认向外的阴影方向改为向内。

```
<!-- HTML 部分 -->
<div class="box">CHINA</div>

<!-- CSS 部分 -->
<style type="text/css">
	.box {
		width: 100px;
		height: 100px;

		text-align: center;
		line-height: 100px;
		letter-spacing: 2px;
		text-shadow: 2px 2px 1px #000;
		text-decoration: underline;

		box-shadow: 0px 0px 5px 5px gray;
	}
</style>
```

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/css/IMGS/box-shadow.png)

# CSS布局模型

## css布局模型

css 布局模型能够决定盒模型直接如何排列

![img](https://gitee.com/moist-master/rimi_web_font/raw/master/pics/css/IMGS/flex_01.gif)

css的布局模式分类

1、流动模型（Flow）

2、浮动模型 (Float)

3、层模型（Layer）

## Flow 流动模型

流动（Flow）是默认的网页布局模式。也就是说网页在默认状态下的 HTML 网页元素都是根据流动模型来分布网页内容的。

流动布局模型具有2个比较典型的特征：

1. 块状元素都会在所处的包含元素内自上而下按顺序垂直延伸分布，因为在默认状态下，块状元素的宽度都为100%。实际上，块状元素都会以行的形式占据位置。

   ```
   <div id="box2">box2</div><!--块状元素，由于没有设置宽度，宽度默认显示为100%-->
   <h1>标题</h1><!--块状元素，由于没有设置宽度，宽度默认显示为100%-->
   <p>文本段文本段段文本段文本段文本段文本段文本段。</p><!--块状元素，由于没有设置宽度，宽度默认显示为100%-->

   <div id="box1">box1</div>

   ```

2. 第二点，在流动模型下，内联元素都会在所处的包含元素内从左到右水平分布显示。（内联元素可不像块状元素这么霸道独占一行）

右侧代码编辑器中内联元素标签a、span、em、strong都是内联元素。

```
​```
<em>emmmm..</em>

<strong>strong..</strong>

<b>b..</b>

​```

```

## float 浮动模型

块状元素这么霸道都是独占一行，如果现在我们想让两个块状元素并排显示，怎么办呢？不要着急，设置元素浮动就可以实现这一愿望。

任何元素在默认情况下是不能浮动的，但可以用 CSS 定义为浮动，如 div、p、table、img 等元素都可以被定义为浮动。

```
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>

        div{
            width:200px;
            height:200px;
            border:2px red solid;
            float:left;
        }
    </style>
</head>
<body>



<div id="div1"></div>
<div id="div2"></div>


```

还可以把div分布到两边

```
        #div3{
            width:200px;
            height:200px;
            border:2px red solid;
            float:left;
        }

        #div4{
            width:200px;
            height:200px;
            border:2px red solid;
            float:right;
        }
        
<div id="div3"></div>
<div id="div4"></div>

```

## 层模型

层模型能让层一样可以对每个图层能够精确定位操作

层模型有三种形式：

1、绝对定位(position: absolute)

2、相对定位(position: relative)

3、固定定位(position: fixed)

#### 1. 绝对定位,把图形定义在绝对的位置

```
​```

<!DOCTYPE HTML>
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>absolute样式</title>
    <style type="text/css">
        #div1{
            width:200px;
            height:200px;
            border:2px red solid;
            position:absolute;
            left:10px;
            top:200px;


        }


        #div2{
            width:200px;
            height:200px;
            border:2px red solid;
            position:absolute;
            left:20px;
            top:300px;


        }
    </style>
</head>
<body>
<div id="div1"></div>
<div id="div2"></div>
</body>
</html>
​```

```

#### 2. 相对定位

如果想为元素设置层模型中的相对定位，需要设置position:relative（表示相对定位），它通过left、right、top、bottom属性确定元素在正常文档流中的偏移位置。相对定位完成的过程是首先按static(float)方式生成一个元素(并且元素像层一样浮动了起来)，然后相对于以前的位置移动，移动的方向和幅度由left、right、top、bottom属性确定，偏移前的位置保留不动。

```
​```

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>



        #div1{
            width:200px;
            height:200px;
            border:2px red solid;
            position:relative;
            left:100px;
            top:50px;
        }
    </style>
</head>
<body>




<div id="div1"></div>
</body>
</html>
​```

```

#### 3.固定定位

fixed：表示固定定位，与absolute定位类型类似，但它的相对移动的坐标是视图（屏幕内的网页窗口）本身。由于视图本身是固定的，它不会随浏览器窗口的滚动条滚动而变化

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>


        p{
            width:200px;
            height:200px;
            border:2px red solid;
            position:fixed;
            left:100px;
            top:50px;
        }

        div{
            width:200px;
            height:200px;
            border:2px red solid;

            left:100px;
            top:50px;
        }
    </style>
</head>
<body>




<p>文本文本文本文本文本文本本文本文<p>



</body>
</html>


```

## 相对定位和绝对定位的组合使用

#### 概述

上面看到 绝对定位是基于整个html的原点来进行位移的,其实我们也可以让绝对定位的参照点为某个元素,这就涉及到他们的组合使用了

#### 使用

1. 参照定位的元素必须是相对定位元素的前辈元素：

   ```
   <div id="box1"><!--参照定位的元素-->
       <div id="box2">相对参照元素进行定位</div><!--相对定位元素-->
   </div>


   ```

2. 参照定位的元素必须加入position:relative;

   ```
   #box1{
       width:200px;
       height:200px;
       position:relative;        
   }


   ```

3. 定位元素加入position:absolute，便可以使用top、bottom、left、right来进行偏移定位了。

   ```
   #box2{
       position:absolute;
       top:20px;
       left:30px;         
   }

   ```

4. 组合使用

   ```
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <title>Title</title>
       <style>
           #d1 {
               position: relative;
               border: 1px solid red;
               height: 50px;
               width: 50px;
           }

           #d2 {
               position: absolute;
               top: 10px;
               left: 10px;
               border: 1px solid red;

               height: 10px;
               width: 10px;
           }
       </style>
   </head>
   <body>
   <div id="d1">
       <div id="d2"></div>
   </div>
   </body>
   </html>
   ```