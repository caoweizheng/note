# 事件 #
- 事件绑定方式
	- DOM节点绑定方式
		- 节点.on+事件名 = 事件处理函数
	- 事件监听器
		- 
## 鼠标事件 ##
- onclick 当用户点击某个对象时调用的事件。
- ondblclick 当用户双击某个对象时调用的事件。
- onmousedown 鼠标按钮被按下。
- onmouseup 鼠标按键被松开。
- onmouseover 鼠标移到某元素之上。
- onmouseout 鼠标从某元素移开。
- onmousemove 鼠标被移动时触发。
- onmouseenter 在鼠标光标从元素外部移动到元素范围之内时触发。这个事件不冒泡
- onmouseleave 在位于元素上方的鼠标光标移动到元素范围之外时触发。这个事件不冒泡，
- oncontextmenu 鼠标右键菜单展开时触发

	- PS：click = mousedown + mouseup, dblclick = click*2(短时间内两次单击);
	- 执行顺序：mouseover=>mouseenter; mouseout => mouseleave

## 键盘事件 ##

- onkeydown 某个键盘按键被按下。
- onkeyup 某个键盘按键被松开。
- onkeypress 键盘<字符键>被按下,而且如果按住不放的话，会重复触发此事件

## UI事件 ##

- onload 页面元素（包括图片多媒体等）加载完成后
- onscroll 滚动时触发。
- onresize 窗口或框架被重新调整大小

## 表单事件 ##

- onselect 输入框文本被选中。
- onblur 元素失去焦点时触发。
- onfocus 元素获得焦点时触发。
- onchange 元素内容被改变，且失去焦点时触发。
- onreset 重置按钮被点击。
- onsubmit 确认按钮被点击。
- oninput 输入字符时触发。

## Event对象 ##
- w3c
	- 事件处理函数的第一个参数
- ie8-
	- window.event
- 兼容
	- if(e===undefined)(e = window.event)
	- e = e ? e : window.event
	- e = e || window.evnet
- 事件执行过程中的状态，用来保存当前事件的信息对象
	- 鼠标按钮被点击时
		- event.button
			- 0:代表鼠标按下了左键
			- 1:代表按下了滚轮
			- 2:代表按下了右键
		- document.mousedown = function(event){}
	- 键盘被按下时
		- event.keyCode/event.which
			- keypress
				- 按下的键生成的ascii码
			- keydown/keyup
				- 按下的键的虚拟键盘码。可能跟键盘的布局相关
		- document.keydown = function(event){}

	- altKey
		-  返回当事件被触发时，ALT 键是否被按下。
		- event.altKey == true 表示按下alt
	- ctrlKey 返回当事件被触发时，CTRL 键是否被按下。
	- shiftKey 返回当事件被触发时，Shift 键是否被按下
	
	- 光标位置信息
		- clientX /clientY 光标相对于浏览器可视区域的位置，也就是浏览器坐标。
		- screenX/screenY 光标指针相对于电脑屏幕的水平/垂直坐标。
		- pageX/pageY:鼠标相对于文档的位置
		- 包括滚动条滚动的距离，即：clientX+window.scrollX
		- IE8-不支持
		- offsetX,offsetY: 光标相对于事件源对象的相对偏移量。
		- 事件源对象：触发事件的对象
- 事件传播
	- 事件冒泡
		- 从下到上
	- 事件捕获
		- 从上到下

## 事件冒泡 ##
- 事件源对象
	- 触发事件的初始元素
	- event.target
- 兼容问题
	- 标准：target
	- ie8-:srcElement
	- 解决方法
		- var target = e.target || e.srcElement;

## 停止事件冒泡 ##
- event.stopPropagation()
- 兼容
	- w3c:event.stopPropagation()
	- ie8-:event.vancelBubble = true;
	- 解决
		- e.stopPropagation ? e.stopPropagation : e.cancelBubble = true;
## 事件捕获 ##



- 影响页面性能的操作
	- 1.事件数量
		- 处理方式
			- 事件委托
				- 把本来绑定给某个元素的事件委托给它的父级元素（已经存在页面）来处理
	- 2.DOM频繁操作
	- 3.请求资源数量
