# jQuery #
<div style="color:red ;font-size:30px"></div>
## 核心理念 ##
- write less,do more

## 使用jQuery ##
- DOM节点操作
	- 选择元素
	- 操作元素
- 选择器
	- css选择器

## 选择器 ##
## 筛选 ##
- filter
	- $('a').filter('.link');
- not
	- $('a').not('link');

## 节点关系 ##
- find();
	- 获取到所有后代元素
- children()
	- 获取到所有子元素


## 转换 ##
- jq-->原生
	- [node].get(idx)
	- [node][idx]
	- get()
		- 获取所有dom节点
- 原生-->jq
