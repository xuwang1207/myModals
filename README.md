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
