---
title: Vue笔记
tags: 前端,vue
renderNumberedHeading: true
grammar_cjkRuby: true
---

## 安装


----------

### CDN直接引用

- 开发环境
	- <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
- 生产环境
	- <script src="https://cdn.jsdelivr.net/npm/vue@2.6.11"></script>

----------

### 下载引入

 - 开发环境
	 - wget https://vuejs.org/js/vue.js
 - 生产环境
	 -  wget https://vuejs.org/js/vue.min.js


----------

### npm安装

### 安装nodejs
yum install -y nodejs
升级到最新版
curl -sL https://rpm.nodesource.com/setup_14.x | bash -

### 安装vue-cli

 - npm config set registry https://registry.npm.taobao.org/
 - npm install -g cnpm
 - cnpm install -g @vue/cli 


----------
## 语法
![语法思维导图](xmind/vue常用语法.png)
### 实例属性

 - el 挂载点，用于绑定一个dom元素及其所有子元素
 - data 数据，可以传对象或者函数，对象在el里面可以直接用{{}}引用，函数是组件化用的
 - methods 方法，用于写js函数，方便和dom事件绑定

## 流行框架
 - Vuetify

 
