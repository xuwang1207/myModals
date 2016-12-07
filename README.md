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
```
- parameters - object. Modal 的 parameters/options对象

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
