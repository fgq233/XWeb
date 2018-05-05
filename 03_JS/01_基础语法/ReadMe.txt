一、JavaScript 是属于网络的脚本语言！
	分为3部分：
	1、ECMAScript标准：是一种语言标准，JavaScript是对ECMAScript标准的一种实现
	2、BOM：主要是5个对象---Window对象、History对象、Location对象、Navigator对象、Screen对象
	3、DOM：所有载入浏览器的html文档都会成为Document对象
			所有标签都是Element元素、所有标签的属性都是Attribute、Document、Element、Attribute都属于Node节点

注意：JavaScript严格区分大小写、同时JavaScript是单线程的

二、基础语法
	1、变量的命名规范：所有语言的命名规范基本一致
	2、关键字
	3、变量的定义：JavaScript中所有变量都是用var来定义,没有声明的变量会被视为全局变量
	4、变量的赋值：=、 +=、 -=、 *=、 /=、 %=
	5、变量的数据类型(typeof 变量：检测变量的类型)
		1)、数值类型Number：JavaScript不区分整数和浮点数，统一用Number表示，以下都是合法的Number类型
		2)、字符串String
		3)、布尔类型Boolean
		4)、null
		5)、undefined
		6)、数组类型：JavaScript的数组可以包括任意数据类型	var arr = [1, 2, 3.14, 'Hello', null, true];
		7)、对象类型：JavaScript的对象是一组由键-值组成的无序集合
			var person = {
    			name: 'Bob',
    			age: 20,
    			tags: ['java', 'android', 'js'],
    			hasGirlFriend: true,
    			zipcode: null
			};
	6、运算符
		1)基本运算符：+、  -、  *、  /、  %
		2)自增、自减：++、 --
		3)关系运算符：>、 <、 >=、 <=、 !=
					==	会自动转换数据类型再比较，很多时候，会得到非常诡异的结果
					=== 不会自动转换数据类型
		4)逻辑运算符：&&、  ||、  !
		5)三元运算符：和java一模一样
	7、条件判断
		if () { ... } else { ... }
		if () { ... } else if { ... } else { ... }	
		switch语句 ：和java一模一样
	8、循环
		1)、普通for		for (var i=0; i<100; i++) {	}
		2)、增强for		for (var key in o) { }
		3)、while		while(boolean值){ }		
		4)、do while		do{ }while(boolean值)
	9、函数：函数不调用的话，自己不会执行
		function method(){
		}

		function method(a,b){		JavaScript的形参不用声明类型	
		}
		
		function method(){			JavaScript的返回值类型不用声明
			return 8888;
		}
	10、方法：绑定到对象上的函数称为方法
		var xxoo = {
    		name: 'fgq',
    		birth: 1993,
    		age: function () {
        		var year = new Date().getFullYear();
        		return year - this.birth;
    		}
		};

三、JavaScript中的内置对象
Arguments	函数参数的集合
Array		数组
Boolean		布尔对象
Date		日期对象
Error		异常对象
Function	函数构造器
Math		数学对象
Number		数值对象
Object		基础对象
RegExp		正则表达式对象
String		字符串对象
