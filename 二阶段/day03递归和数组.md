- 回调函数
	- 把函数作为参数传递
	
			// 月份：1  2  3   4   5   6   7   8   9   10   11   12
	        // 数量：1  1  2   3   5   8   13  21 34   55   89   144
	        function fib(num){
	            if(num<3){
	                return 1;
	            }
	            return fib(num -1) + fib(num - 2);
	        }
	        console.log(fib(10));//55
			
- 函数递归
	- 自己调用自己

- 数组的方法
	- push()
		- 在数组末尾追加一个或多个元素
		- 返回添加后的数组长度
	- pop()
		- 删除最后一个数组元素
		- 返回删除的元素
	- unshift()
		- 在数组开头添加一个或多个元素
		- 返回添加后的数组长度
	- shift()
		- 删除第一个数组元素
		- 返回删除的元素
	- splice(start,deleteNum,items...);
		- 数组中插入、删除、修改的通用方法
		- start
			- 起始索引位置
		- deleteNum
			- 要删除的数量
		- items
			- 插入的元素（可以是多个）
	- sort()
		- 将数组中的元素排序，并返回排序后的数组
		- 默认以字符串的排列方式（转换成ASCII码进行对比）		
	- reverse()
		- 将数组中的元素颠倒顺序，返回逆序后的数组
	- join(separator) 
		- 返回字符串值，其中包含了连接到一起的数组的所有元素
		- separator为分隔符，默认为逗号
	- slice()
		- 格式
			- 数组.slice(start,end);
		- 功能
			- 基于当前数据获取指定区域(包含头，不包含尾)的元素并创建一个新数组。原数组不改变
		- 参数
			- start开始获取区域的下标，end结束获取区域的下标
		- 返回值
			- 指定区域元素生成的新数组
		- 可以取负数
			- -1相当于最后一个元素，以此类推
		- 可用于数组复制
			- 赋值数组的方法
				- 1.遍历将数组的元素添加到新数组中
				- 2.调用slice(0)返回新数组
				- 3.调用map(fn(item){return item})返回新数组
				- 4.调用filter(fn(item){return true})返回新数组
				
	- arr1.concat(arr2)
		- 数组拼接
- arguments
	- 函数内部隐藏的对象（是一个类数组），保存着实参的信息
		- 数组
		- 索引
			- 从0开始到length-1
			- 一系列数据的集合
	- length
		- 实参的数量
- ES5数组的遍历方法

		不返回值
		 arr.forEach(function(item,index,arr){
			item:数组元素
			index:元素索引
			arr:数组本身
		});
		返回一个与元数组长度相同的数组，内容取决于函数的内容
 		arr.map(function(item){
			item:数组元素
		});
		返回过滤后的数组，函数返回true则保留，false则过滤
		arr.filter(function(item){
			return item>10;
		});
		返回Boolean值，函数的值包含true，则整个结果为true，全部false才为false
		arr.some(function(item){
			return item===10;
		});
		返回Boolean值，函数中所有项返回true，结果才为true
		arr.every(fn)
	- 判断是否为数组
		- Arry.isArry([10,2]);
	- 判断数组中是否存在值,有则返回存在值所在的索引位置，没有则返回-1
		- arr.indexOf('10'[,startIndex]);
		- 从后面往前找,索引位置还是从左往右数
			- lastIndexof('10',[,startIndex]);

	- 归并方法
		- 都会迭代数组中的所有项，然后生成一个最终返回值
		- reduce(fn[,initVal]);
		- reduceRight(fn[,initVal])
			- fn(prev,cur,index,arr)
				- 每一项调用的函数
				- prev
					- 前一次fn的返回值
				- cur
					- 当前值
				- index
					- 索引值
				- arr
					- 当前数组
			- 函数需要返回一个值时，这个值会在下一次迭代中作为prev的值
			- initVal
				- 迭代初始值(可选)，如果缺省，prev的值为数组的第一项
## 排序 ##
- 冒泡排序
	- 用当前数分别跟下一个元素对比（两两之间对比）
- 选择排序
	- 用当前数依次跟后面的元素对比

## 对象 ##
- var laowang = {name:'laowang',sex:'male'};
- 增
	- laowang['age'] = 28;
- 删
	- delete laowang['age];
	- delete laowang.age;
- 查
	- laowang['age'];
		- 当属性为变量时，必须使用该方式
	- laowang.age;
- 改
	- laowang.age = 22;
	- laowang['age'] = 22;


- 对象遍历


-  
	 for(var key in laowang){
		// 遍历所有的属性，分别把属性名赋值给key
		// 获取属性值
		var value = laowang[key];
	 }
- console.dir()


		