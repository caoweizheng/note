# DOM #
- DOM是Document Object Model（文档对象模型）的缩写，它是W3C国际组织的一套Web标准。是针对HTML和XML文档的一个API，它定义了访问HTML文档对象的一套属性、方法和事件
![](https://i.imgur.com/kIhRZyA.png)
## 节点类型 ##
- 每个节点都有一个nodeType属性，用于表明节点的类型
	- 元素节点
		- 1
	- 属性节点
		- 2
	- 文本节点
		- 3
### 节点获取 ###
- querySelector('css选择器');
	- 获取匹配到的第一个元素节点，返回DOM节点
- querySelectorAll('css选择器')
	- 获取匹配到的所有元素节点，返回DOM类数组
- document.getElementById(id);
	- 速度最快
	- 必须通过document获取
	- 返回DOM 节点对象，如果id不存在返回null
- getElementsByTagName(tagName)
	- 通过标签名获取元素节点列表
	- 返回类数组，如果tagName不存在返回空数组[]
	- 可以小范围获取
- getElementsByClassName('clsName')
	- 通过class类名获取节点列表
	- 必须通过document获取
	- 返回类数组，如果clsName不存在返回空数组[]
	- 可以小范围获取
- 获取表单元素
	- doucument.getElementByName
- document.links
	- 获取页面上的所有a节点
- document.images
	- 获取页面上的所有img节点
	
### 节点属性 ###
- nodeName
	- 根据其类型，返回节点的名称。
- nodeType
	- 返回节点的类型
- nodeValue
	- 返回节点的值
		- 元素节点的nodeValue为null
### 节点方法 ###
- 创建
	- domument.createElement(ele);
		- 创建一个元素节点
	- document.createTexNode(txt)
		- 创建一个文本节点
	- document.createAttribute(attr)
		- 创建一个属性节点
- 插入
	- paent.appendChild(el);
		- 向parent节点列表的结尾添加新的子节点
		- 如果el已经存在则移动el为parent的最后一个子元素
	- parent.insertBefore(new,node)
		- 在指定的子节点node前插入新的子节点new。
		- ele.setAttributeNode(attrNode) 
			- 在指定元素中插入一个属性节点（了解）
				- 对页面已存在节点的处理
- 复制
	- el.cloneNode(boolean);
		- 复制节点，参数为true是深复制
- 删除
	- parent.removeChild(ele)
		- 删除(并返回)当前节点parent的指定节点ele
- 判断
	- parent.hasChildNodes(ele)
		- 判断当前节点是否拥有子节点，返回布尔值

## 利用节点关系获取其他节点(可能得到元素节点||文本节点) ##
- 获取父节点
	- el.parentNode;
		- 得到el元素的父节点 （所有节点---eg:document??）
			- ES5
				- el.parentElement（元素节点）
- 获取子节点（子元素之间有空格或换行会得到文本节点）
	- el.childNodes
		- 获取到el所有的子节点(类数组)
			- ES5 
				-  el.children（良好兼容）
	- el.firstChild
		- 获取el元素的第一个子节点
			- ES5
				- el.firstElementChild
	- el.firstChild
		- 获取el元素的最后一个子节点
			- ES5
				- el.lastElementChild
- 获取兄弟节点
	- ele.nextSibling
		- 得到ele元素的下一个兄弟节点
			- ES5
				- el.nextElementSibling
	- ele.previousSibling
		- 得到ele元素的上一个兄弟节点
			- ES5
				- el.previousElementSibling

## 常用属性 ##
- tagName 获取元素元素的标签名
- id 设置/获取元素id属性
- name 设置/获取元素name属性
- style 设置/获取元素的内联样式
- className 设置/获取元素的class属性
- innerHTML 设置/获取元素的内容（包含html代码）
- outerHTML 设置或获取元素及其内容（包含html代码）
- innerText 设置或获取位于元素标签内的文本
- outerText 设置(包括标签)或获取(不包括标签)元素的文本

## 盒模型相关 ##
- offsetTop: 当前元素离<定位父级>元素顶部的距离。
- offsetLeft: 当前元素离<定位父级>元素左边的距离。	
	- 以上两个属性如果没定位的父级，则相对于根元素html的距离
- offsetWidth
	- 当前元素的宽度（border + padding + content）
- offsetHeight
	 - 当前元素的高度（border + padding + content）

## 元素方法(适用所有的属性)  ##
- ele.getAttribute(attr)
	- 获取元素的属性值（自定义属性获取）获取HTML属性
- ele.setAttribute(attr,val)
	- 设置元素的属性
- ele.removeAttribute(attr)
	- 删除属性attr
- ele.hasAttribute(attr)
	- 判断是否存在属性attr
## 获取css样式（非内联样式） ##
- 得到当前元素计算后的所有样式
	- getComputedStyle(ele,pseudo) （标准）
	- ele:要获取样式的元素
	- pseudo:伪元素样式字符(可选)，可获取伪元素样式（eg:after）
	- ele.currentStyle （IE8-）

