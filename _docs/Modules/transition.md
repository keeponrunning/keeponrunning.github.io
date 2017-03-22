---
title: transition
category: Modules
order: 4
---

概述
---

简单实现presentViewControler的方式来实现控制器之间的跳转


API
---

可用方法如下

#### 1. ***`present(options, callback)`***

弹出一个新的页面

##### 参数
 * `options `    (object): some options.
  * `url`  (string)

    新页面的链接（全路径），不能为空
  * `animated` (string)

    是否需要动画，默认有动画，可以为空
 
 * `callback`
  (object): the callback function after executing this action.
  
  
  
##### 返回参数结构定义

```json
{
  "code":"0000",
  "data": options,
}
```
* code
状态码

* data 
调用的时候所传过来的参数对象 



#### 2. ***`dismiss(options, callback)`***

关闭弹出的那个页面

##### 参数
 * `options `    (object): some options.
  
  想要传递的一些参数
 
 * `callback`
  (object): the callback function after executing this action.

##### 返回参数结构定义

```json
{
  "code":"0000",
  "data": options,
}
```
* code
状态码

* data 
调用的时候所传过来的参数对象 

-----

Usage
---

```javascript

//引入
var module = require('@weex-module/transition');

//打开新页面
//该对象不可为空，url必传(文件全路径)
var params = {
    'url': 'navigator-demo.js',
    'animated' : 'true',
}

module.present(params, function(res) {
  nativeLog(res.data) 
});

//关闭打开的页面
//该对象完全自定义传入，可不传
var params1 = {
    'status': '完成',
    'response':'2134567890',
}

module.dismiss(params1, function(res) {
  nativeLog(res.data) 
});

```