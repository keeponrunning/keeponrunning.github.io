---
title: location
category: Modules
order: 7
---


概述
---

打开定位获取经纬度以及具体位置信息

API
---
可用方法如下

#### 1. ***getLocation(callBack)***

获取位置信息

##### 参数
  
* `callBack`

  获取位置之后的wx回调

##### 返回参数

```json

{
  "code":"0000",
  "data": {
    "latitude":"31.214852",         //经纬度
    "longitude":"121.596372",
    "country":"中国",                 //国家
    "locality":"上海市",              //城市
    "subLocality":"浦东新区",         //区
    "thoroughfare":"金科路",          //街道
    "subThoroughfare":"2557号",      //子街道
  }
}

```

Usage
---

```javascript
//引入
var location = require('@weex-module/location');

location.getLocation(function(res) {
  nativeLog(res.data)
});

```

