# BootStrap

## 概述

可以简单理解为已经写好的css样式文件

## 部署

### 下载

点击[链接](https://objects.githubusercontent.com/github-production-release-asset-2e65be/2126244/bd152f10-d98d-464c-b679-733913aafbaa?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20220620%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20220620T131042Z&X-Amz-Expires=300&X-Amz-Signature=39b0c9e03f9d14d50bc8b309d41d41d924c9419cb43b0e83401816c4c196a9cb&X-Amz-SignedHeaders=host&actor_id=18628255&key_id=0&repo_id=2126244&response-content-disposition=attachment%3B%20filename%3Dbootstrap-5.2.0-beta1-dist.zip&response-content-type=application%2Foctet-stream)下载预编译好的BootStrap **v5.2.0-beta1** 压缩包，也可以去[BootStrap官网](https://getbootstrap.com/)自行下载最新版BootStrap

### 引用

在html的link标签中引用解压后的bootstrap.css，demo如下。

```html
<!--    开发环境版本  -->
<link rel="stylesheet" href="static/plugins/bootstrap/css/bootstrap.css">
<script src="static/plugins/bootstrap/js/bootstrap.bundle.js"></script>
<!--    生产环境版本  -->
<link rel="stylesheet" href="static/plugins/bootstrap/css/bootstrap.min.css">
```

生产环境版本因为删除了大量的换行符，文件更小，但是可读性更差。一般开发时用开发版，上线时换成生产环境版本

## 用法

在[网站](https://v5.bootcss.com/docs/components/navbar/)上寻找想要的组件的效果，然后拷贝到自己的代码中，再在chrome的开发者工具上按照需求微调，自己写css来实现期望的效果

### 导航

https://v5.bootcss.com/docs/components/navbar/

### 栅格 grid

#### 响应式

根据屏幕宽度不同，做不同响应

开始是堆叠在一起的，当页面大于某个阈值时变成水平排列

col-sm-* col-md-* col-lg-*

sm，md和lg的区别：触发水平排列的阈值不一样 sm 540px md 720px lg 960px

#### 非响应式

总是水平排列

class col-xs-*

#### 列偏移

往右移动若干个格

col-sm-offset-*



