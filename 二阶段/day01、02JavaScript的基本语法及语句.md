- ECMAScript(专利)，标准化
- W3C
- ES

- js = ECMAScript(核心) + BOM（浏览器对象） + DOM（文档对象模型）

## js语法 ##
- 变量
	- 存储数据的容器
- 变量声明
	- var
- 函数声明
	- function

- 用来判断是否是非数字
	- isNaN();
- 取整
	- parseInt();
- 生成一个随机数（0-1）
	- Math.random();

- 判断数据类型
	- typeof

- 隐式转换
	- 若果内部不能进行运算，会进行隐式转换
		- 逻辑运算、关系运算、算术运算都会进行隐式转换

- 进制转换
	- 十进制转其他
		- num.toString(16);    转16进制
	- 16进制 	前面加0x
	- 8进制    	前面加0o
	- 2进制    	前面加0b

	- 其他转十进制
		- parseInt('a',16);//10   16进制转十进制
- if条件判断语句
	- 单分支
	- 双分支
	- 多分支
	


- 三元运算符
	- 格式
		- 条件？条件成立执行：条件不成立时执行
- switch语句
	- switch(val)
		- case:value
			- value的值恒等于val,代码从这里开始执行
		- default 相当于if语句中的else
	- 不加break,叫switch语句穿透
- for循环
	- for(变量初始化;条件判断;变量跟新){循环体}
	- 执行顺序
		-  先执行，后更新

## 循环标识 ##
- label
	- 给循环添加标识（起个名字）
		- wai:for(){}
		- break wai;
	- 在内循环中也可以跳出外层循环	


