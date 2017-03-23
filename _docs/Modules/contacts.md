---
title: contacts
category: Modules
order: 6
status: dev
---


概述
---

弹出手机联系人选择界面，选择联系人，然后将该联系人姓名以及手机号码返回到`web`


API
---
可用方法如下

#### 1. ***`pickContact(callBack)`***

选择并获取联系人信息

##### 参数
  
* `callBack`

  请求结束之后的回调 

##### 返回参数结构定义

```json

{
  "code":"0000",
  "data": [
        {
            name = "\U7238";
            phone = 18706115419;
        },
        ...
    ];  
}

```
  请求返回的具体参数，为一个对象（包含姓名和手机号）数组


*PS：如果联系人无号码，则返回`code`为`'2003'`,`data`为一个空数组*


Usage
---

```javascript
//引入
var module = require('@weex-module/contacts');

module.pickContact(function(res) {
  nativeLog(res.data)
});

```
