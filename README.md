# webclipboard
浏览器复制功能
=================


原理：创建一个input元素，然后将内容设置到这个input上面，再执行copy
 --------------------
 
``` javascript
function OnCopy(eve)
{
    var text = $("#id-input").val();
    // 创建一个输入框
    var hide_input = $("<input id='id-input-copy-9527' type='text'></input>");
    hide_input.val(text);
    $(document).find("body").append(hide_input);
   hide_input.select();
   document.execCommand("Copy",null); // 执行浏览器复制命令
   $("#id-input-copy-9527").remove();
   alert('复制成功');
}
``` 

``` html
<div>
    <label>复制的例子:</label>
    <input type="text" id="id-input">
    <a href="javascript:void(0);" onclick="OnCopy(this)">点击复制</a>
</div>
```
