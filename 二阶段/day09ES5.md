# ECMAScript5 #
## 页面加载事件 ##
- 页面加载步骤
	- 1.解析HTML结构
	- 2.加载外部脚本和样式表文件
	- 3.解析并执行脚本代码
	- 4.DOM树构建完成 //DOMContentLoaded
	- 5.加载图片等外部文件
	- 6.页面加载文件  // window.onload
- onreadystatechange
	-  第四第六步都会执行
		-  第四步
		-  document.readyState ==interactive
		-  第六步
		-  document.readyState ==complete

- DOMContentLoaded
	- 第四步完成之后执行
	- 必须使用事件监听器绑定

- 严格模式(ES5)
	- 'use strict'
	- 全局
		- script标签开头
		- js文件的开头
	- 局部
		- 函数开头
	- 严格模式下的限制
		- 不使用var声明变量严格模式下不通过

## bind ##
- fn(){}.bind(obj)
- 不会执行fn
- 用于将当前函数和指定的函数绑定（改变this指向），返回一个新的函数
## 类名操作 ##
- ![](https://i.imgur.com/c1ZS0zO.png)
- el.classList
	- add()
		- 添加类名
	- remove()
		- 删除类名
	- contains()
		- 判断是否包含某个类
	- toggle()
		- 切换类名
			
				<div class="box"></div>
				var box = querySelector('.box');
				box.classList.add('box1');
				box.classList.remove('box1');
				box.classList.contains('box1');
				box.classList.toggle('box1');

## 自定义属性操作 ##
- dataset()
	- 保存所有自定义属性的数据
	
			<div class="box" data-name='cc' data-age='18'></div>
			var box = querySelector('.box');
			console.log(box.dataset.name);// cc
