# JQuery

## 部署jquery

可以在官网下载[开发版](https://code.jquery.com/jquery-3.6.0.js)和[生产环境版](https://code.jquery.com/jquery-3.6.0.min.js)jquery文件，再将文件放在项目对应的文件夹中。

## 用法

### 寻找标签

jquery可以使用css的选择器，而不是js原生的document.getElementByxx函数

```js
$("#txt").text("demo")  //修改id为txt的标签的内容为demo
$(".c1")                //选择类为c1的标签
$("div")                //选择所有的div标签
$(".c1 .c2 a")          //选择c1类下的c2类下的所有a标签
$("input[name='n1']")   //属性选择器
$("#txt").prev()         //id为txt标签的前一个标签
$("#txt").next()         //id为txt标签的下一个标签
$("#txt").parent()       //id为txt标签的上一级标签
$("#txt").children()      //id为txt标签的所有的子级标签
$("#txt").children('.c1') //id为txt标签的所有的子级标签中类为c1的标签
$("#txt").find("div")      //id为txt标签下的所有div标签
```

## demo

### 实现点击隐藏/显示菜单

````html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>菜单</title>
    <link rel="stylesheet" href="static/css/menu.css">
</head>
<body>
<div class="menu">
    <div class="item">
        <div class="header">上海</div>
        <div class="content">
            <a href="">宝山区</a>
            <a href="">青浦区</a>
            <a href="">浦东新区</a>
            <a href="">普陀区</a>
        </div>
    </div>
    <div class="item">
        <div class="header">北京</div>
        <div class="content">
            <a href="">海淀区</a>
            <a href="">朝阳区</a>
            <a href="">大兴区</a>
            <a href="">昌平区</a>
        </div>
    </div>
</div>
<script src="static/plugins/jquery/jquery-3.6.0.js"></script>
<script src="static/js/menu.js"></script>
</body>
</html>
````

```css
.menu {
    width: 300px;
    height: 800px;
    border: 1px solid red;
}

.item .header {
    background-color: yellow;
    height: 40px;
    line-height: 40px;
}

.content a {
    display: block;
    height: 30px;
    line-height: 30px;
    border-bottom: 1px dotted black;
}

.hide {
    display:none;
}
```

```js
$(".menu .item .header").click(function() {
    if ($(this).next().hasClass("hide")) {
        $(this).next().removeClass("hide")
    } else {
        $(this).next().addClass("hide")
    }
})
```

