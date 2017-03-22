---
title: secrityinput
category: Components
order: 1
---

安全键盘组件的实现


`<ddsecrityinput>`
------

#### 思路:
在input组件的基础下做些修改，将自有的`secritykeyboard`绑定到`ddsecrityinput`组件上面。
#### 方法:
在原有的基础下扩充一种type类型（`ddpassword`），其他的处理方式与原有的保持一致。仍然支持input组件所拥有的所有属性的使用。

#### 定义
* 组件名(name)：`ddsecrityinput`


#### 新增类型

* `ddpassword`
  
即付密码键盘  
* `number`
  
带小数点的数字键盘，仅能输入数字和小数点

#### 新增扩展属性

* `clearmode`
  * iOS端`UITextField`所拥有的`clearButtonMode`属性的简单设置， 在官方提供的input里面未包含该属性的设置方法。
  * 可设置的value（设置小按钮的显示时间）如下：
    * `always`
       一直显示
    * `whileedit`
      开始输入的时候显示
    * `endedit`
      结束输入的时候显示
  * 支持所有type的ddsecrityinput


* `random`
  * 安全键盘上面数字、字母符号显示顺序的随机性
  * `true`
    表示打乱顺序
  * `false`
    表示不打乱顺序
  * 需要注意一点，`random`属性只对type为`ddpassword`的`ddsecrityinput`起作用，其他type均无任何效果

* `maxlength`属性仅作用于数字键盘，用于做银行卡密码的校验,设置`maxlength`后无法切换到字母键盘以及符号键盘

* `cursorcolor`   new add by 2017年2月20日

设置输入框内部的光标颜色，支持16进制颜色；例如`"cursorcolor"="#51b0d6"`,需要写在标签头

* 其他属性与官方[input](http://alibaba.github.io/weex/cn/doc/components/input.html)一致,全部支持


一个简单例子：

 ```html
 <ddsecrityinput
  class="secrityinput"
  type="ddpassword"
  clearmode="whileedit"
  autofocus="false"
  random="true"
  placeholder="请输入用户名以及密码"
  onChange="onchange"
  onInput="onInput">
 </ddsecrityinput>

 ```

#### ***PS:需要注意一点***


使用该组件的时候，写法需要注意一下，必须要 
```<ddsecrityinput type="ddpassword">
</ddsecrityinput>```写.
而不能```<ddsecrityinput type="ddpassword" />```
