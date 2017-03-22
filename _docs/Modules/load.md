---
title: load
category: Modules
order: 2
---


概述
---

在经过一段时间的开发以及测试发现，完全运用远程链接的方式去加载并渲染一个页面，相当耗费用户流量以及时间，因为每次渲染都会去重新下载该js文件并下载页面中所用到的所有资源（图片、字体等）。所以我们通过讨论想出一种解决方式，通过本地存储一份web的js文件以及所用到的其他资源文件，然后在js跳转新页面以及加载资源的时候调用本地的文件，这样可以保证所有的资源都是通过本地化的方式来加载；如果文件在本地已存在，则直接加载本地文件，否则native这边去下载资源到本地，并返回本地路径给到web那边，这样做的好处就是既节省了时间成本，也相应的提高了用户体验（本地加载比远程快的不是一星半点）。所以我们这个模块`load`也就应运而生了。


API
---

可用方法如下

#### ***1. `getUrlPath(sring urlStr, callback)`***

根据远程连接获取该文件的本地绝对路径

##### 参数
 * `urlStr `
  
  文件远程连接地址，必传
  
##### 返回参数结构定义

```json
{
  "code":"0000",
  "data":"file:///xxxxx/JFFolder/homeIcon.png"
}

```
* data 

  文件本地连接地址
  
#### ***2. `getRoutePath(string key, callback)`***

根据模块的Key值,获取路由绝对路径

##### 参数
 * `key `
  
  js文件对应的Key值，必传
  
##### 返回参数结构定义

```json
{
  "code":"0000",
  "data":"file:///xxxxx/JFFolder/home.js"
}

```
* data 

  本地js文件的绝对路径地址 




Usage
---

```javascript
//引入
var loadPath = require('@weex-module/load');

//调用资源下载
var fileUrl = "http://www.jfpal.com/index.js"
loadPath.getUrlPath(fileUrl, function(res) {
  nativeLog(res.data) 
  //file:///User/dadasdasd/IMAGEFolder/homeIcon.png
});

//获取路由文件全路径
loadPath.getRoutePath('keyStr', function(res) {
  nativeLog(res.data) 
  //file:///User/dadasdasd/JSFolder/index.js
});

```


