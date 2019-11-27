# `html5`开始
##### `html5`新增语义化标签布局
```html
	<!-- 头部 -->
    <header></header>
    <!-- 中间内容区域 -->
    <main>
        <!-- 左边侧边栏 -->
        <aside></aside>
        <!-- 右边侧边栏  section 区块 区域 article-->
        <section></section>
    </main>
    <!-- 尾部 -->
    <footer>
    </footer>
```
##### `html5`新增表单类型
- `email` 	输入email格式
- `tel` 		手机号码(在移动端，定位焦点，会弹出数字键盘)
- `url` 		只能输入url格式
- `number` 	只能输入数字 (在移动端，定位焦点，会弹出数字键盘)
- `search` 	搜索框 (在移动端 enter/开始键里面的文字会变成搜索)
- `range` 	范围
- `color` 	拾色器
- `time`		时间
- `date` 		日期不是绝对的（会出现日期选择器）
- `datetime-local`时间日期
- `month` 	月份
- `week` 		星期

##### 新增表单属性
- `placeholder` 	占位符
- `autofocus`	 	获取焦点
- `required` 		验证条件，必填项
- `Pattern`: 		正则验证pattern="\d{1,5}“

##### 新增多媒体标签
* 音频:
```html
	<audio src=""></audio>
	<!-- autoplay 自动播放
	controls 是否显不默认播放控件
	loop 循环播放
	source 音视频源 -->
```
* 视频
```html
	<video src="" controls=""></video>
	<!-- autoplay 自动播放
	controls 是否显示默认播放控件
	loop 循环播放
	width 设置播放窗口宽度
	height 设置播放窗口的高度 -->
```


##### 新增自定义属性 `data`
```html
	<div id="box" data-abc="zzz" data-user-name="赵四" data-age="24">这是盒子</div>
```
```js
	//  h5 提供给我们一种新的操作属性的方法  定义的时候 通过data-*  获取 dataset去获取
	    var oBox = document.getElementById('box');
	    console.log(oBox.dataset); //它是一个对象  domStringMap 
	    // 里面能够存下来一些自定义属性
	    console.log(oBox.dataset.userName);
	    console.log(oBox.dataset['userName']);
	    oBox.dataset["aaBb"] = '哈哈啊哈哈';
```

##### `HTML5` 新增`dom` 操作`API`
1. `document.querySelector('selector')` 通过CSS选择器获取元素，符合匹配条件的第1个元素。
2. `document.querySelectorAll('selector')` 通过CSS选择器获取元素，以类数组形式存在。

##### 新增类名操作
1. `Node.classList.add('class')` 添加class
2. `Node.classList.remove('class')` 移除class
3. `Node.classList.toggle('class')` 切换class，有则移除，无则添加
4. `Node.classList.contains('class')` 检测是否存在class

```html
	<style>
        .active {
            width: 100px;
            height: 100px;
            background-color: red;
        }
    </style>
	<input type="button" value="单击切换类">
	<div id="box">盒子</div>
```
```js
		var oBox = document.querySelector('#box');
		oBox.classList.add("active");
		document.querySelector('input').addEventListener('click', function() {
	        // 来回切换类
	        oBox.classList.toggle('active');
	    });
```

##### 新增本地存储`SessionStorage`与`localStorage`
- `sessionStorage` 会话存储(窗口关闭,会话结束)
- `localStorage` 本地存储(永久存储) 除非手动删除
* 存储方法
- `setItem(key, value)` 设置存储内容
- `getItem(key)` 读取存储内容
- `removeItem(key)` 删除键值为key的存储内容
- `clear()` 清空所有存储内容

##### 定位