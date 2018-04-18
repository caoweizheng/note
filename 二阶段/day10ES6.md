# ES6 #
## 变量与声明 ##
- let
	- 不允许相同作用域多次声明相同的变量
	- 变量不会声明提前
	- 块级作用域-->标识‘{}’
- const
	- 声明常量
	- 声明的值不允许修改
	- 变量不会声明提前
	- 块级作用域
## 解构 ##
- let obj = {name:'laoxie',age:18,grnder:'男'}
- ![](https://i.imgur.com/oiSRX0Q.png)
- ![](https://i.imgur.com/YXNuIGm.png)
- ![](https://i.imgur.com/Kai7t2U.png)

- 变量名需要与属性名一致，否则解构失败，值为undefined
- 不一致的写法
	- gender:sex;
		- 用gender的值赋给sex
	- hobby='唱歌'
		- 设置参数默认值
- 用途
	- 可以用来交换变量
		- var [x,y] = [y,x];
	-  形参，不用再考虑参数的顺序，直接用对象.key来调用
	-  直接传入对象，再解构
	-  ![](https://i.imgur.com/cTXN1ld.png)

## 字符串扩展 ##
- 判断字符串是否包含某个值
	- 'google'.includes('o');
	- 返回布尔值
- 是否以某一字符开头/结尾
	- str.startsWith()/str.endsWith()
- 将字符串重复
	- str.repeat(n)

- 字符串模板
- ![](https://i.imgur.com/qDabf54.png)

## 对象扩展 ##
- Object.assign()
	- 合并/扩展对象
	- ![](https://i.imgur.com/5mTrdVf.png)
	- ![](https://i.imgur.com/a7zFarL.png)
	- 对象复制
	- Object.assign(newObj,oldObj)
	- 如果对象中有引用数据类型，则不能完全复制，称为浅复制
	- 深复制
		- newObj = JSON.parse(JSON.stringify(oldObj));
- 对象简写
	- ![](https://i.imgur.com/vTPkETQ.png)
	- ![](https://i.imgur.com/NPuEYdl.png)

## 箭头函数 ##
- 格式
	- 标识符=>表达式
	- 省略function,return,关键字，圆括号，花括号
	- 多行代码时不可省略{}、retutn
	- 一个或者没有参数
		- ![](https://i.imgur.com/eXE2PTG.png)
	- 多个参数
		-  ![](https://i.imgur.com/gJwNdfq.png)
	

- 返回一个对象
	- 紧随箭头的{被解析为块的开始，而不是对象的开始}
	- ![](https://i.imgur.com/1f2gQD0.png)

## 箭头函数中的this ##
- 箭头函数没有它的this值，箭头函数内的this值继承自外围作用域
	- ![](https://i.imgur.com/C3kjmUD.png)
## 剩余参数Rest ##
- ![](https://i.imgur.com/iRF03fY.png)

## symbol ##
- ![](https://i.imgur.com/5GlbYHG.png)
- ![](https://i.imgur.com/o1Hkfmp.png)

## set集合 ##
- ![](https://i.imgur.com/6HHPFLk.png)
- ![](https://i.imgur.com/xzDVCio.png)
- set集合，相当于数组，但是成员的值都是唯一的，可自动去重
	- 去重的前提是两个值恒等
- 数组去重
- ![](https://i.imgur.com/UsV2JIR.png)
- 把set类型转成数组
	- Array.from()
## Map映射 ##
- 类似于对象
- 由于创建对象时，对象的属性名只能是string
	- 增强对象Object
	- 键可以是任意数据类型
- ![](https://i.imgur.com/jGLKvt8.png)
- ![](https://i.imgur.com/uGrmrIv.png)
- let[key,value] = item;//解构，将键值分别赋值

## 生成器函数Generators ##
- ![](https://i.imgur.com/LwcvNXd.png)
- ![](https://i.imgur.com/JHs71hE.png)
- 继续执行需要用返回的对象继续调用next()
- 用done的值来判断函数执行完毕





