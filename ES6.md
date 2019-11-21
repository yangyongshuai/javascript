# `ES6`开始
* `ES6`也可以叫`ES2015`

### 变量
1. `let`声明变量
2. `const`声明常量

### 模板字符串
* `(``)`反引号 
	- 可换行
	- 可以引用变量

### 变量结构
```js
	let [a,b,c] = [1,2,3]
	console.log(a)  //1
	console.log(b)	//2
	console.log(c)	//3
	let {foo,bar} = {foo:'aaa',bar:'bbb'}
	console.log(foo)  	//aaa
	console.log(bar)	//bbb
```

### `rest`可变参(展开运算符)
```js
	 myFun(1,2,2,5,6)
	function myFun(num, ...args){
		console.log(num)
		console.log(args)
	}
	//用展开运算符可以做到合并数组的操作
	let arr = [12,2,5,6,8]
	let arr2 = [12,2,5,6,8]
	console.log(...arr)
	let arr1  = [...arr,...arr2]
	console.log(arr1)
```

### 普通函数
* 可以给形参设置指定默认值
```js
	myFun(1,7)
	function myFun(num=1, num1=19) {
		console.log(num + num1)
	}
	console.log(myFun.name)
```

### 箭头函数
* 注意:
	- 箭头函数不能使用`arguments`对象  可以用`rest`代替
	- 如果只有一个参数，形参列表的圆括号可以省略
	- 如果只有一条返回语句，那么花括号和return都可以省略
```js
	let myFun = (num1,num2) =>{}
```

### 合并对象 
* Object.assign() 这个方法是对对象做深拷贝操作的,第一个参数是被合并操作的对象，第二个参数是要把哪个对象合并到第一个参数对象里
```js
  var apple = {
	price: 15,
	color: 'red',
	};
	var dog = {
		name: '伊咪',
	};
	var newObj = Object.assign(apple, dog);
		console.log(newObj);
```

#### 注意:
* 两个对象怎么合并?两个对象怎么深拷贝?两个对象如何做继承(浅拷贝)?

### `ES6`数组`API`
* 下面参数都是一个`callback`回调函数
* `find()`：返回数组中第一个满足条件的结果  在回调函数内，通过return 来判断要查找的结果
```js
	var arr1 = [1, 2, 3, 4, 5, 6];
	var result1 = arr1.find(function (item) {
		console.log(item);
		return item === 3;
	});
	console.log(result1);
	//原生封装
	 Array.prototype.find=function(callback){
		var resultNum;
		for(var i =0;i<this.length;i++){
			var boolResult = callback(this[i]);
			if(boolResult){
				resultNum=this[i];
				break;
			}
		}
		return resultNum;
	} 
```

* `findIndex()`：返回数组中第一个满足条件的元素的索引
```js
		var arr1 = [1, 2, 3, 4, 5, 6];
	  var currentIndex = arr1.findIndex(function (item) {
			return item.id === 4;
		});
		console.log(currentIndex);
```

* `filter()`：返回符合条件的新数组
```js
	var newData = data.filter(function (item) {
		return item.age <= 25;
	});
	console.log(newData);
```

* `map()`：对原数组中每个项可以做些操作后，返回新的数组
```js
	 var newArr1 = arr1.map(function (item, index) {
		return item * 2;
	});
	console.log(newArr1)
```

* `includes()`：判断数组中是否包含某个值
```js
	var arr1 = [1, 2, 3, 4, 5, 6];
	 if (arr1.includes(20)) {
			console.log('有了，坡肥特！');
		} else {
			console.log('哦呵，完蛋,没有');
		}
```

* `some()`：根据条件判断数组中是否有满足条件的值，有了就返回`true`，否则返回`false`
```js
	 var result1 = data.some(function (item) {
		return item.id === 3;
	});
	console.log(result1);
```

* `every()`：和`some()`很像，但唯一区别就是，`some()`是有任意一项符合就是`true`，而`every()`则是每一项都要一样才会返回`true`
```js
	 var result2 = data.every(function (item) {
		return item.age > 19;
	});
	console.log(result2);
```

* `reduce()`：数组的新迭代方法的操作，回调函数中的第一个参数是上一个值，第二个参数是下一个值
```js
	  var result3 = arr1.reduce(function (prev, next) {
		console.log(prev, next);
		return prev + next;
	});
	console.log(result3);
```

### `forEach`循环
* `forEach` (只能循环数组)
```js
	 var data = [
	            {
	                id: 1,
	                name: '李白',
	                age: 18,
	            },
	            {
	                id: 2,
	                name: '娜可露露',
	                age: 22,
	            },
	            {
	                id: 3,
	                name: '不知火舞',
	                age: 30,
	            },
	            {
	                id: 4,
	                name: '宫本武藏',
	                age: 40,
	            },
	            {
	                id: 5,
	                name: '橘右京',
	                age: 25,
	            },
	        ];
			data.forEach(function (item, index) {
			console.log(item, index);  //第一个是循环的每一项，第二个是循环的索引
	});
```

* `for-of`循环
	- `for-of`和`for-in`的区别:
		- `for-in`循环获取到的是每一个`key`，
		- `for-of`获取到的是每一个`value`
```js
	for (var item of arr1) {
		console.log(item);
	}
	for (var item of data) {
		console.log(item);
	}
```

### 对象强化字面量写法
* 键值一样可以只写一个

### `Class`类
```js
	class Animal {
		// 第一步，要先声明出来对象的构造函数(构造器)constructor
		constructor(name, age) {
			// 属性在构造函数里定义
			this.name = name;
			this.age = age;
		}

		// 方法行为在class里直接定义即可
		show() {
			console.log(this.name, this.age);
		}
	}
	var XueQiu = new Animal();
	XueQiu.show()
	//继承
	class BiXiong extends Animal {
	            // 在使用extends做继承后，子对象里必须要在constructor构造器中使用super关键词来体现继承
	            constructor(name, age, color) {
	                // super其实指的就是父类，那么直接super()，表示调用了父类的构造函数
	                // 调用父类的构造方法后，将子类实例化时获取到的实参的值传递给了父类
	                super(name, age);
	                this.name = name;
	                this.age = age;
	                this.color = color;
	            }
	            eat() {
	                console.log(this.name + '开心的吃着狗粮');
	            }
	
	            // 在class类里定义一个静态方法
	            // 和function函数对象一样，静态方法里this指向window，静态是通过类名直接调用的
	            static run() {
	                console.log(this.age + '呵呵的跑着');
	            }
	        }
			var yiMi = new BiXiong('伊咪', 5, '白色');
	        yiMi.eat();
	        yiMi.show();
	        BiXiong.run();
```

* ES6的类class对象使用总结：
	- 通过class{}来定义对象的模板
	- 需要手工来编写constructor构造函数
	- 通过extends来做父类和子类之间的继承关系
	- 当有extends继承时，子类的构造函数constructor里必须要有super()关键词调用，在继承后，子类必须调用父类的构造函数
	
### `Promise` 异步编程
* Promise是一个对象，在实例化是传递一个回调函数的实参，在这个回调函数里又有两个参数，分别是resolve和reject，那么通过实例化后的Promise对象的then()方法来调用触发resolve模块，catch()方法触发调用reject模块
* promise三种状态:
	- pending（进行中）
	- fulfilled（已成功）
	- rejected（已失败）
	
```js
	function cheng(num1, num2) {
		var promise = new Promise((resolve, reject) => {
			// 当前cheng这个函数的实际业务模块代码全部写在Promise对象里
			var result = num1 * num2;
			console.log(result);
			if (result < 80) {
				// 根据条件判断，要想进一步触发回调，则执行resolve模块就ok了
				resolve('呵呵');
			} else {
				// 如果不想再继续回调了，则根据条件判断触发执行reject模块即可
				reject();
			}
		});
		return promise;
	}
	 // then执行触发的就是resolve模块，then()方法里的参数其实就是resolve方法
	cheng(1, 2)
		.then((str) => {
			console.log('第一次回调执行' + str);
			// 在第一次函数执行完后，如果还需要再次回调调用时，则可以通过return将需要回调的函数再次执行即可
			return cheng(3, 4);
		})
		.then(() => {
			console.log('第二次回调执行');
			return cheng(5, 6);
		})
		.then(() => {
			console.log('第三次回调执行');
			return cheng(7, 8);
		})
		.then(() => {
			console.log('第四次回调执行');
			return cheng(9, 10);
		})
		.then(() => {
			console.log('第五次回调执行');
			return cheng(11, 12);
		})
		.then(() => {
			console.log('第六次回调执行');
			return cheng(13, 14);
		})
		.catch(() => {
			console.log('够了！');
		});
	  // 基于上边的回调地狱场景，实际开发时，在使用ajax访问接口时也可能会出现类似情况
			// function ajax(obj, callback) {
			//     var result;
			//     var xhr = new XMLHttpRequest();
			//     xhr.open(obj.method, obj.url);
			//     xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
			//     xhr.send();
			//     xhr.onreadystatechange = function () {
			//         if (xhr.readyState === 4 && xhr.status === 200) {
			//             result = xhr.responseText;
			//         }
			//     }
			//     /* 
			//         json格式的字符串转json对象：JSON.parse();
			//         json对象转json格式的字符串：JSON.stringify();
			//      */
			//     return result;
			// }
			// var result = ajax({ method: 'get', url: 'localhost:8888/getName' }, function () { 
			//     // 一次请求完成之后，可能还需要拿刚请求完的结果做一些业务逻辑判断处理，紧跟着再发送一次新的请求
			//     result = result && result;
			//    if(!result){reject()}
			//     var result1=ajax();
			// });
			function ajaxPromise() {
				/* 
					实际开发时，可能会从一个接口API拿到响应结果后，处理完结果，再拿这个结果去请求另外一个接口
				 */
				return new Promise((resolve, reject) => {
					var xhr = new XMLHttpRequest();
					xhr.open('get', 'http://localhost:8888/data');
					xhr.setRequestHeader('Content-Type', 'application/json');
					xhr.send();
					xhr.onreadystatechange = function () {
						if (xhr.readyState === 4 && xhr.status === 200) {
							console.log(xhr.responseText);
							resolve(xhr.responseText);
						} else {
							reject();
						}
					};
				});
			}
			ajaxPromise()
				.then(response => {
					console.log('第一次回调：' + response);
					return ajaxPromise();
				})
				.then(response => {
					console.log('第二次回调' + response);
					return ajaxPromise();
				})
				.catch(() => {
					console.log('服务器挂了，打死后端！');
				});
```

* `Generator`函数的使用，解决异步同步化问题
* `async/await`函数的使用，解决异步同步化问题

# `ES6`结束