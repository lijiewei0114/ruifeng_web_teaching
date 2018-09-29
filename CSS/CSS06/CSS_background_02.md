## 6、背景固定

  `background-attachment` 属性用于固定背景图，其主要有两个值：

- fixed：页面出现滚动条后就算页面滚动，背景图也会固定在原来的位置不会跟随页面滚动。
- scroll：默认值，当页面滚动的时候，背景图也跟随页面同步滚动。

[参考示例](https://lihongyao.github.io/tutorials/css/background/bg_attachment.html)

## 7、背景裁切

  `background-clip` 属性是规定背景显示的范围，是从“border”开始，是从“padding”开始，还是从“content”开始，它有以下值：

- border-box：默认，背景的覆盖范围从“border”开始
- padding-box：背景的覆盖范围从“padding”开始
- content-box：背景的覆盖范围从“content”开始

```html
<div class="bg-clip-wrap">
    <section class="item border-box"></section>
    <section class="item padding-box"></section>
    <section class="item content-box"></section>
</div>
```

```css
.bg-clip-wrap {
    text-align: center;
}
.bg-clip-wrap .item {
    width:  200px;
    height: 130px;

    display: inline-block;
    margin: 0px 30px;
    padding: 10px;
    border: 10px dashed #800080;
    
    background-image: url("../images/sights.jpeg");
}

.bg-clip-wrap .border-box  { background-clip: border-box; }
.bg-clip-wrap .padding-box { background-clip: padding-box;}
.bg-clip-wrap .content-box { background-clip: content-box;}
```

![](../../image/css/IMGS/bg-clip.png)

## 8、背景起始位置

  ` background-origin` 设置背景图像开始的位置，它和 *background-clip*  的使用方式十分相似，二者的区别在于 *background-clip* 主要是设置裁切范围，而 *background-origin* 主要是设置背景图片的起始位置，即从什么位置开始显示图片。该属同样的有以下3个属性值：

- border-box：默认，背景的覆盖范围从“border”开始
- padding-box：背景的覆盖范围从“padding”开始
- content-box：背景的覆盖范围从“content”开始

```html
<div class="bg-origin-wrap">
    <section class="item border-box"></section>
    <section class="item padding-box"></section>
    <section class="item content-box"></section>
</div>
```

```css
.bg-origin-wrap {
    text-align: center;
}

.bg-origin-wrap .item {
    width:  200px;
    height: 130px;

    display: inline-block;
    margin: 0px 30px;
    padding: 10px;
    border: 10px dashed #800080;
    
    background-image: url("../images/sights.jpeg");
}

.bg-origin-wrap .border-box  { background-origin: border-box;}
.bg-origin-wrap .padding-box { background-origin: padding-box;}
.bg-origin-wrap .content-box { background-origin: content-box;}
```

![](../../image/css/IMGS/bg-origin.png)



## 9、背景组合值

  在实际的开发过程中为了节省代码量，减小维护难度，我们通常会采用组合值的写法去设置背景，通常是下面这种模式：

```css
background: color image repeat attachment position;
```

  以上属性也可以省略，只设置其中一个，其中“background-clip”、“background-size”及“background-orign”需单独设置。