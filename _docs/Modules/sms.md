---
title: sms
category: Modules
order: 11
---


概述
---

调用手机发送短信功能

API
---
可用方法如下

#### 1. ***`sendSMS(content, callback)`***

给指定的手机号发送短信，短信界面不需要选择接收人

##### 参数
  
* `content`

  短信内容

* `callback`
	
	回调

#### 2. ***`sendSMS(content, phoneNo, callback)`***

发送短信，到短信页面去选择发送对象

##### 参数
  
* `content`

  短信内容

* `phoneNo`

	短信接收者的手机号

* `callback`
	
	回调




Usage
---

```javascript
//引入
var module = require('@weex-module/sms');

//发送短信
module.sendSMS("发送的内容", function(res) {
  nativeLog(res.data)
});

//发送短信给指定人
module.sendSMS("发送的内容", "15121178175", function(res) {
  nativeLog(res.data)
});

```