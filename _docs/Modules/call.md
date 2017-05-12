---
title: call
category: Modules
order: 12
status: dev
---


概述
---

调用手机拨打电话功能


API
---

可用方法如下

#### 1. ***`callTel(telNo)`***

拨打电话

##### 参数
  
* `telNo `

  电话号码


Usage
---

```javascript
//引入
const module = weex.requireModule('module');

//拨打电话
module.callTel("10086");

```