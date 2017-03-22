---
title: loading
category: Modules
order: 8
---

概述
---

调用原生loadingview（加载资源过渡用的loading），可以供web调用

API
---
可用方法如下

#### 1. ***`show(text, callBack)`***

显示原生loadview

##### 参数
  
* `text`

	loading时要提示的文字

* `callBack `
	
	回调

##### 返回参数

是否show成功

```json
{
  "code":"0000",
  "data":""
}

```
	

#### 2. ***`dismiss(callBack)`***

关闭原生loadview

##### 参数
  
* `callBack`

	回调

##### 返回参数

是否dismiss成功

```json
{
  "code":"0000",
  "data":""
}

```


Usage
---

```javascript
//引入
var loading = require('@weex-module/loading');

//显示loading
loading.show('请稍候...', function(res) {
  nativeLog(res.data)
});

//隐藏loading
loading.dismiss(function(res) {
  nativeLog(res.data)
});

```

