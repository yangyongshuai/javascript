# `DOM`部分开始
* `DOM (document object model)`文档对象模型

### 获取标签方法
* `document.getElementById()`  获取`id` 
* `document.getElementsByClassName()`  获取`class`类名,返回伪数组`HTMLCollection`
* `document.getElementsByName()`  获取`name`属性  返回伪数组`NodeList`集合
* `document.getElementsByTagName()` 获取标签元素  返回伪数组`HTMLCollection`  

#### `H5`新增
* `document.querySelector()`   获取选择器元素
* `document.querySelectorAll()`  获取选择器所有节点列表  返回数组

### 节点属性
* `nodeType`  返回节点类型
	- 元素节点 返回1
	- 属性节点 返回2
	- 文本节点 返回3
	- 注释节点 返回8
* `nodeName`  依据节点类型返回名称  

### 获取节点
#### 会获取到空白节点 (IE5/6/7/8 不会获取空白节点)
* `Element.childNodes` 获取当前节点的所有子节点
* `Element.firstChild` 获取当前节点的第一个子节点
* `Element.lastChild` 获取当前节点的最后一个子节点
* `Element.nextSibling` 获取当前节点的下一个兄弟节点
* `Element.previousSibling` 获取当前节点的上一个兄弟节点

#### 不会获取到空白节点 (不支持IE5/6/7/8)
* `Element.children` 获取当前节点的所有子节点
* `Element.firstElementChild` 获取当前节点的第一个子节点
* `Element.lastElementChild` 获取当前节点的最后一个子节点
* `Element.nextElementSibling` 获取当前节点的下一个兄弟节点
* `Element.previousElementSibling` 获取当前节点的上一个兄弟节点

#### 获取子节点和兄弟节点兼容性写法
```js
	function firstNode(obj) {return obj.firstElementChild || obj.firstChild;}
	function lastNode(obj) {return obj.lastElementChild || obj.lastChild;}
	function nextNode(obj) {return obj.nextElementSibling || obj.nextSibling;}
	function prevNode(obj) {return obj.previousElementSibling || obj.previousSibling;}
```

### 元素操作
#### 设置元素属性方法:
* `element.getAttribute()`  获取元素节点指定属性值 主要是标签对象的属性
* `element.setAttribute()`  设置元素节点指定属性值
* `element.removeAttribute()`  删除元素节点指定属性值
* `Attributes` 获取当前一个DOM对象里的所有属性,并且每个属性在`attributes`里是一个属性节点对象的方式存在的,想要从`attributes`里获得某个属性节点对象时,直接`attributes.属性名`获取当前属性节点的值
* `hasAttribute`方法可以判断`DOM`对象里是否有某个属性,有返回true,没有false,此方法接受一个参数,就是属性名即可
* `hasAttributes`方法判断当前`DOM`对象是否有属性,有返回true,没有false.

#### 设置样式
* `element.style`  设置或者返回元素的行间样式
* `element.className` 设置或者返回元素的`class`属性

#### 设置元素内容 (重点)
* `element.innerHTML`  设置或返回元素内容    会解析标签元素
* `element.innerText`	设置或返回元素内容    不会解析标签元素

#### 创建节点
* `document.createAttribute()`	创建属性节点
* `document.createElement()`  	创建元素节点
* `document.createTextNode()`  	创建文本节点
* `document.createComment()`  	创建注释节点

#### 克隆节点
* `cloneNode` 此方法表示复制一个`DOM`,默认值克隆当前`DOM`对象,如果传参为`true`可以克隆`DOM`对象里的所有子节点都会被克隆进去

#### 元素操作
* `element.appendChild()` 	为子元素之后添加一个新的子元素
* `element.insertBefore()` 	现有的子元素之前插入一个新的子元素
* `element.removeChild()` 	删除一个子元素
* `element.replacechild()`	替换一个子元素

#### 获取父节点和祖父节点 (重点)
* `Element.parentNode`  	获取当前节点的父节点
* `Element.offsetParent` 	获取当前节点的祖父节点 (父级无定位,是body, 有定位,是离他最近的定位节点)

#### 元素距离 (重点`offset`常用)
* `Element.offsetLeft` 	计算元素到左侧距离  (会受到定位影响)
* `Element.offsetTop` 	计算当前元素到顶部距离
* `Element.offsetWidth` 	获取当前DOM对象包括边框，并且包括padding的盒子宽
* `Element.offsetHeight`	获取当前DOM对象包括边框，并且包括padding的盒子高
* `Element.getBoundingClientRect()` 返回元素的大小及相对于视口的位置
* `clienLift` 	获取当前DOM的左边边框的宽
* `clienTop` 	获取当前DOM的左边边框的高
* `clienWidth`	获取当前DOM对象不包括边框，但包括padding的盒子宽
* `clienheight`	获取当前DOM对象不包括边框，但包括padding的盒子高

#### 元素滚动距离
* `Window.pageYOffset`  获取或者设置窗口的垂直滚动距离(IE5/6/7/8不支持)
* `Window.pageXOffset`	获取或者设置窗口的水平滚动距离(IE5/6/7/8不支持)
* `document.documentElement.scrollTop` 	获取窗口垂直滚动距离
* `document.documentElement.scrollLeft` 获取窗口水平滚动距离
* `document.body.scrollLeft`	设置或获取窗口的水平滚动距离
* `document.body.scrollTop`		设置或获取窗口的垂直滚动距离
* `scrollHeight`	盒子的原始高加上滚动条可以滚动的距离的高
* `scrollWidth`		盒子的原始宽加上滚动条可以滚动的距离的宽

### 事件
#### `onload`
* `onload`事件的本质执行行为都是通过函数代码来描述的,等标签渲染完成后,才执行`liad`事件代码

#### 面试题:为什么把`script`标签写到`body`的下边:
* 放到下边,不影响标签内容的渲染,提高渲染速度
* 在`js`中获取标签时,不需要再加`onload`事件了,可以直接获取
* 渲染速度快的原因,跟浏览器的底层渲染机制有关!
* `script`标签如果写到开头或`body`的标签代码中间,会导致底层渲染机制的`Layout`和`Painting`

#### 鼠标事件
* `onclck` 		单击
* `ondblclick` 	双击
* `onmousedown` 鼠标按下
* `onmousemove`	鼠标移动
* `onmouseout` 	鼠标从某元素离开
* `onmouseover` 鼠标移到某元素上
* `onmouseup` 	鼠标松开

#### 键盘事件
* `onkeydown` 	键盘按下
* `onkeyup`		键盘离开
* `onkeypress`	键盘按下并离开

#### 表单事件
* `onchange` 	表单改变离开时触发
* `oninput`  	表单输入时触发

#### 事件对象(`event`)
* 兼容性写法   `ev = event || window.event`

##### 键盘
* `event.keyCode` 返回键盘的数字编码	

##### 鼠标
* `event.clientX`	鼠标所在可视窗口X轴位置
* `event.clientY`	鼠标所在可视窗口Y轴位置
* `event.pageX`   	鼠标所在整个页面X轴距离  (IE5/6/7/8不支持)
* `event.pageY`   	鼠标所在整个页面Y轴距离	(IE5/6/7/8不支持)

##### 事件源
* `event.target` 事件源  (IE5/6/7/8不支持)
* `event.srcElement`  (IE5/6/7/8支持)

##### 阻止默认事件
* `event.preventDefault` 阻止默认事件
* `return false`  也可以做到

# `DOM`部分结束