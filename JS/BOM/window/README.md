用于和用户交互的三个函数

* alert：弹窗，没有返回值，在没有点击确定或关闭之前，阻止其他操作

```
window.alert('弹窗中显示的值');
```

![](/assets/window_alert.png)

* prompt：弹窗，返回用户输入的值，在没有点击确定或关闭之前，阻止其他操作
  * 点确定时：没有输入返回空字符串，否则返回输入的值
  * 点取消，返回null

```
var a = prompt('弹框中显示的值')
```

![](/assets/window_prompt.png)

![](/assets/window_prompt2.png)

* confirm：弹框，返回用户的选项，确定返回true，取消返回false

![](/assets/window_confirm.png)

