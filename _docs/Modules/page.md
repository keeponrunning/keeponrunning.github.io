---
title: page
category: Modules
order: 5
status: dev
---


概述
---

对页面做相关的操作，比如刷新渲染页、关闭当前页的编辑状态（收起键盘）。

在某些特定的情况下（比如说更换皮肤），需要重新刷新(渲染)整个页面，所以需要我们提供接口来刷新整个渲染页。

API
---

可用方法如下

#### 1. ***`refreshPage()`***

刷新渲染页

##### 参数

无
  
##### 返回参数

无

#### 2. ***`popToRootPage(callBack)`***

页面跳转示例: RootPage ->  Apage -> Bpage ->Cpage


在Cpage中调用 popToRootPage方法 即可关闭 Apage，Bpage，Cpage，返回到 RootPage

##### 参数
  
* `callBack `

  

##### 返回参数
```json
{
  "code":"0000",
  "data":""
}

```

#### 3.***`closeKeyboard()`***

关闭当前页面的键盘，无参数，无回调



Usage
---

```javascript
//引入
const ddrefresh = weex.requireModule('page');

//刷新
ddrefresh.refreshPage()

//pop回到root
module.popToRootPage(function(res) {
  nativeLog(res.data)
});

//关闭键盘
module.closeKeyboard();


```

