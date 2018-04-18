# String #
- 创建字符串
	- 字面量(推荐)
		- var str = '我是一个字符串';
	- 构造函数
		- 用new关键字产生的变量都是引用数据数据类型，也叫变量
		- var str = new String('我是一个字符串');
-  length
	- 字符串的属性
		- 表示字符串的长度，只读（不可以修改）
	- 字符的获取
		- str[idx]
			- 兼容到ES5
## 字符串的获取方法 ##
- chartAt()
	- 根据下标获取对应的字符串
		- str:Hello
		- 下标:01234
		- str.charAt(3);//l
			- 获取到下标为3的字符
## 字符串的查找方法 ##
- indexOf/lastIndexOf(keyword *[,startIndex]*)

	- 从开头/尾部向后查找字符串keyword第一次出现的位置,如果没找到返回-1
- match(str|regExp) 
	- 匹配字符串，返回一个数组
	- index:匹配字符所在的索引
	- input:表示整个字符串的引用
- replace(str|regExp,'替换成这个') 替换字符串
	- 替换只能执行一次，不能够进行全局匹配，如果需要全局匹配，则应使用正则表达式
## 字符串截取方法 ##
- substring(start[,end])
	- 不包括end所在字符，end省略表示截取到最后
- substr(start[,len])
	- 支持负数，len为截取的数量
	- 负数表示从后边往前截取。例如，-1表示最后一个，以此类推
- slice(start[,end]) 
	- 截取start到end(不包括end)的字符串，支持负数
	- 负数表示从后边往前截取。例如，-1表示最后一个
## 字符串的分割 ##
- split(分割符)
	- 根据分割字符，把字符串拆分成数组
## 字符串大小写转换 ##
- toLowerCase()
	- 转换成小写
- toUpperCase()
	- 转换成大写

- ASCII码和字符集
	- charCodeAt(3) //获取下标为3的字符的ASCII(American Standard Code for * Information Interchange) == > unicode编码
	- String.fromCharCode(94) //编码转换成字符

## ECMAscript5新增 ##
- str[3]
	- 通过下标获取
- trim()
	- 删除前后所有空格，返回新的字符串 