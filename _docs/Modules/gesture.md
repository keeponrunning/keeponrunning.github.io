---
title: gesture
category: Modules
order: 14
---


概述
---

一个简单的手势密码验证组件

API
---

可用方法如下

#### 1. ***`setGesture(userKey, callBack)`***

设置（开启）手势密码

##### 参数

* `userKey `
  
  标识用户唯一性的参数，方便区分不同用户的手势密码
* `callBack ` 回调
  

##### 返回参数
```
{
  "code":"0000",
  "data":"密码具体信息"
}
```

#### 2. ***`checkGesture(userKey, callBack)`***

验证手势密码（重新打开APP可能会调用、进入后台再次回到前台可能会调用）

#### 参数

* `userKey `
  
  标识用户唯一性的参数，方便区分不同用户的手势密码
* `callBack ` 回调
  

#### 返回参数
```
{
  "code":"0000",
  "data":"密码具体信息"
}
```

#### 3. ***`resetGesture(userKey, callBack)`***

重置手势密码，一般重置手势密码需要先输入登录数字密码，再调用该方法来重新设置密码，所以这个地方可能会和业务有些耦合性需要去经一部优化。（忘记密码调用该方法）

##### 参数

* `userKey `
  
  标识用户唯一性的参数，方便区分不同用户的手势密码
* `callBack ` 回调
  

##### 返回参数

```
{
  "code":"0000",
  "data":"新密码具体信息"
}
```

#### 4. ***`alterGesture(userKey, callBack)`***

修改手势密码

##### 参数

* `userKey `
  
  标识用户唯一性的参数，方便区分不同用户的手势密码
* `callBack ` 回调
  

##### 返回参数
```
{
  "code":"0000",
  "data":"新密码具体信息"
}
```

#### 5. ***`deleteGesture(userKey, callBack)`***

删除（关闭）手势密码，该方法不一定需要调用，根据具体情况而定。如果需要清除的话，可调用

##### 参数

* `userKey `
  
  标识用户唯一性的参数，方便区分不同用户的手势密码
* `callBack ` 回调
  

##### 返回参数
```
{
  "code":"0000",
  "data":"密码删除成功"
}
```


Usage
-----

```javascript

var gestureModule = require('@weex-module/gesture');

//1、设置（开启）手势密码
gestureModule.setGesture('15121178175', function(res) {
  if (res.code === '0000') {
    nativeLog('手势密码设置成功');
  }else {
    native.log(res.data);
  }
});

//2、验证手势密码
gestureModule.checkGesture('15121178175', function(res) {
  if (res.code === '0000') {
    nativeLog('手势密码验证成功');
  }else {
    native.log(res.data);
  }
});

//3、重置手势密码（忘记密码也调用该方法）
gestureModule.resetGesture('15121178175', function(res) {
  if (res.code === '0000') {
    nativeLog('手势密码重置成功');
  }else {
    native.log(res.data);
  }
});

//修改手势密码
gestureModule.alterGesture('15121178175', function(res) {
  if (res.code === '0000') {
    nativeLog('手势密码修改成功');
  }else {
    native.log(res.data);
  }
});

//删除手势密码
gestureModule.deleteGesture('15121178175', function(res) {
  if (res.code === '0000') {
    nativeLog('手势密码删除成功');
  }else {
    native.log(res.data);
  }
});


```