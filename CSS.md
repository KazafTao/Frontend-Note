# CSS

## 概述

CSS 专门用于 “美化” HTML标签

### 应用方式

1. 写在css文件里，是复用效率最高的方式

   ```html
   <head>
       <link rel="stylesheet" href="common.css">
   </head>
   ```

2. 在标签上

   ```html
   <div style="color:red"></div>
   ```

3. 在head中

   ```html
   <head>
       <style>
           .div{
               color:red;
           }
       </style>
   </head>
   ```

### 页面布局

根据效果图将页面划分为多个小区域，搭建html骨架，再一一实现这些区域的样式

## 选择器

### 类选择器(用得最多)

.类名

```css
.c1 {
    color:red;
}
```

### id选择器

#id名

```css
#id {
    color:red;
}
```

### 标签选择器

标签名

```css
div {
    color:red;
}
```

### 属性选择器

指定特定属性值：在选择器后加上[属性 = 值]

demo:

```css
.class[type='text'] {
    border: 1px solid red;
}
```

### 后代选择器 （用得多）

在选择器后继续指定选择器，使样式仅作用于同时满足两种选择器下的html标签，后代选择器可以多重嵌套

demo （选择c1类下的所有li标签）

```css
.c1 li {
    color:red;
}
```

如果只想选定直接后代而不是所有后代，可以加 >

demo  (选择c1类下第一层嵌套的li标签)

```css
.c1 > li {
    color:red;
}
```

## 样式覆盖

html标签可以有多个类，同时应用多个类的样式。如果不同类中定义了不同的样式效果，对于相同的样式，以css文件中最后的样式为准。

如果某个样式不希望被后面的样式覆盖，在其后加上！important，则该样式不会被覆盖

demo

```css
.c1 {
    color:red !important;
}
```

## 样式

### 高度和宽度

高度属性height，宽度属性width，这两个属性的值可以用px(像素)来确定，宽度支持百分比%，高度不支持百分比%

高度和宽度对行内标签不生效，对块标签生效，右侧区域即使空白也不允许占用。如果希望在行内标签中使用宽度和高度属性，可以将该标签转换为行内块标签，这样就可以应用高度和宽度

demo

```css
div {
    height: 300px;
    width: 50%;
}
```

### 字体和颜色

字体属性font-family

字体大小属性font-size，值可以用px(像素)确定

字体粗度属性font-weight

颜色属性color，值可以用十六进制颜色码确定

demo

```css
div {
    font-family: arial,sans-serif;
    font-size: 18px;
    font-weight: 600;
    color: #00FF7F;
}
```

### 文字对齐

demo

```css
div {
    text-align: center;   /*水平方向居中对齐*/
    line-height: xxpx;   /*垂直方向居中对齐，和height属性的值保持一致，且文本中只能有一行数据*/
}
```

### 边距

#### 内边距

标签里面的内容距离标签的距离，用于让内容和标签本身保持一定距离

demo

```html
<head>
    <meta charset="utf-8">
    <style>
        .outer {
            border: 1px solid red;
            width: 200px;
            height: 200px;
            padding-top: 20px;
            padding-left: 20px;
            padding-right: 20px;
        }

    </style>
</head>
<body>
<div class="outer">
    <div style="background-color:gold;">听妈妈的话</div>
    <div>小朋友</div>
</div>
</body>
```

![image-20220618112504755](https://s2.loli.net/2022/06/18/5IKPgLCmU4G79qu.png)

#### 外边距

标签距离其他标签的距离

demo

```html
<div style="height:200px;background-color:blue"></div>
<div style="height:100px;background-color:red;margin-top:20px"></div>
```

效果

![image-20220618132102807](https://s2.loli.net/2022/06/18/MOt9QjwhRrFBAaJ.png)

body默认有外边距，造成页面四边都有白色空隙。如果不希望看到body的外边距，可以添加

```css
body {
    margin:0;
}
```

如果希望区域水平居中，可以设置区域宽度+左右外边距为auto

如果希望区域垂直居中，可以计算整体区域高度与该区域高度的差，再除以二得到上下外边距

### 透明度

可以通过设置opacity来设置元素的透明度，取值在0-1之间，0表示全透明，1表示不透明

### 浮动

浮动demo

```html
<span style="float: right">右边</span>
```

块标签浮动起来的时候，变成行内块标签。标签浮动之后，就会脱离文档流，使父标签失去支撑。如果要取消脱离文档流的效果，可以在浮动标签的兄弟标签下加clear: both，demo如下

```html
<div style="float: left"></div>
<div style="clear: both;"></div>
```

### 位置

position有三个取值，分别为fixed，relative和absolute

#### fixed

固定在窗口的某个位置。demo

```html
<head>
    <meta charset="utf-8">
    <style>
        /* 通过四边距离均为0实现覆盖全屏的幕布效果 */
        .mask {
            background-color: black;
            position: fixed;
            left: 0;
            right: 0;
            top: 0;
            bottom: 0;
            opacity: 0.7;
        }
        /* 通过四边距离均为0 + 自动外边距实现居中的效果 */
        .dialog {
            width: 500px;
            height: 300px;
            background-color: white;
            position: fixed;
            left: 0;
            right: 0;
            top: 0;
            bottom: 0;
            margin: auto auto;
        }

    </style>
</head>
<body>
<div class="mask"></div>
<div class="dialog"></div>
</body>
```

![image-20220620153920237](https://s2.loli.net/2022/06/20/yEr3dvs7QTXUl2O.png)

#### relative和absolute

通过relative元素作为参考物，配置absolute相对于relative的元素的位置

demo,实现 下载二维码在下载链接的下方

```html
<a href="" class="download">下载app
    <div class="qcode">
        <img src="qcode.png" alt="下载二维码">
    </div>
 </a>
```

```css
.download {
    position: relative; /*作为参照物*/
}

.qcode {
    position: absolute; /*二维码默认在download的下方*/
    display: none;
}

.download:hover .qcode{
    display: block;
}
```

![image-20220620161721229](https://s2.loli.net/2022/06/20/jgEVo1b5p8IOFQh.png)

## 伪元素

### hover

设置鼠标放在元素上时的样式，demo

```css
.header a:hover {
    color: white;
}
```

还可以和其他样式组合使用，达到鼠标放在某个区域下元素才显示的效果

```css
.download {
    display: none;
}

.app:hover .download {
    display: block;
}
```

### after

在选定的元素后追加伪元素，demo

```html
head>
    <meta charset="utf-8">
    <style>
        a:after {
            content: "->"  /*在所有a标签的内容后面自动添加一个 -> */
        }
    </style>
</head>
<body>
<a href="">点击</a>
```

效果如下

![image-20220620113611392](https://s2.loli.net/2022/06/20/U4t5eBh8OwXYEJv.png)

应用：在float元素后面自动追加 ```<div style="clear:both;"></div>``` 清除浮动元素，demo

```css
/*这样clearfix类的div就不需要再添加 <div style="clear:both;"></div>了*/
.clearfix:after {
    content: "";
    display: block;
    clear: both; 
}
```







