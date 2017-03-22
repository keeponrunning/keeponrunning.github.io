---
title: camera
category: Modules
order: 10
---


概述
---

调用手机拍照功能和从相册选择照片

API
---

可用方法如下

#### 1. ***capturePhoto(callBack)***

拍照

##### 参数
  
* `callBack `


##### 返回参数
返回 base64的字符串

```json
{
  "code":"0000",
  "data":"base64字符串"
}

```

#### 2. ***selectPhoto(callBack)***

从相机里选择照片

##### 参数
  
* `callBack `



##### 返回参数

返回base64的字符串

```json
{
  "code":"0000",
  "data":"base64字符串"
}

```



Usage
---

```javascript
//引入
var module = require('@weex-module/camera');

//拍照
module.capturePhoto(function(res) {
  nativeLog(res.data)
});


//从相机选择照片
module.selectPhoto(function(res) {
  nativeLog(res.data)
});

```

