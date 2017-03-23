---
title: touchID
category: Modules
order: 13
status: dev
---


概述
---

调用系统的指纹认证功能，用来在一些密码输入的地方做处理


API
---

可用方法如下

#### 1. ***`deviceSupportTouchID(callBack)`***

判断设备是否支持ToucID验证

##### 参数
  
* `callBack ` 回调

##### 返回参数
```json
{
  "code":"0000",
  "data":"设备支持TouchID验证"
}

```

#### 2. ***`touchIDAuth(callBack)`***

校验TouchID

##### 参数
  
* `callBack ` 回调

##### 返回参数
```json
{
  "code":"0000",
  "data":"验证TouchID通过"
}

```

Usage
---

```javascript

var touchIdModule = require('@weex-module/touchID');

//获取设备是否支持
touchIdModule.deviceSupportTouchID(function(res) {
  if (res.code === '0000') {
    nativeLog('设备支持TouchID验证');
  }else{
    ///......
  }
});

//验证TouchID
touchIdModule.touchIDAuth(function(res) {
  if (res.code === '0000') {
    nativeLog('TouchID验证通过');
  }else{
    
  }
});


```

TouchID验证错误码
---


|序号|错误码|错误描述|
|:---|:---:|:---:|
|1|28001|TouchID验证不通过|
|2|28002|用户取消了TouchID验证|
|3|28003|用户不想进行TouchID验证，想进行输入密码操作|
|4|28004|系统终止了TouchID验证|
|5|28005|用户没有在设备Settings中设定密码|
|6|28006|设备TouchID不可用|
|7|28007|设备没有进行TouchID指纹注册|
