---
title: jump
category: Modules
order: 1
status: dev
---


概述
---

有时候我们需要native做一些静态的不会变的页面，当我们需要跳转到该native页面时，需要一个桥来处理这个跳转，这里是一系列的跳转（跳转到native静态页面）。

还有一种就是一个用自定义的webview打开一个链接url，这个时候也需要做一些桥的处理。

还有另外一种是直接用系统浏览器打开一个url。

调用系统-拨打电话、发送邮件、打开通讯录。

API
---

可用方法如下

#### 1. ***`openUrlInWebView(url)`***

用自定义的webView打开url

##### 参数定义
* `url `

需要打开的链接




Usage
---

```javascript
//引入
var jumpmoudle = require('@weex-module/jump');

//1.openUrlInWebView
jumpmoudle.openUrlInWebView("http://www.baidu.com",function(e) {
  nativeLog(e);
});

```
