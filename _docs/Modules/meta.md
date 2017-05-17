---
title: meta
category: Modules
order: 3
---


概述
---

动态化配置一些页面属性，该属性的集合从服务端获取，由`native`存储并提供给`web`使用

API
---

可用方法如下

#### 1. ***`getSourceMeta(key ,callback)`***

获取某个单页的meta信息

##### 参数
 * `key `

  页面对应的key值，必传,(可能是页面名(pageName))

##### 返回参数结构定义

```json
{
  "code":"0000",
  "data":{},  
}

```
***PS：data里面的数据依据实际情况而定***

#### 2.***`refreshSourceMeta(callback)`***

刷新这个meta信息

##### 返回参数结构定义

```json
{
  "code":"0000",
  "data":{},  
}

```

Usage
---

```javascript
//引入
const metamodule = weex.requireModule('meta');

//获取meta信息
metamodule.getSourceMeta('pageName' ,function(res) {
  nativeLog(res.data)
});

//刷新meta数据
metamodule.refreshSourceMeta(function(res) {
  nativeLog(res.data)
});

```
