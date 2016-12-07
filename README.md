# myModals
从 [SUI Mobile](http://m.sui.taobao.org/) 中精简出对话框、加载提示器、toast三个HTML5常用控件

##Alert
```
$.alert(text, [title, callbackOk]) 
或者
$.alert(text, [callbackOk])
```
- text - string. Alert文本
- title - string. Optional. Alert modal 标题
- callbackOk - function. Optional.在Alert modal下，当用户点击“Ok”按钮时，回调函数将被执行。

##Confirm
```
$.confirm(text, [title, callbackOk, callbackCancel])
或者 
$.confirm(text, [callbackOk, callbackCancel])
```
- text - string. Confirm 文本
- title - string. Optional. Confirm modal 标题
- callbackOk - function. Optional. 在 Confirm modal下，当用户点击“Ok”按钮时，回调函数将被执行。(当用户确认操作）
- callbackCancel - function. Optional. 在 Confirm modal下，当用户点击“Cancel”按钮时，回调函数将被执行。(当用户不想进行操作)

##Prompt
```
$.prompt(text, [title, callbackOk, callbackCancel])
或者
$.prompt(text, [callbackOk, callbackCancel])
```
- text - string. Prompt 文本/问题
- title - string. Optional. Prompt modal 标题
- callbackOk - function. Optional. 在 Prompt modal下，当用户点击“Ok”按钮时，回调函数将被执行。回调函数的参数是输入框的值
- callbackCancel - function. Optional. 在 Prompt modal下，当用户点击“Cancel”按钮时，回调函数将被执行。回调函数的参数是输入框的值

##自定义Modal
```
$.modal(parameters) - 显示 custom modal
$.closeModal(modal) - 关闭任意 modal
```
- parameters - object. Modal 的 parameters/options对象
- modal - HTMLElement or string ( CSS 选择器). 可选. 除了指定的，任何被打开modal都将被关闭。

|参数|类型|默认值|	描述|
|:-------------:|:-------------:|:-------------:|:-------------|
|title|	字符串|		|可选. Modal 标题 (可以是html字符串)|
|ext|	字符串	|	|可选. Modal 文本 (可以是html字符串)|
|afterText|	字符串|		|可选. 将被放在"text"后的文本 (可以是html字符串)|
|buttons|	数组	|	| 可选.按钮数组. 每个按钮应该被表示为带按钮参数的对象 (看下面)|
|extraClass|	字符串|		|可选. 给modal的根节点.modal附加1或多个自定义class(如'bg-red','bg-blue share-type')，方便按需定制不同的modal样式。|
|verticalButtons|	boolean|	false|	Optional. Set to true to enable vertical buttons layout|
|onClick	|函数|		|可选.回调函数将在用户点击任何Modal按钮后被触发执行. 它接收 modal (Modal的 HTML元素) 和 index作为参数 (被点击按钮的索引号)|

让我们一起来看看按钮参数:

|参数|	类型|	默认值|	描述|
|:-------------:|:-------------:|:-------------:|:-------------|
|text	|字符串|		|按钮文本 (可以是 HTML 字符串)|
|bold	|布尔值|	false	|可选. 设置为true会加粗按钮文本|
|close	|布尔值|	true|	可选. 如果是“true”，点击这个按钮后modal会被关闭|
|onClick	|函数|		|可选. 用户点击这个按钮后，回调函数会被执行|

##带标题的加载指示器showPreloader
```
$.showPreloader([title])- 显示 预加载 modal
$.showPreloader() - 隐藏/关闭 预加载 modal. 因为 预加载 modal 没有任何按钮, 它应该用 JavaScript 来关闭
```
- title - string. Optional. 预加载 modal 标题. 默认（没有指定）的时候，它等同于 "Loading...". 你可以在App初始化时通过 modal预加载Title 参数改变默认的 预加载 标题。

##迷你指示器showIndicator

> 如果你不需要用像预加载Modal这样如此大的modal 窗口去指示活动, 你可以使用简单并且小的指示器modal:

```
$.showIndicator() - 显示指示器 modal
$.hideIndicator() - 隐藏/关闭指示器 modal. 因为指示器modal没有任何按钮, 它需要用JavaScript来关闭
```

##toast

> toast是一种轻量的提示，在页面中间显示，并且会在2秒(默认值，可修改)之后自动消失。可以用来显示一些不会打断用户操作的提示。

```
/* msg{string}: toast内容
 * duration{number}：toast显示时间,默认2000
 * extraclass{string}：给toast根节点附加class，高度自定义属性，方便用户自行控制不同场景的样式。
 * 如果使用了第三个参数，请自行在业务css里添加extraclass对应的样式
 * /
 ```
