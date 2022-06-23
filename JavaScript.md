# JavaScript

## 概述

javascript是一门动态编程语言，浏览器是它的解释器。主要用于实现动态效果。

### 引用js

#### 在body最底端

推荐放在body最底端。html是从上到下解析的，假如耗时的js在head中引入，就会导致浏览器先执行js，再渲染网页，导致渲染慢。

```html
<script src="static/js/js.js"></script>
</body>
```

#### 在head中引用

```html
<head>
    <meta charset="UTF-8">
    <title>JS</title>
    <script>
        function demo() {
            alert("hi");
        }
    </script>
</head>
```

## 基础

### 变量

```js
//声明变量
var name = "demo"
console.log(name)
//常用功能
name.length
name[0]
//去除字符串前后的空格
name.trim()
name.substring(0,2) //字符串切片，前取后不取

//声明数组
var arr = [11,22,33]
arr[0] = 44
arr.push(55) //在数组末尾添加55这个元素
arr.unshift(11)  //在数组开头插入11这个元素
arr.splice(1,0,'456')  //将456插入到数组的第1个位置，即arr[1],后面的元素自动后退一格
arr.pop()  //尾部删除
arr.shift()  //头部删除
arr.splice(0,1)   //删除arr[0]

var info = {
    name: "de",
    age: 18
}
info.age = 19
delete info["age"]
```

### 逻辑控制

```js
var arr = [4,5,6]
//for循环
for (var index in arr) {
    // 循环打印索引，如果要操作数组中的元素，用arr[index]
    console.log(index)
}
for (var i=0;i<arr.length;i++) {
    //do something，也可以用break和continue
}

//条件控制
if () {
    //
} else if {
    //
} else {
    //
}
```

## DOM(Document)

可以将js中的dom理解为一个模块，这个模块的功能就是操作html标签

```js
//加载动态数据
var dataList = [{id: 1,name: "demo",age: 18},
    {id: 1,name: "demo",age: 18},
    {id: 1,name: "demo",age: 18}]
//获取id为body的tbody标签
tbody=document.getElementById("body")
for(var idx in dataList) {
    //创建tr标签
    var tr=document.createElement("tr")
    for(var key in dataList[idx]){
        //创建td标签
        var td=document.createElement("td")
        //将数据填充到td标签中
        td.innerText=dataList[idx][key]
        //将td添加到tr
        tr.appendChild(td)
    }
    //在tbody下添加tr
    tbody.appendChild(tr)
}
```



## 事件绑定

### 点击绑定

```html
<div class="header" onclick="demo()">标题</div>
```

