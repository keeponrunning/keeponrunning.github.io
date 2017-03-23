---
title: share
category: Modules
order: 9
status: dev
---


概述
---

调用手机系统原生的分享功能

API
---

可用方法如下

#### 1.***`share(contentText，callBack)`***

分享文本

##### 参数
  
* `contentText `

  文本的内容

##### 返回参数
```json
{
  "code":"0000",
  "data":"分享成功"
}

```

#### 2.***`shareImage(imageUrl，callBack)`***

分享图片

##### 参数
  
* `imageUrl `

   图片URL地址



##### 返回参数
```json
{
  "code":"0000",
  "data":"分享成功"
}

```



Usage
---

```javascript
//引入
var module = require('@weex-module/share');

//分享文本
module.share("分享的内容"，function(res) {
  nativeLog(res.data)
});

//分享图片
module.shareImage("https://image...",function(res) {
  nativeLog(res.data)
});

```

