# HTML

## 标签

### 块标签

 占一整行的标签，宽高属性生效，默认100%宽度，高度按宽度等比例伸缩，如div，ul，li

强制转换为块标签：display:block

### 行内标签

内容有多大就占多大的标签，不会占一整行，宽高属性不生效。如span，a

强制转换行内块标签：display:inline

#### a

默认当前页面跳转，如果想新开一个tab页跳转，要使用target="_blank" 

#### select

和option一起组成单选下拉框，如果要多选，加上muitiple。通过value来指定向表单提交的值。

demo如下

```html
<select>
    <option>北京</option>
    <option>上海</option>
    <option>广州</option>
</select>
```

### 行内块标签

结合行内标签和块标签的优点，对宽高属性生效，且可以多个标签存在一行，如img，input，textarea

强制转换为行内块标签：display:inline-block

#### input

type为**radio**时，通过**相同的name属性**来确定属于同一个**单选项**，通过value来指定向表单提交的值

type为**checkbox**时，通过**相同的name属性**来确定属于同一个**多选项**，通过value来指定向表单提交的值

type为**file**时，浏览器自动识别为**选择文件上传**

type为**button**时，浏览器识别为**按钮**，为**submit**时，浏览器识别为**表单提交按钮**

## 请求

### GET请求

传输的数据显示在url上

### POST请求

传输的数据不显示在url上，藏在请求体中，表单提交默认post请求

## 表单

### form标签

form标签的method属性指定请求方法，action属性指定请求url,如果url中没有ip和端口只有uri，默认是当前页面的ip和端口。如果不填action,则默认为当前url。

表单内input，textarea，select标签必须用name属性来标识字段名

### submit按钮

submit只提交form表单内的数据