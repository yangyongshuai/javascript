# `day1`
#### `javascript` 

* `js`做为弱类型解释型脚本型语言，在运行每行代码时，浏览器里专门解析`js`的`v8`解析引擎就开始逐行对代码先进行预编译预解析，作用就是检查每行代码的语法是否使用正确，解析一些需要进驻内存的变量数据或对象数据。总结：基于上班说辞，其实就总结出来代码的一个执行顺序，从上往下，从左往右，当然如果遇到赋值运算符`=`时，则是先右再左
* 在1995年时，由[Netscape](https://baike.baidu.com/item/Netscape)(网景)公司的[Brendan Eich](https://baike.baidu.com/item/Brendan Eich)(布兰登·艾奇)，在[网景导航者](https://baike.baidu.com/item/网景导航者/10404300)浏览器上首次设计实现而成。因为[Netscape](https://baike.baidu.com/item/Netscape)与[Sun](https://baike.baidu.com/item/Sun/69463)(Java的创始者公司，创始人詹姆斯·高斯林)合作，[Netscape](https://baike.baidu.com/item/Netscape)管理层希望它外观看起来像[Java](https://baike.baidu.com/item/Java/85979)，因此取名为`JavaScript`。但实际上它的语法风格与[Self](https://baike.baidu.com/item/Self/4959923)及[Scheme](https://baike.baidu.com/item/Scheme)较为接近。`js`这个语言的前身名字叫`ECMAScript`。随着时代的进步的发展，好东西依然是不变的，`Netscape`进行了重组，目前就是`Mozilla`公司，没错，火狐`Fire Fox`浏览器就是`Mozilla`公司的杰作！
* 每一行代码完了后，结尾不要忘记加一个英文输入法的分号`;`，就好像是我们中文一句话说完了要加句号
  
#### 变量 `var`(`variable`) 的简写
* 变量: 内存的基本组成单元
  - 变量定义的语法 `var` 变量名= 变量值 
  - 变量名是自己起名字的
  - 变量名字的基本规则:
    * 变量的命名要有一定的含义,用英文有语义化的名字命名变量
    * 变量名开头必须是英文,下划线和美元符号$开头
    * 起名字时多个英文字母命名时,则采用驼峰命名规则,第一个单词首字母小写,后面单词首字母大写
  
#### 数据类型
* `Number`    数字类型      包含了整数和小数,整数和负数.只要是数字就行,值不需要加引号
* `String`    字符串类型     一个字是一个单字符,那么一串字呢,就是字符串,字符串是用引号包裹起来的,建议用单引号
* `Boolean`   布尔类型,值是`true`和`false`,只有这两个值
* `Array`     数组类型,可以一下存多个数据的集合,相当于一个数组的集合
* `Function`  函数类型
* `Null`      空值类型,值就是`null`关键词
* `Undefined` 未定义类型,值就是`Undefined`关键词,可以不写;
* `Object`    对象类型

#### `Null`和`Undefined`的区别:
* `Null`会占用内存空间,相当于内存里为`null`开辟一个专门存它的空间
* `Undefined` 是未定义的,未定义的意思就是不存在,更别提内存空间了

#### `typeof`查看数据类型
```js
    var num = 5;
    var str = '5';
    var result = num + str;
    console.log(result, typeof result); 
```
#### 数据类型转换
* 隐式类型转换 又叫自动类型转换
  - 自动类型转换是在JS程序运行时,不同变量及运算符搭配使用时,JS程序对数据类型做隐式转换
* 强制类型转换 又叫显式类型转换
  - `Number`() 转数字
  - `parseInt`()
  - `parseFloat`()
  - `String`/ `toString`/ `''`() 转字符串

#### `prompt`弹出输入框
```js
    var num = prompt('请输入一个数字：');
    console.log(num, typeof num);
```
#### 保留小数的操作方式
* 数字类型的变量都有一个`toFixed`()方法,对浮点类型(小数)操作时,括号里传入一个数字,写几保留几位,这种方法会进行四舍五入
```javascript
    var xiaoShu =3.141592654;
    xiaoShu = xiaoshu.toFixed(2)
    // toFixed(2) 参数写几就保留几位小数
    console.log(xiaoShu)
```
#### 运算符
* 赋值运算符: `=` 
* 算数运算符: `+`,`-`,`*`,`/`,`%`(`+`遇见字符串会变成字符串拼接符)
* 关系运算符: `>`,`<`,`>=`,`<+`,`==`,`!=`,`!==`,`===`  
  - 关系运算符的表达式结果是一个`boolean`结果
  - 字符串在关系运算符里会首先转换成数字类型进行比较
  - 总结: 双等号判断是否相等时,仅仅判断值和变量是否相等,而不判断数据类型;三等号在判断是否相等时,是判断了变量的值和标量的数据类型都必须一样时,才是`true`,否则`false`
* 三元表达式:var 变量名 = 关系表达式?为`true`时的结果:为`false`时的结果
* 逻辑运算符:`&&`,`||`,`!`
  - 作用:两边链接两个关系运算符的表达式
  - `&&` 中文叫与,表示两边结果都是`true`时,最终结果才是`true`只有一个为`false`
  - `||` 中文叫或,表示两边的结果只有一个为`true`,那么最终结果就是`true`同时为`false`时,最终结果为`false`
  - `!` 中文叫非,表示当前结果为`true`时,则!能反转结果为`false` 
  - 非 > 与 > 或  优先级排序

#### `js`代码运算符的优先级
* 小括号 -> ++算数运算符 -> 逻辑运算符! -> 算术运算符 -> 关系运算符 -> 逻辑运算符`&&` -> 逻辑运算符 `||` -> 赋值运算符 -> 算数运算符++

#### `boolean`类型的数据隐式转换方式:
* `Nunber`:`0`就是`false`,非`0`的其他数字都是`ture`
* 空值字符串为`false`,所有非空的字符串为`true`
* `null`和`undefined`都是`false`

#### 短路语法也可以叫短路思想,
  - 就是利用逻辑运算在运行时对两边数据的隐式转换
  - `&&`:从左边开始判断,如果左边为真时,则将右边的值赋值给变量,如果左边为假,则将左边的值赋值给变量
        * 左为真,值为右,左为假,值为左
  - `||`:如果两边都为假时,返回右边变量值,如果两边都为真时,则返回左边的变量值,如果有一边为真时,则返回真的变量值
        * 左为假,值为右,左为真,值为左.

#### 语法糖: syntax sugar 是由一个英国佬创造的一种说法
* 目的: 解决实际编程时过于复杂的一些语法,将语法在底层就进行简化操作的封装,这样程序猿就不在需要用一些复杂的语法方式来进行编程,而是用相应的语法糖语法来编程
  - 叠加的计算方式:
```javascript
    var num =1;
    // num++ 其实就是num=num+1;的语法糖 ++表示每次只加1
    num ++ ;
    console.log(num)
```

#### 运算符优先级面试实例坑题:
```js
    var num = 1;
    /* 
        小括号提高了优先级，那么也就是说，在执行最终的加号运算符之前，会先将
        小括号里的每段结果得出来一个值之后，才会运行最终的加
    */
    //             1            3        4         4         5
    var result = (num++) + (++num) + (++num) + (num++) + (num++);
    console.log(result);
    /* 
        在表达式中，使用时，++在后，是先拿值，才++，在前则先++，再拿值
    */
```

# `day2`

#### 选择判断语法
* `if` 语法
  - `if`  
  - `else-if :`  可以有多个
  - `else :`  可以省略不写
```javascript
    // if  if后边条件可以不写,在不写的时候,只执行满足条件的后边一行代码    
    if(条件判断){
        console.log('如果上边boolean为true,则执行if大括号里的代码,如果false则不执行')
    }
    // if else
    if(条件判断){
        console.log('满足执行')
    }else{
        console.log('不满足执行')
    }
    // if和else只执行其中一个
```
* `switch - case`
  - `switch` 
  - `case`    可以有多个
  - `switch` 自己定一个`Number`或`String`
```js
    switch(自己定一个`Number`或`String`)
        case....:
        break;  //(终止switch运行)
        case....:
        break;
        default: //可以省略不写 
        break;
```   
#### `if` 和 `switch` 的区别
* `if-else` 可以判断区间范围的条件,所以区间范围的条件,建议首选if-else
* `switch` 单个值条件判断,建议seitch判断
  
#### 浏览器自带的断点调试
* 按步调试(F10)
* 按行调试(F11)

#### 循环语法
* 循环三要素:
  - 循环变量:定义循环次数开始时的初始值
  - 循环条件:约束循环的执行范围
  - 循环索引的更新:在执行循环体时,不断的修改循环索引,以满足对循环条件的判断需求
1. `while` 循环
```js
while(Boolean){
    //  当满足条件,循环,不满足, 终止
    // 一直满足,不断循环,死循环 
}
```
#### while循环处理的两种问题:
   1. 循环范围固定时 ,可以通过条件的范围和更新循环索引来达到执行一定次数的循环体
   2. 循环范围在不固定时,则需要通过用户输入来确定一下次循环是否执行,这种循环条件往往是等值判断条件
2. `do -while` 循环
```js
    do{
    // 先执行循环体内容 在判断
    }while(循环条件);
```
3. `for` 循环
```js
    for( 循环索引;循环条件 ;更新循环索引 ){
        // 循环体代码 
    }
```

#### break和continue
* `break`:只能在循环语法或switch选择判断中使用,终止循环或者switch语法
* `continue`: 单词是继续的意思;次关键词只能在循环语法中使用,作用是终止当前循环,继续下一次循环 

#### js学习过程中的三大难点
  - 循环语法
  - 函数
  - 对象


# `day3`
* 字符串变量.`length`可以获取当前字符串值得长度
#### 数组(array)   可以保存多个数据的变量
```js
    // 创建一个数组,
    var arr = new Array()
    var arr1 = []
```
#### 循环遍历数组
```js
    var arr1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12];
    // 正序输出
     for (var i = 0; i < arr1.length; i++) {
            console.log(arr1[i]);
    }
    // 倒序输出
    for (var i = arr1.length - 1; i >= 0; i--) {
        console.log(arr1[i]);
    }
```
* 数组的排序方法 `sort`()的使用
  - 使用数组调用`sort`方法 

* 数组的动态插入元素方法 `push`  在数组最后添加一个索引元素
  - 不用`push`可以用 `arr2[arr2.length]` 方法
```js
    var arr2 = [1, 2];
    arr2.push('你好，好困');
    console.log(arr2);
```
* 数组的`pop()`方法 删除数组最后一个索引元素
```js
    var arr3 = [1, 2, 3, 4, 5];
    var beiShanDeHuo = arr3.pop();
    console.log(arr3);
    console.log('被删除的家伙是：', beiShanDeHuo);
```

### 双重循环,循环嵌套
  * 外侧循环一次,内层循环一轮
  * 当循环嵌套执行时，程序在双重循环里的执行次数是成倍运行的，这种 运行对于程序性能是一种极其高的损耗浪费，因此一般在实际开发编程时，嵌套循环最多只能套一层，就是所谓的双重循环
```js
    var count = 0;
    for (var i = 0; i < 5; i++) {
        for (var j = 0; j < 7; j++) {
            // 不建议再嵌套循环，太浪费程序性能
            for (var z = 0; z < 3; z++) {
                count++;
            }
        }
    }
    console.log(count);
```
  
#### `document.write`()向网页里写入一些内容
```js
// 打印一个6行的直角三角形
   var row = 6;
    for (var i = 0; i < row; i++) {
        for (var j = 0; j <= i; j++) {
            document.write('*');
        }
        document.write('<br>');
    }
    document.write('<hr>');
// 九九乘法表
    for (var i = 1; i <= 9; i++) {
        for (var j = 1; j <= i; j++) {
            document.write(j + '×' + i + '=' + (i * j) + '&emsp;');
        }
        // document就是文档的意思，相当于利用它的write()方法往网页里写文档内容，就是html超文档内容
        document.write('<br>');
    }
    document.write('<hr>');
```

#### 冒泡排序
```js
    /*
        冒泡排序主要解决数组里各个值排序的问题
        第一种使用方式：拿数组里各个位置的值和其余的值比大小，
        以从最小值开始依次往后到最大值的操作方式来做
    */
    var count1 = 0;
    var arr1 = [5, 3, 4, 1, 2];
    console.log('排序前的数组是：' + arr1);
    for (var i = 0; i < arr1.length; i++) {
        for (var j = i + 1; j < arr1.length; j++) {
            if (arr1[i] > arr1[j]) {
                count1++;
                var temp = arr1[i];
                arr1[i] = arr1[j];
                arr1[j] = temp;
            }
        }
    }
    console.log('排序后的数组是：' + arr1);
    console.log('性能低的执行次数：', count1);
    console.log('****************************************************');
    /* 
        冒泡排序的第二种方式：这种方式是利用相邻两个数据进行比较，优先找最大值，这样从大到小以排序
    */
    var arr2 = [5, 3, 4, 1, 2];
    var count2 = 0;
    console.log('排序前的数组是：' + arr2);
    for (var i = 0; i < arr2.length; i++) {
        for (var j = 0; j < arr2.length - 1 - i; j++) {
            if (arr2[j] > arr2[j + 1]) {
                count2++;
                var temp = arr2[j];
                arr2[j] = arr2[j + 1];
                arr2[j + 1] = temp;
            }
        }
    }
    console.log('排序后的数组是：' + arr2);
    console.log('性能高的执行次数：', count2);
```
#### 打印一个三角形实例
```js
// 第一种
    for (var i = 0; i < 6; i++) {
        for (var j = i; j < 6; j++) {
            document.write('*');
        }
        document.write('<br>');
    }
    document.write('<hr>');
    // 第二种
    for (var i = 1; i <= 6; i++) {
        for (var j = 1; j <= 2 * i - 1; j++) {
            document.write('*');
        }
        document.write('<br>');
    }
    // 要把html里的body加上text-align:center; 不加是直角三角形
```
# `day4` 
* `Math`对象方法
* `Math.ceil()`上舍入
```js
    var num1 = 2.0;
    num1 = Math.ceil(num1);
    console.log(num1);
```
* `Math.floor()`下舍入
```js
    var num2 = 2.9;
    num2 = Math.floor(num2);
    console.log(num2);
```
* `Math.round()`四舍五入
* `Math.abs()`求绝对值
* `Math.PI`返回圆周率
* `Math.random()`获取0-1随机数
* `Math.random()*(max-min)+min`获取min到max之间的任意随机数
```js
    // 求5-10之间的随机数
    for (var i = 0; i < 10; i++) {
        console.log(Math.round(Math.random() * (10 - 5) + 5));
    }
```


#### 函数
* `function` 作用就是将一段代码包裹起来  把一段具有相对特定功能的代码块封装起来
```js
    function 函数名(){
        // 函数体代码
    }
    // 函数调用语法:
    函数名()
```

#### 函数的五种声明方式:
```js
    // 第一种 普通定义放式
    function func1(){
        console.log('我是函数的第一种声明方式')
    }
    func1('调用')
    //  第二种 委托式 
    var func2 = function(){
        console.log('我是函数的第二种声明方式')
    }
    func2('调用')
    // 第三种 函数构造式 几乎不用  这种定义函数方式里,函数体代码是用字符串表达的 new Function()的最后day8 demo02补充
    var func3 = new Function('console.log("我是函数的第三种声明方式")')
    func3('调用')
    // 第四种 箭头函数或lambda表达式
    var funnc4 = () => {
        console.log('我是函数的第四种的声明方式')
    }
    func4('调用')
    // 第五种 匿名函数 在做面向对象闭包封装开发时,可以利用函数的局部作用域,来用匿名函数保护对象的作用域
    (function(){
        console.log('我是匿名函数');
    })('调用');

```
#### 函数普通声明和委托式的区别
  - 在浏览器开始运行`script`标签里的`js`代码时，会先对整个代码进行一次预编译预解析
    那么浏览器的解析引擎v8做这件事的目的就是，把代码先过一遍，主要是找代码里是否
    存在"`function` 函数名(){}"，如果存在，则将`function`(){}函数直接先预解析到浏览器内存中，
    总结：原来`function`(){}这货是个`VIP`呀，在第一遍全文预编译预解析时，整个代码里所有的
    `function`会被先提出来，这些佬会优先进入到内存中
    但是，如果将`function`赋值给一个变量时，那么就会在逐行运行时，当运行到这个`function`变量时，
    这时才开始运行赋值运算符右边的`function`，那么这个`function`进入内存的时间就慢了很
    重点：`function`是一群特殊的群体，有钱人，`VIP`，它们在内存里存储时，根本不和那些低俗的变量
    在一个环境里存储，而是在一个叫“函数栈区（`VIP`包厢）”里单独存储

# `day5`
#### js编程语言的作用域
- 作用域在编程里其实就是指可以使用的范围!
  - 小括号:提高表达式优先级
  - 中括号:声明数组集合用的语法
  - 大括号:语法和函数或代码块或对象`JSON`的使用,大括号有一定的限制作用域的功能
    - 普通大括号无法限制作用域
    - 选择判断的语法的大括号都无作用域限制
    - 在循环语法里无作用域限制
    - 函数无论哪种声明方式,都是有作用域的,函数最终进入独立的函数栈区
  - 总结:除了函数其他语法都无作用域,函数可以调用任何语法作用域中的变量,但是其他语法不可以使用函数中的变量,由于函数是独立预编译解析到内存中的,并且是首先进驻到内存里的
#### 局部变量和全局变量
- 总结:只要定义在函数里的变量就是局部变量,不定义在函数里的就是全局变量,函数可以使用全局变量,全局不能使用函数的局部变量

#### 全局变量分两种,分别是带`var`和不带`var`的变量
  - 不带`var`声明的变量其实就是被一个全局对象所管理的,这个对象叫`window`,被`window`对象管理的成员,`window`可以不写,
  - 带`var`声明的变量其实也是window管理的变量,所以都是全局变量.
  - 在函数里声明一个不带`var`的变量,函数里不带`var`的变量其实就是在使用一个变量,使用的是函数外边的全局变量,但是变量在未声明时,则将此变量自动归到window下进行管理.
  
#### 解释函数的变量作用域提升的问题:
  - 总结:函数带`var`的变量数据函数内部局部变量,那么不带`var`变量,会首先在函数找是否声明了此变量,如果没有声明,则此变量作用域自动提升为了全局变量,最终还是被`window`管理,这就是函数的变量作用域提升的问题.


#### 定义函数参数
```js
    // 函数里定义的参数叫形参
    function 函数名 (参数1,参数2....定义形参){
        // 函数代码块
    }
    // 调用函数  函数调用传递的值叫实参
    函数名(参数值1,参数值2....传递实参,可以传任意类型)
    // 函数的参数就是函数里的一个局部变量,用一个局部变量接受了全局变量,这样就不会污染全局变量的值,并且函数的局部作用域之间并无任何关系,就是说不同函数同名变量之间毫无任何关系
```
- 总结:在`js`语言体系里,只要不是在函数里定义的变量,都是全局变量,无论加`var`或不加`var`,包括在普通语法里定义变量也是全局变量

#### 函数`function`三大要素 之一`arguments`的使用:
- `arguments`一般是在不确定函数参数时,可以考虑使用`argunebts`
- `arguments`关键词 只能在函数中使用
  - 无论是否定义了形参,函数内都有一个`arguments`关键词来帮你装所有实参,`arguments`是一个类数组的变量,其真实类型是`arguments`类型,说起来是伪数组,数组的基本操作方式都可以使用,但是一些`API`方法伪数组不能使用,无论是否有形参,都不影响`arguments`操作
  - 可以用`Object.prototype.toString.call()`来查看真实类型
  - `arguments callee()`使用递归时,函数调用自己,也可以用`arguments callee()`方法来调用函数自己,做到函数的调用
```js
    func3('oh!shit!', 123, true, [1, 2, 3]);
    function func3(str1, num1) {
        console.log(arguments, Object.prototype.toString.call(arguments));
        console.log(arguments[0], arguments[1]);
    }
```
- `return`
- `this`
  - 在函数使用时,`this`默认指向了`window`

#### 最权威的前端字典文档: MDN
#### `Array.from`()使用:
  - 可以使用`Array.from`()把伪数组转换为数组 

#### 面试题: 什么样的集合可以被`Array.from`()转换成数组?什么样的可以用length属性,可以被for循环?可以使用索引呢?
- 伪数组类型的`Arguments``DOM`集合`DOMCollection`等等都可以被`Array.from`()方法调用并转换成真数组类型,
- 伪数组不能用真数组的一些`api`方法,比如`push``pop``sort`等等
- 字符串虽然可以被`for`循环,有`length`,有索引,但是字符串不是伪数组类型,字符串就是`String`类型
- 在`js`语言体系中,可以被`for`,有索引,有`length`的数据,在`js`底层,这种数据他们在底层都实现了一个类型,叫`iterator`(迭代器类型),所有在底层继承了`iterator`(迭代器类型)的数据都有`for`循环,都有`length`和索引的操作.
- 伪数组和真数组都可以用`length`和`for`和索引.

#### 函数内部局部作用域在外面接收
```js
    var num1=1,num2=2;
    func1(num1,num2)
    function func1(num1,num2){
        var num = num1+num2;
        // 可以将函数内部莫个作用域成员交给window,这样在函数外就能获取到window成员
        window.num = num
    }
    console.log(num)
```
#### `return`使用:
  - `return`在函数代码里,如果碰到`return`则后面的代码将不再运行,函数将`return`前的代码执行完后遇到`return`后,函数代码执行完毕
  - `return`后面可以接一个值,这个值得作用就是函数在运行完后,可以将函数里的一个数据返回出来给外边公共空间去使用

- 无参无返回值得函数 5%都用不到
- 有参数无返回值得函数  15%
- 有参有返回值的函数    80%

- 函数的返回值`return`是函数的一个关键要素,函数内部是一个局部作用域,那么要将函数里的一个数据返回出来给外边用,就必须要用`return`将值从函数里返回出来

#### 函数重载
* 重载的意思就是两个函数的函数名一样,但是函数的参数值不一样,这个是后端的概念,在前端此概念简洁化为同一个函数,参数不同时所执行不同的代码逻辑
```js
// 如果只传一个参数，则直接返回此参数结果，如果两个参数，则返回两个参数相加的和，如果三个参数
// 则返回前两个相加再乘以第三个参数的结果，如果没传参，则返回一个-1
var result1 = func1();
    console.log(result1);
    var result2 = func1(5);
    console.log(result2);
    var result3 = func1(1, 2);
    console.log(result3);
    var result4 = func1(1, 2, 3);
    console.log(result4);
    function func1(num1, num2, num3) {
        if (num1 && !num2 && !num3) {
            return num1;
        } else if (num1 && num2 && !num3) {
            return num1 + num2;
        } else if (num1 && num2 && num3) {
            return (num1 + num2) * num3;
        } else {
            return -1;
        }
    }
```
  
#### 函数作用域链的问题:
- 所谓函数的作用域链,就是当函数嵌套运行时,最内层函数要使用的变量,可以使用上一层函数里的变量如果内层函数的变量在上一层函数中找不到时,则会继续找上上一层,最终找到全局环境是否有无此变量,当然上边说的变量都是在函数中直接使用的变量,不加`var`的变量
- 函数外边没有其他函数作用域包裹，所以里边如果没有var则表示使用的是全局变量
- 代码实际时,是从最外层函数往内层函数运行,但是作用域则是看每层函数的脸面如果函数使用`var`声明变量了,则表示当前作用域链的变量是从声明了`var`变量函数开始看起

#### 闭包
- 函数是有独立作用域的,函数内部的局部变量在函数执行完后,应该是触发浏览器的垃圾回收机制会被内存回收,可是这时,如果在函数内部又来了一个局部作用域的函数,并且此内层函数使用外层函数的局部变量,导致外层函数里这个变量不能被内存回收,因此外层函数里的这个不能被内存回收的变量就是一个闭包环境变量,这就是'真·闭包原理'
- 闭包使用过多,会产生性能问题,会导致有过多的变量无法被回收,最终导致内容溢出!
- 闭包的终极奥义思路:在函数内部的局部变量,通过函数内部的函数来进行操作,最终将操作函数局部变量的这些函数`return`出去就`OK`了

- 闭包会浪费内存,需要根据代码结构来合理的释放掉一部分的闭包变量所占的内存,但闭包很难完全释放
```js
    function func3() {
        var num1 = 1;
        function func4() {
            num1 = 2;
            console.log(num1);
        }
        func4();
    }
    func3();
```

  
# `day6`
#### 回调函数
- 回调函数`callback`简称(`cb`)其实就是将函数作为一个参数传递到另一个函数中去按需执行的过程.
```js
    sum(1, 2, function () {
        sum(3, 4, function () {
            sum(5, 6, function () {
                sum(17, 8, function () {
                    sum(9, 10, function () {
                        sum(11, 12, function () {
                            console.log('不玩了不玩了');
                        });
                    });
                });
            });
        });
    });
```
  
#### 递归
- 任何编程语言都有递归的思想,递归不是什么固定语法,是一个思想递归的使用,其实就是函数自己调用自己
- 总结:递归在使用时,跟循环的一些思路是一样的,比如说递归执行条件变量,终止递归条件判断更新递归的条件变量
- 一般来说,处理一些有一定规律的业务逻辑时,可以考虑用递归来处理,根据情况判断其实也可以考虑用循环处理
- 终止递归的条件就是if-else
```js
    /* 
        利用递归，打印输出10次，好好学习，天天向上
    */
    var count = 1;
    goodStudy(count);
    function goodStudy(count) {
        if (count > 10) {
            console.log('结束了！不玩了！');
        } else {
            console.log(count, '好好学习，天天向上');
            count++;
            // goodStudy(count);
            arguments.callee(count);
            console.log('观察count变化：', count);
        }
    }
    // 利用递归计算1-100的和
    var sumResult = 0, num = 0;
    sumResult = sum(sumResult, num);
    console.log('1-100的和是：', sumResult);
     function sum(sumResult, num) {
    if (num <= 5) {
        // 满足递归条件时，在这个if里处理递归流程
        sumResult += num;
        num++;
        return sum(sumResult, num);
    }
    return sumResult;
```

#### 递归的执行原理
- 递归在执行时,从外边第一次方法的调用开始执行,这时如果在执行过程中又碰见要调用自己的时候,则导致上一次调用未执行完,然后根据条件判断不断调用自己执行时,当某一次彻底执行完后,则会沿着调用自己的路线反着往回把未执行完的其他自己全部执行完就`ok`了

#### 递归面试题:
```js
    /* 
        递归面试题：
        现有一数列：1，1，2，3，5，8，13，21········
        请用代码表达第21个数应该是几？
        这道题就是有名的斐波那契数列，也就是所谓的黄金分割定律，这个也是有名的二叉树算法
    */
    // 参数n表示第几个数
    var result = fib(20);
    console.log(result);
    function fib(n) {
        if (n <= 2) {
            return 1;
        } else {
            // 在每一次递归时，除了return和加号没执行，两个递归方法是执行的
            // 而最终时，在return和加号之间，优先执行加号
            return fib(n - 1) + fib(n - 2);
        }
    }
```

#### 函数的柯里化,其实就是在函数内部,返回又是一个函数,这样就形成了函数调用时通过多次的小括号调用来获取最终要执行的函数
```js
    function func2() {
        var num = 123;
        return function () {
            var newNum = num;
            return newNum;
        }
    }
    var newNum = func2()();
    console.log(newNum);
```

#### 对象:
1. 定义对象的描述信息
2. 将对象实例化出来,并且实际可以使用才`OK`
- 在利用`funxtion`声明对象描述时,函数名首字母大写

#### `js`对象创建原理
* 在使用关键词`new`来调用函数时,这时会在内存的公共区域空间里根据`new`创建个对象来接收new的函数调用
* 在公共空间里通过`new`调用函数时,会开辟一个空间来接收函数里所有`this`描述的对象的信息数据,包括对象的属性和方法.就是说普通在函数里定义的`var`变量和`new`没有丝毫关系
* 函数既可以做代码的封装,又可以做对象的封装,那么普通函数里是不用`this`的,而对象函数里是需要使用`this`的,`this`的关键作用就是要和`new`搭配使用,当对一个函数进行`new`的调用时,则会触发内存重新开一块空间将`new`调用的函数结果存到这个空间中,并且函数里所有的`this`就自动的转换指向,指向到`new`调用后的函数之后的那个内存空间里,这个内存空间就是一个对象数据,其数据类型是`Object`

# `day7`

- 通过函数创建对象,只是对象的第一种创建方式,而这种创建方式在实际编程的作用主要是包装代码用的,`js`还提供了另外的一种创建对象的方式,语法就是`new Object()`但是实际开发时,`js`底层已经将`new Object()`做成语法糖,这种对象的使用方式是偏向对象方向使用的
  
#### `JOSN`对象数据创建对象方式:
```js
    var 对象名 = {
        键(key):值(value)
        .....
    }
    // 通过上面这种方式,`json`对象还有别名,叫'键值对'数据,英文名叫`key-value pair`
    // `json`里的`key`默认是字符串类型,引号可以不写,那么在根据键拿值时,可以通过'对象名.`key`名'来获取值,也可以通过'对象名[`key`名]来获取值'
    // 当不确定具体用哪个key时,那么[key名]的这种通过`key`获取值得方式就好用了,当确定了要使用莫个`key`时可以考虑用'`.key名`'的方式来获取值
```
#### `json` `for-in`循环
- 玩`json`使用`for-in`循环
```js
    for(var key in 对象名){
        console.log(key)
    }
    // 总结:碰到数组就用普通for循环,碰到json就用for-in循环
```

#### 补充`for-of`循环,可以对数组进行循环,不能对josn做循环
```js
    for(var value of 对象名){
        console.log(value)
    }
```
for
#### `JSON`独立作用域
- `json`也是有自己作用域的一种数据,所以,闭包可以和`json`一起使用

#### 面试题
1. 
```js
    var arr = func1();
    for (var i = 0; i < arr.length; i++) {
        arr[i]();
    }
    function func1() {
        var arr = [];
        // 这里改成let后，表示每次循环时，都重新创建了一个新的循环索引变量i，相当于每次循环时
        // 上一个i都被保留下来了，因此获取结果是0-9，但如果是var了，表示循环时，使用是同一个变量i
        // 这样，在方法未被调用时，循环一直操作一个变量，因此最后方法调用时，运行是最终变量的结果
        for (let i = 0; i < 10; i++) {
            arr[i] = function () {
                console.log(i);
            }
        }
        return arr;
    }
```
2. 
```js
    /* 
    当全局作用域和函数内的局部作用域里有相同变量时，
    函数内如果使用不加var的变量名，则优先先找函数内是否有这个变量定义，如果没有了，才去找全局
    但如果全局和局部有相同变量名时，那么局部变量的优先级最高，那么想使用全局变量时，则只能通过
    window来获取了
    */
    var num = 1;
    (function () {
        console.log(num);
        num = 2;
        console.log(num);
        console.log(window.num);
        var num = 3;
        console.log(num);
    })();
```

#### 小技巧:
- 在使用`vs code`时,将来使用某些js提供的资料时,如果看到智能提示里前边图标是紫色盒子时便是在使用的是一个方法(函数)如果是蓝色盒子时,表示是一个属性

#### `this`指向
- `js`中,`this`默认指向`window`当实例化后,就改变指向,指向实例化后的对象,在静态资方法里,`this`指向函数对象模板
  
#### 主动改变`this`指向
- 第一个`call`方法,
  - 所有函数的静态方法里都有一个叫call的方法,call如果在不改变函数里this指向时,会发现和普通调用一个函数没什么区别
  - `call`接收两个参数 第一个参数是改变`this`指向的参数,不该为`null`,后面的参数为函数的实参.形参有多少,实参有多少
```js
    var hero = {
        name:'李元芳',
        age:18,
    };
    function func1 (param1,param2,param3){
        // 打印形参
        console.log(param1,param2,param3)
        // 打印this
        console.log(this,this.name)
    }
    // this指向window  调用函数 传入实参
    func1('参数真好玩',1,2);
    //null不改变this指向, 所以this指向window, 后面参数是传入形参    
    func1.call(null,'呵呵',5,6)
    //改变this指向为hero  this指向hero对象,后面参数是传入形参
    func1.call(hero,'你好',7,8)
```

- 第二个`apply`方法
  - 两个参数第一个参数是改变`this`指向的参数,不该`this`指向为`null`,第二个参数以数组的形式传参,函数有多少形参,就往数组中丢多少实参
```js
    function func1() {
        console.log('又见面了func1函数');
        console.log(this);
        this.dinner = '八宝粥';
    }
    var funcc = new func1();
    func1();
    console.log('========================');
    func1.apply();
    console.log('========================');
    function func2(param1, param2, param3) {
        console.log('func2方法');
        console.log(param1, param2, param3);
        console.log(this, this.dinner);
    }
    func2(1, 2, 3);
    console.log('========================');
    func2.apply(null, [1, 2, 3]);
    console.log('========================');
    func2.apply(funcc, [3, 4, 5]);
```

#### `apply`和`call`的区别 
  * `apply`和`call`的区别在于,传递实参时,`call`和普通方法传递实参一样 demo10补充

- `bind`方法,出镜率最高
- 第一个参数也是改变`this`指向,第二个参数开始往函数传实参的使用方式和`call`一样,和`call`以及`apply`的超级无敌大区别在于,`call`和`apply`会立即调用函数,在调用时,改变函数里`this`指向`bind`方法不会立即调用函数,而是返回了一个改变`this`指向后的新方法,然后在手工调用
  
#### 原型链
- 函数有`prototype`,对象有`_proto_`,对象的`_proto_`指向了函数的`prototype`对象与对象之间的继承则是子对象函数模型的`prototype`指向了父对象的`_proto_`,最终此链一直向上指向了`Object`,如果`Object`再往上指就什么都没有了,就是所谓的`null`
- 原型将各个类型之间进行了继承操作
- 通过js的类型的原型继承关系,可以了解到每层类型本质其实都是个`function`函数因此,与其说`js`是基于原型的,会给人感觉是基于函数的继承编程
- 所有函数都有一个`prototype`原型子对象,函数只有`prototype`没有`_proto_`,所有对象都有一个`_proto_`子对象,对象没有`prototype`只有`_proto_`,对象的`_proto_`指向函数的`prototype`,这就是所谓的原型规则
- 所有对象都是基于函数产生的,包括`js`里的语法糖
- `_proto_`用来获取一个对象的上一级原型对象(如何知道一个对象直接继承那个对象)
```js
    function Son() {
        this.name = '哪吒';
        this.age = 20;
    }
    var neZha = new Son();
    console.log(neZha);
    console.log(neZha.__proto__ === Son.prototype);
```

#### 函数的`prototype`用法:
- 在对象模型的开发阶段时,对象方法会占用对象里大部分代码,为了提高方法代码的可维护性,节约维护成本,因此使用`prototype`将方法全国站到对象外边来使用
- 函数的`prototype`绝对了函数里`this`最终的归属


#### 面向对象编程的三大特征: 封装,继承,多态
- `js`是弱类型语言,在整个`js`语言体系里只有一个`prototype`来继承完成的,所以`js`本质没有多态
- 在`js`中面向对象的继承编程解决的问题,主要就是将一些相同业务逻辑代码抽离出来,封装到一个父对象函数模型里,那么最终就可以让各个模块的子对象函数模型通过`prototype`继承父对象即可

# `day8`
#### 函数的重写
* 对一个父对象已有的方法，在子对象里又拉出来写，这就是函数的重写`override`,`js`里函数的重写其实体现出来依然是就近原则
* 函数初始化时使用this来操作的成员(属性和方法)是函数的私有固定的成员！基于函数的prototype扩展的成员(属性和方法)，则可被拿来各种赋值给别的函数的prototype，以达到共享资源的目的
- `eval()`方法可以将一坨字符串作为一个正常的`js`代码去执行
  
#### 堆和栈讲解,值类型和引用类型
* 栈内存空间
  * 栈类型空间里主要储存一种叫值类型的变量,值类型变量在赋值时,是将自己的值`copy`一份赋值给对方的,结果就是不管修改那个值类型变量的值时,都不会影响到对方,其本质原理就是两个值类型变量的内存地址不同,值类型变量在赋值时,仅仅只是把值`copy`一份赋值给对方的操作
  * 值类型
    - `Number`,`String`,`Boolean`,`Null`,`Undefined`
* 堆内存空间
  * 堆内存空间里主要存储的是引用类型变量,那么引用类型的变量在赋值操作时,不仅仅将自己的值给到对方,并且将自己的内存地址也一起给了对方
  * 引用类型
    - `Array`,`Object(JSON)`,其他各种伪数组类型
* 总结 : 值类型变量赋值时,其实只是将值给对方,两个变量依然在操作两个不同内存地址的数据.引用变量赋值时,其实就是两个变量指向了同一个内存地址的值   


#### 面向对象的一种模块化封装思路:
* 对象的设计原则必须要保证单一性原则,每个对象只做跟自己对象有关的事情!在`js`,因为作用域的原因,所以需要使用`(function(){})()`;匿名函数对象封装的作用域进行保护管理,这种保护作用域的思想,我也把他叫'鲁棒设计思想',基于鲁棒性的设计思路,就可以将每个对象单独用一个`js`文件封装出去
* 面向对象编程时,对象与对象之间的耦合性很强,导致某个对象的数据发生变化时,其他对象的数据可能都要跟着变,这样子做很影响后期的维护,利用中间对象,将其他各个对象之间的关系进行解耦合,这种设计就能实现对象之间的松耦合,这种设计模式就是所谓的面向对象的'中介者模式'


# `day 9`
* `try-catch-finally`如何使用:
* 捕捉和处理异常
* 另一个妙用:用来释放闭包!贼爽
* 无论是try还是catch里的代码哪个执行，即便是有return，但是finally在这个语法体系里是被
  强制执行的，所以如果finally里有return，则最终函数的结果是以最后一个finally里的return为结果的
* `try-catch-finally`异常检测语法:
```js
    try{
        // try里放主要的代码块,就是我们平常所写的正常代码
    }catch(error){
        // 如果try里代码出现了bug,则try里其余的代码不再运行,会立即跳转到catch块里的代码开始执行
        // catch块里的参数error是一个异常对象,收集了try里碰到的异常信息
    }finally{
        // 此块可写可不写,根据实际情况的业务逻辑来合理使用finally,这个快的意思表示,不管代码在上边
        // 运行了try还是catch,最终都会执行finally块
    }
```

#### 面试题:

```js
   function func1() {
        try {
            var num = 123;
            return num;
        } catch (error) {
            return error.message;
        } finally { 
            var str = '呵呵';
            return str;
        }
    }
    console.log(func1());
```

#### 正则表达式
- 通过正则对象`test()`方法校验输入的值是否OK
```js
    // 第一种写法 第一个参数正则表达式是,第二个参数正则匹配规则
    var regex = new RegExp(正则表达式,正则匹配规则)
    
    // 第二种写法  其实就是第一种方式的语法糖
    var regex = / /
```
* 正则表达式在程序里应用时,其实就是用一种规则的表达式约束某个变量的值,在程序里对变量赋值操作时,用法律来约束变量只能是哪种值!
* 正则只是约束了输入数据的基本格式,那么对于有些数据的实际校验还需要进一步的功能才能确定.
* 只增变大时里,只要有两种符号,一种叫元字符,一种叫限定符
* `g`:全局匹配,`i`忽略大小写匹配,`m`忽略换行匹配
* 正则表达式的方法  `char()` 方法  `exec()`方法
- 元字符:
    - 元字符作用:主要是对用户输入的结果进行匹配
      1. 点:前端只有`string`类型,没有单字符的`char` 所以点在前端表示任意字符串结果值
      2. []:表示匹配满足中括号里条件的字符串结果,只要出现了中括号里的值就`OK`,中括号里可以写多个值,但是都是以单个值出现匹配的,中括号里的值如果在最开始加一个`^`表示非中括号里的其他值都`OK`
      3. \d:表示任意一个数字,其实就是[0-9]
      4. \D:表示出了数字以外的任意字符串都`ok`其实就是`[^0-9]`,表示非`0-9`之间的数字
      5. \w:表示匹配任意数字和英文字母和下划线符号的表达式,其实就是`[0-9a-zA-Z_]`
      6. \W:表示第5条反过来,其实就是`[^0-9a-zA-Z_]`
      7. \s:表示匹配空格字符串值
      8. \S:表示没有空格值得字符串都`OK`
- 限定符:
    - 对元字符匹配的结果进行进一步的限定,只要是长度的规定
      1. {n}:`n`表示一个数字,意思就是限定前边的那个元字符必须出现`n`的次数,相当于限定了字符串的长度
      2. {n,}:表示最少出现`n`次,最多出现无数次,也就是说,只要满足相应的元字符和限定符的长度就`OK`了
      3. {n,m}:表示最少出现`n`次,最大不超过`m`次,字符串中只要有连续出现nm次就`ok`
- 限定符的语法糖写法:
      1. *: 表示最少0次,最多出现无限次,就是{0},说简单就是有也行,没也行
      2. +: 表示最少出现一次,最多出现无限次,就是{1,}
      3. ?: 表示最少出现0次,最多出现1次,就是{0,1}问号有终止贪婪匹配模式
      4. ^: 在中括号里用是非的意思,在元字符前边使用,表示开头匹配
      5. $:在元字符后边匹配,表示结束匹配
      6. |: 表示或者的意思,就是
    - ():在正则表达式里有两个功能:
      1. 优先级功能
      2. 分组功能  
    - 转义符`\` 转意正则里面的关键词,转意成普通静态字符串 
    - 特出符号矫正 正则里面所有符号判断 `\x21-\2f\x3a-\x40\x5b-\x60\x7B-\x7F`
    - 断言正则 判断某个字符串组至少出现一次`(?=.*)`

#### 字符串`api`
- `charAt:`作用根据索引找到字符串里某个单字符,接受一个`number`参数,返回找到的那个字符串,如果索引找不到这个字,则返回一个空字符
- `concat:`作用字符串拼接方法,比`+`拼接的效率要高,参数时一个要拼接的字符串,返回一个拼接后的新字符串, 
  - 区别:` +`号拼接的字符串会在内存里留下来上一次拼接前的旧字符串变量
  - `concat`方法在拼接时,其实只是对内存里的一个字符串进行操作,不会遗留旧字符串
- `indexOf:`根据一个字符串参数,查找这个字符串在原字符串里第一次出现的索引位置,返回结果是字符串在原字符串里的索引位置,如果要找的字符串在原字符串里没有,则返回-1;  还有第二个参数意思是从当前字符串的某个索引开始找第一个参数出现的索引
- `lastIndexOf:`根据参数字符串在原字符串中最后一次出现的索引位置,从头开始查的,如果没找到依然返回-1;
- `match:`根据一个字符串结果匹配原字符串里是否出现这个要匹配的字符串,可以是正则表达式,返回一个数组结果,在数组最终显示所有匹配信息,匹配结果字符串有以下信息: 开头几个值是`match`方法的参数在原字符串里匹配到的值,`index`值表示在原字符串中匹配的值得索引位置,`input`值表示原字符串就是调用`match`方法的字符串值,`groups`表示匹配,这个值在正则里面有效,所以这个方法一般搭配正则表达式来用
- `replace:`可以指定原字符串里的某段字符串根据`replace`方法进行替换,第一个参数时原字符串里的某段字符串,第二个参数是要替换的新字符串,第一个参数也可以是一个正则表达式,当是正则时,表示正则替换,第二个参数可以是一个回调函数.
- `search:` 搜索参数字符串或正则表达式在原字符串出现的索引位置,返回一个索引值,只会按正则把匹配到第一个结果所在索引返回,`g`无效
- `slice:` 截取字符串,可以传负值,倒着截取
- `split:` 根据一个字符串值,对原数组进行分割,将分割后每段字符串结果放入到一个数组里
- `substr` 截取字符串
- `substring` 截取字符串 (此方法实际开发用的比较多) 两个参数 第一个参数表示从某个索引开始截取,第二个参数表示截取结束的索引位置,截取时包含开头位置的索引字符,不包含结束索引的字符
- `trim` 表示将字符串两边的空格去掉
- `trimStrart` 表示将字符串开头的空格去掉
- `trimEnd` 表示将字符串结束的空格去掉
- `startsWith`  表示字符串开头匹配,如果匹配则返回`true,`否则返回`false`
- `endWith` 表示字符串结束匹配,如果匹配则返回`true,`否则返回`false`

# `day10`
#### 数组`api`
* `toLowerCase` 转小写
* `toUpperCase` 转大写
* `join:` 作用就是根据一个表示字符串将数组里的每个部分连接起来转换成一个新的字符串并返回
* `reverse:` 作用就是将数组里的每个值进行反转
* `concat:` 作用字符串或数组拼接返回一个新数组或字符串
* `shift` 删除数组里的第一个元素,返回被删除的元素
* `pop` 删除最后一个元素,返回被删除的元素◊
* `unshift` 往数组的开头第一个索引位置加入一个新元素 返回新数组的新长度
* `push` 往数组的开头最后一个索引位置加入一个新元素 返回新数组的新长度
* `slice` 根据开始和结束索引截取一个数组,并返回截取一个新数组,包含截取部分,包含开头索引值,不包含结束索引值,支持负数,注意: 截取数组后不影响原数组长度,原数组的值也没影响
* `splice` 删除数组中一段数据,会改变原数组长度和原数组数据,此方法第一个参数是从哪个索引开始删,第二个参数时删除的个数,第三个参数到第N个参数的作用是往被删除的原数组里的那段数据放一段新数组进去,返回值将删除的一段数据放到一个新数组并返回,
  - 作用1: 删除数组里一串数据;
  - 作用2: 替换一个数组里数据;
* `reduce`

#### `delete` 可以删除数组或对象的某个元素 对象操作贼方便
* 删除数字里元素时,通过数组的索引删除某个元素
  - 删除数组里一个元素时,是将当前索引元素值干掉,变成`undefined`,输出是`empty`,但不影响数组的原始长度,相当于只是将那一项的值干为空值
  - pop()封装 demo5
* 删除对象里某个元素时,通过某个元素的`key`来删除
  - 在删除对象某个值时贼方便,大多情况都是用在操作对象使用的,而对数组操作可以使用`js`提供`pop``shift``splice`来操作 

#### `Date`的操作 
```js
    // Date底层其实就是个function(){} ,实例化Date后,可以获取到当前时间,返回类型是Object
    var date = new Date();
```
* `date.getFullYear()` 获取年
* `date.getMonth()` 获取月,老外的每年的第一个月就是`12`月
* `date.getDate()`  获取日
* `date.getDay()`  获取星期
* `date.getHours()` 获取小时
* `date.getMinutes()` 获取分钟
* `date.getSeconds()`  获取秒
* `date.getTime()` 获取到`1970-1-1`的毫秒数
* `date.now()` 获得当前时间距离`1970-1-1`的毫秒差时间戳

#### `Object` `api`
* `js`语言类型检测: `typeof`
* `instanceof` 此关键词返回一个`boolean`结果,判断一个对象时否时某个函数的实例化结果,如果是则返回`true`,否则`false`
  - 对普通值类型做类型校验时完全无效,对引用类型做校验时,非常有效,值类型使用`typeof`足以 
* `Object.prototype.toString.call()` 查看真实类型 
* `Object.create()` `create`方法接受一个参数,参数可以是一个已有的对象,如果新对象,则传null ,第二参数可写可不写
* `Object.assing()` 深拷贝将一个对象复制给另外一个对象,第一个参数表示当前变量的原始数据,第二个参数表示要把某个数据复制到第一个参数里 
  -  `Object.assing()` 只会对第一层数据做复制,但是深度的子对象和子数组数据并未做复制操作,而是直接赋值操作,所以`Object.assing()` 并不能成为深拷贝方法.`Object.assing()` 兼容性有问题,同时又不能深拷贝.
* `Object.keys()` 可以获取一个对象里所有的key
* `Object.values()` 可以获取一个对象里的所有value值
* `Object.defineProperty()` 在一个对象里动态定义属性的操作方法,,三个参数必须填
  - 参数1: 要操作的对象
  - 参数2: 要添加的新属性名字,字符串值
  - 参数3: 属性的约束定义规则, 就是刚才讲过`writable`(是否可以重写),`value`(初始值),`set`(属性设置值),`get`(获取属性值),
    - `configurable`(是否可以被删除) 这个配置项的作用是管理当前通过`definePrioerty`添加的属性的是否可以被`delete`删除,默认值是`false`,表示不能被`delete`删除
    - `enumerable`(是否可以被循环) 这个配置是管理`definePrioerty`定义的属性是否可以在`obj`的循环时被循环出来,默认值是`false`,表示不可以被循环输出此属性,也就是说,此属性不在循环列表里,循环无法获得此属性如果是`ture`就可以正常循环

#### 深拷贝封装 
```js
    var sourceObj = {
        name: 'xiaomin',
        age: 24,
        sub: {
            hehe: '好玩',
            xixi: 'assign废物',
            arr: [1, 2, { haha: '简直傻x' }],
        },
    };
    var targetObj = {};
    cloneDeep(sourceObj, targetObj);
    sourceObj.sub.hehe = '这次真的神了';
    console.log(targetObj, sourceObj);
    function cloneDeep(sourceObj, targetObj) {
    // 主要处理的数据是Object和Array
    for (var key in sourceObj) {
        if (Object.prototype.toString.call(sourceObj[key]) === '[object Object]') {
            targetObj[key] = {};
            cloneDeep(sourceObj[key], targetObj[key]);
        } else if (Object.prototype.toString.call(sourceObj[key]) === '[object Array]') {
            targetObj[key] = [];
            cloneDeep(sourceObj[key], targetObj[key]);
        } else {
            // 既不是对象，又不是数组时，就可以直接将数据赋值给目标对象里targetObj
            targetObj[key] = sourceObj[key];
            }
        }
    } 
```
#### `pop`封装 删除数组最后一个索引元素
```js
    Array.prototype.myPop = function () {
    var lastElement = this[this.length - 1];
    // 没有这行delete，如果只是强制让数组长度改变，那么强制被移除出去的变量依然残留在内存里，不会释放
    delete this[this.length - 1];
    this.length = this.length - 1;
    return lastElement;
    };
    var arr3 = [1, 2, 3, 4, 5, 6];
    var myDeleteElement = arr3.myPop();
    console.log(myDeleteElement, arr3);
```
# `day11`

#### 可以利用`debugger`来做代码中断调试
* `valueOf` 获取当前值 面试题demo04
#### 高阶函数: 从设计模式角度,也成称为装饰设计者模式,本质就是利用回调函数,来将用户的操作行为独立的封装传递
  - 高阶函数的处理私立
    1. 封装一个高阶函数,将几个函数里相同的业务代码抽出来封装
    2. 对于原来的几个函数里关键的不同行为操作时,利用回调函数的方式交给调用高阶函数的人来具体执行
  - 高阶函数的核心思路，就是把多个封装函数中，相同的业务代码抽出来，不同的业务代码交给回调函数来处理即可那么在这个里边，回调函数cb就是所谓装饰设计者，而封装的所谓的高阶函数，则是被装饰设计的那面墙

#### `javascript:`由三部分组成
- `ECMAScript:` 简称`es`,这部分包含整个所有js语言的底层及语法
- `DOM`(`Document Object Model`的简写)
- `BOM`(`Browser Object Model`的简写)

#### `DOM`
* `DOM`选择器`api`
  - `document.getElementById` 获取一个`id`值得`DOM`对象
#### `getArrtibute`方法
- 获取一个`DOM`对象的属性,主要是标签对象的属性
#### `setAttribute`方法
- 给一个`DOM`对象设置一个属性,此方法无返回值,两个参数
  
#### `onload`事件 
- 事件的本质执行行为都是通过函数代码来描述的,等标签渲染完成后,才执行`liad`事件代码

#### 面试题:为什么把`script`标签写到`body`的下边:
* 放到下边,不影响标签内容的渲染,提高渲染速度
* 在`js`中获取标签时,不需要再加`onload`事件了,可以直接获取
* 渲染速度快的原因,跟浏览器的底层渲染机制有关!
* `script`标签如果写到开头或`body`的标签代码中间,会导致底层渲染机制的`Layout`和`Painting`

#### 浏览器渲染过程:

# `day12`
#### 面试题demo01
#### `DOM`
* 选择器`api`
* 除了`byid`以外,其余的获取`DOM`对象的方法都是获得一组`DOM`,并且是一个伪数组类型的`HTMLCollection`
  - `document.getElementsByClassName` 返回伪数组`HTMLCollection`
  - `document.getElementsByTagName` 返回伪数组`HTMLCollection`
  - `document.getElementsByName` 此方法比较特殊,返回的不是伪数组`HTMLCollection`而是一个伪数组`NodeList`集合
  
#### `DOM`方法和属性
* `innerHTML`获取标签里的内容,
* `innerText`获取标签里的文本内容
* `attributes` 获取当前一个DOM对象里的所有属性,并且每个属性在`attributes`里是一个属性节点对象的方式存在的,想要从`attributes`里获得某个属性节点对象时,直接`attributes.属性名`获取当前属性节点的值
* `hasAttribute`方法可以判断`DOM`对象里是否有某个属性,有返回true,没有false,此方法接受一个参数,就是属性名即可
* `hasAttributes`方法判断当前`DOM`对象是否有属性,有返回true,没有false.
* `removeAttribute`方法接受一个属性名参数,表示从一个`DOM`里清除一个属性节点对象,无返回值
#### 节点操作`api`
* `nodeType`此属性获得当前节点的类型,此属性结果是个`number`类型的结果返回1.表示标签2.表示属性3.表示标签里的内容
* `nodeName`
* `nodeValue`
* `childNodes` 获取子节点  有文本节点


# `day13`
* `hasChildNodes()`有子节点返回`true`,无`false`
* `tabIndex` 标签里设置索引
* `tagName` 获取标签名
* `parentNode` 获取父节点
* `createElement()`创建一个虚拟标签对象
* `insertBefore()` 在一个`DOM`对象内部将一个参数`DOM`添加到第二个参数DOM的前边显示,虚拟DOM渲染到网页上之后才能被称为一个真实`DOM`
* `remcveChild` 删除节点
* `replaceChild` 替换节点,用第一个参数的`DOM`替换掉第二个参数的`DOM`
* `appendChild` 是往一个`DOM`里追加一个子节点`DOM`子节点`DOM`会被追加到最后一个位置
* `cloneNode` 此方法表示复制一个`DOM`,默认值克隆当前`DOM`对象,如果传参为`true`可以克隆`DOM`对象里的所有子节点都会被克隆进去
* `addEventListener`
* `children`  获取子节点 不包括文本节点 返回`HTMLCollection`伪数组
* `parentElement` 
* `parentNode`
* 
#### 虚拟`DOM`概念


`offsetParent`属性,获取当前`DOM`的有定位元素的父元素,找不到就是`body`
`offsetLeft` 获取当前`DOM`根据其外层定位元素的位置的左边距离,找不到就以`body`的左边为准
`offsetTop` 获取当前`DOM`根据其外层定位元素的位置的上边距离,找不到就以`body`的上边为准


# `day14`
* `clienLift` 获取盒子到左边边框的宽
* `clienTop` 获取盒子到左边边框的高
* `clienWidth`
* `clienheight`
* `scroll`操作时当前盒子必须有滚动条
  - `scrollWidth`
  - `scrollHeight`
  - `scrollTop`
  - `scrollLeft`

#### 读取`css`样式
* `currentStyle` 只支持`Ie`低版本
* `Computedstyle()`

* `URL` 全局统一资源定位符  简称路径
* `domain` 当前文件在浏览器里打开后的主域名,
* `referrer` 保存当前网页是被哪个网页链接打开的那个网页路径

### `bom`
* 弹窗三大佬
  * `alert`
  * `confirm`此弹窗方法是询问的方式弹窗,会返回一个`boolean`类型结果
  * `promt`

- `window.navigator.userAgent` 使用这个值,可以通过正则判断一些当前客户端的兼容性
- `innerWidth`  当前浏览器的可视化区域宽度的值,随着窗口变大变小都能影响这个值得变化
- `innerHeight` 当前浏览器的可视化区域高度的值,随着窗口变大变小都能影响这个值得变化
- `windew.screen`主要获取当前显示器的有关信息
  - `width` 显示器的宽
  - `height` 显示器的高
  - `availWidth`
  - `availHight`
  - `colorDepth`
  - `pixelDepth`
#### `location`
- `location`是`window`里的子对象,在浏览器里,主要针对当前页面的一些资源以及页面的路径有关
  - `href` 
  - `hash` 获取当前页面路径锚链接值
  - `reload`此方法作用在浏览器中,其实就是`F5`
  - `search` 此属性可以获取当前页面路径的?号后边的参数列表字符串的部分值
  - `assign` 此方法接受一个路径的字符串,做超链接跳转
  - `replace`此方法接受一个路径的字符串,做超链接跳转
    - 两者区别demo10
#### `history`
  - `back`
  - `forward`
  - `go`

#### 定时器
* `setTimeout()`两个参数,第一个参数是回调函数,第二个参数是时间单位毫秒,触发一次
* `setInterval()`两个参数,第一个参数是回调函数,第二个参数是时间单位毫秒,循环触发
* `clearTimeout`
* `clearInterval`

#### 定时器原理 demo13
* 异步代码主要有以下三种
  * 定时器语法代码
  * 事件
  * `ajax(Asynchronous Javascript and XML/HTML)`:异步无刷新请求
 
#### 定时器的底层执行原理

# `day15`
#### 事件`event`
* 事件语法三个组成部分
    1. 触发事件的对象,也就是绑定事件的对象
    2. 监听事件的监听器和所监听的事件名称(on+事件名)
    3. 当被一个外部行为影响时,最终所触发的事件函数

#### 事件底层讲解  例图

#### 触发事件的写法
* 第一种:`on+事件名写法`demo04
* 第二种:`addEventListener()` `add`(添加),`event`(事件)`listener`(监听器) 第一个参数: 事件名的字符串不用加`on`  第二个参数: 事件体函数 是一个回调函数 第三个函数: 这个参数时一个可选参数,是一个布尔类型的参数,默认值是`false`,表示从事件的冒泡开始触发执行.如果设置为`true`,则表示会主动从事件的捕获过程触发
  * 两者区别:`on`绑定的事件在赋值时,时借助了赋值运算符进行赋值时,同一个`DOM`对象如果绑定了两个相同的事件时,用`on`来绑定事件,那么后边的事件体函数会覆盖前边`on`绑定事件的事件体函数,相当于在操作同一个变量,被重新赋值
  * `addEventListener`方法在绑定事件时,其实是往底层的事件监听器上边去累加叠加事件,因此`addEventListener`在绑定事件时,我们也称为'追加事件'
  * 总结: 在实际开发时,为了让事件的代码更加灵活,在触发同一个事件时,可以保证前边的相同事件也会执行因此多用`addEventListener`是实际开发时的必选,`on`可以忘记了
    - 高版本`addEventListener`
    - 低版本`attachEvent`  区别后绑定的先执行 第一个参数必须加`on`
* `removeEventListener()`可以针对以传参方式绑定事件函数时
* `mouseover`鼠标划入某个`DOM`上时触发该事件
* `mouseout` 鼠标划出某个`DOM`上时触发该事件
* `mouseenter`鼠标进去某个`DOM`时触发该事件
* `mouseleave`鼠标离开某个`DOM`时触发该事件
    - 如果只作用在一个`DOM`上时 ,用哪一对都行但是如果在嵌套的`DOM`结构上使用时,要注意`mouseover`和`mouseout`会触发事件冒泡`mouseenter`和`mouseleave`不会触发事件冒泡,
* `mousemove` 鼠标在某个`DOM`对象上移动时触发的事件
* `mousedown`鼠标在某个`DOM`对象上按压鼠标按钮时触发的事件
* `mouseup`鼠标在某个`DOM`对象上松开鼠标按钮时触发的事件
    - 触发顺序`mousedown`  >  `mouseup`  >  `click`  
* `keydown`  按下键盘的某个键就立即触发的事件
* `keyup`   松开键盘触发
* `keypress` 一直按着某个键不松开始,一直触发的事件
* `scroll`
* `resize`就时浏览器窗体改变大小时触发的事件
* `hashchange` 时在当前页面的锚链接路径发生变化时会触发的事件 demo12多看看
* `contextmenu`浏览器按下鼠标右键时会触发此事件,相当于可以屏蔽掉浏览器的默认的右键快捷菜单,然后自定义一个新的菜单给自己用,这个事件主要作用就是唤起鼠标右键的快捷菜单,但是浏览器默认自带的有右键快捷菜单,所以想办法先干掉这个右键快捷菜单,然后召唤自己的快捷菜单即可
* `dblclick`鼠标的双击事件
* `blur`失去焦点时触发的事件
* `focus`鼠标的光标选中某个`DOM`时触发的事件 获取焦点
* `change`当表单里的值发生改变时触发事件,在鼠标焦点离开表单元素时,才获取到当前表单元素里的内容
* `input`当表单的值发生改变时触发事件,随着改变一直触发该事件
#### 事件对象
* `e || event`
  - `e.button` 获取当前按的是鼠标哪一个按键
  - `e.keyCode`判断当前在键盘上按下的哪一个按键 
  - `e.clientX` 获取当前鼠标点击时的位置距离浏览器屏幕的左边距离,不包含滚动条距离
  - `e.clientY` 获取当前鼠标点击时的位置距离浏览器屏幕的上边距离,不包含滚动条距离
  - `e.pageX`获取当前鼠标点击时的位置距离浏览器屏幕的左边距离,包含滚动条距离
  - `e.pageY`获取当前鼠标点击时的位置距离浏览器屏幕的上边距离,包含滚动条距离
  - `e.offsetX`获取当前鼠标点击的位置到当前`DOM`对象的左边距离
  - `e.offsetY`获取当前鼠标点击的位置到当前`DOM`对象的上边距离
  - `e.screenX`获取当前鼠标点击的位置到显示器的左边距离
  - `e.screenY`获取当前鼠标点击的位置到显示器的上边距离
#### 事件冒泡
  - `e.stopPropagation()` 高版本阻止事件冒泡
  - `e.cancelBubble = true` 低版本阻止事件冒泡
#### 事件委托
* 处理事件冒泡最好的手段就是事件委托
  - `e.target` 
  - `e.srcElement`
  - 事件委托在操作时,指定一组嵌套DOM来 demo16

# `day16`
* 浏览器默认行为
  - `e.preventDefault`

# `day17`
* `className`

# `day18` 

# `day19`

# `day20`
<!-- 郭哥 -->
# `day21`
#### `jQuery`


#### jquery和js的对比
1. 入口函数  `jquery` 可以有多个入口函数 并且比`js`的入口函数触发时机早
2. 容错性    `jquery`的容错性要好于`js`
3. 兼容性    `jquery` 不需要考虑兼容性 内部已经处理
4. 操作复杂性 `jquery`操作简洁
**jquery的特点/优点**
1. 强大的`dom`选择器
2. 丰富的动画
3. 灵活的`ajax`
4. 完整的事件机制
5. 完美的插件解决方案
- `js`:作者 布兰登爱奇
- `jq`：约翰莱西阁

##### 基本选择器
- `ID` 选择器 `$('#box')`
- 类选择器  `$('.box')`
- 标签选择器 `$('p')`
- 并集选择器 `$('p,a,#box,.aa')`
- 交集选择器 `$('div.aa')`
##### 层级选择器
- 子代选择器 $('ul>li')
- 后代选择器 $('ul li')
#### 过滤选择器
```js
    :eq(index) 第几个元素 下标从0开始
    :odd 选择奇数
    :even 选择偶数
    // :first :last   
    :gt() 大于某个索引 $('ul li:gt(3)')
    :lt() 小于某个索引
```
#### 筛选选择器
- `children(selector)` 一级孩子 `$("#box").children("p")   $('#box>p')`
- `find(selector)`  所有孩子 `$('#box').find("p")       $('#box p')`
- `siblings(selector)` 其他兄弟们 `$('ul li:eq(1)').siblings()`
- `parent()` 父级  `$('p').parent()`
- `parents()` 父级们   `$('ul>li').parents("body")`
- `fisrt()`  该元素的第一个元素 `$('ul li').first()`
- `last()`   最后一个元素
- `index()` 直接可以通过这个方法  获取该元素的索引（所有的兄弟们里面排行老几）
#### 动画`API`
* 以下`api`参数
  1. 参数一:时间 单位(ms) 可以用固定字符串参数`slow`(相当于`600ms`)`normal`(相当于`400ms`)`fast`(相当于`200ms`)
  2. 参数二:回调函数 
- `show()`显示 `hide()`隐藏 `toggle()`显示和隐藏切换
- `slideDown()`划入 `slideUP()`划出 `slideToggle()`划入划出之间切换` 
- `fadeIN()`淡入 `fadeOut()`淡出 `fadetoggle()`淡入淡出切换 `fadeTo()`变化到指定透明度
* `animate()` 自定义动画 多值同时缓冲运动 
  - 参数:参数1:传入`json` 
        参数2:过渡时间 单位`ms` 支持固定字符串  默认`normal 400ms`
        参数3:速度形式 `linear` 默认`swing `
        参数4:回调函数
#### `Class`相关`API`
- `addClass()` 添加类
- `removeClass()`移除类
- `hasClass()` 判断是否有类 返回布尔值
- `toggleClass()`切换类

# `day22`
#### `stop()`讲解
* 两个参数
    - 参数1:是否清除队列  布尔值  默认`false(不清除动画队列,后续动画还可以执行)`
    - 参数2:是否跳转到当前动画的最终效果 布尔值  默认`false()`当前动画直接停止住,不会跳转到最终效果

* `finish()` 停止当动画之后 直接跳转到所有动画队列所有效果

#### `jQ` 的
* 添加方法
- `append(B)`  把B放到A的里面的最后
- `prepend(B)` 把B放到A的里面的最前面
- `after(B)`  把B放到A的后面
- `before(B)`   把B放到A的前面
* 清除内容
- `empty()` 清除里面内容
- `remove()` 清除本身及里面内容
* `jq`的克隆方法
  -  `clone()` 直接克隆元素本身以及内部子元素,无法克隆事件
     -  参数1: `clone(true)`可以克隆事件
#### `jq`的属性操作
- `attr()`获取或者设置属性
- `removeAttr()`移除属性
- `prop()` 这个属性针对表单获取到布尔值属性,也可以获取到里面的属性
- `width()` 设置或获取宽
- `height()` 设置或获取高
- `offset()` 相对于文档`douument`的距离 可以设置
- `position()` 获取相对于其最近定位的父级元素的位置,只能读取不能设置
- `scroll()` 滚动事件
- `scrollTop()`
- `scrollLeft()`
#### 阻止默认行为
- `e.preventDefault()` 阻止默认行为
- `return false()`也可以阻止默认行为 也可以阻止事件冒泡

# `day23`
* `jq`事件绑定
  - `.bind()`
  - `.delegate()`
  - `.on()`
* `jq`的解绑
  - `.off()` 普通绑定解绑
  - `.unbind()` `.bind()`绑定解绑
  - `.undelegate()``.delegate()`绑定解绑
  - `.off()``.on()`绑定解绑
* `trigger()` 可以用来自定义事件
* `each()` 可以遍历非`JQ`对象的元素
* `$.noConflict()`释放$控制权

#### `jquery`插件
- `jQuery.fn.extend(obj)` 扩展jq对象的方法,常规的开发插件的方式
- `jQuery.extend(obj)` 扩展jq工具函数的方法

* `jq的颜色插件`

# `day24`
# `ajax``(Asynchronus javascript and xml)`
- `localhost` 本地服务器地址  或者`127.0.0.1`
```js
     var xhr = new XMLHttpRequest()
        xhr.open('get','hello.txt',true)
        xhr.send()
        xhr.onreadystatechange = function(){
            if(xhr.readyState == 4){
                if(xhr.status == 200){
                    alert(xhr.responseText)
                }
            }
        }
```
- `open()` 参数一:请求方式 `get/post` 参数二:请求地址路径 参数三:是否为异步 `true` 异步  `false` 同步
- `send()`

#### `ajax``get`和`post`的区别
  - `get`
    1.  数据是以键值对方式串联,数据对之间用&来串联,最后通过?号附加到`url`地址后面,传向后端
    2.  因为`get`的数据到地址`URL`后面,所以有长度限制(URL地址有长度限制)
    3. 相对而言 `get`安全性较差 (安全性后端会有加密存储)
  - `post` 
    1. 数据放到请求头的`from-data`中传向后端
    2. 理论上可以无限,但是服务端有限制
    3. 相对而言安全性较高一些
    - 代码层面 `post`需要设置请求头的编码格式

#### 状态码介绍
- `readyState``ajax`状态码
- `status` 服务器状态码

#### 处理中文或者特出符号数据进行编码
- `encodeURI()`编码  `decodeURI`解码

#### 解决`ajax` `get`请求 缓存问题

1658261070@qq.com

# `day25`
# `day26`
##### `ajax`跨域问题

```js
// 数组去重
arr[1,2,3,4,5,6,1,2,3,456,78,1,23,0]
arr[... new Set(arr)]
```

# `h5 c3`
#### `Object.assign()` 深拷贝方法  可以拷贝字符串数组和对象

# `css3`
- 属性选择器 
  - `E[attr]`
  - `E[attr=value]`
  - `E[attr*=value]`
  - `E[attr^=value]`
  - `E[attr$=value]`
- 伪类选择器
  - `nth-child`
  - `first-child`
  - `last-child`
  - `nth-last-child`
  - `nth-of-child`
  - `nth-last-of-type`
  - `first-of-type`
  - `last-of-type`
  - `::after`
  - `::before`
- 颜色表示方式
  - `rgba`
  - `hsla` 
    - h色相 0--360
    - s饱和度 0--100%
    - l亮度  0--100%
    - a透明度  0--1
- 阴影 
  - 文本阴影 
    - `text-shadow` 
    - 参数水平偏移量 
    - 垂直偏移量  
    - 模糊半径 
    - 颜色
- 盒子阴影
    - `box-shadow`
    - 参数水平偏移量 
    - 垂直偏移量  
    - 模糊半径 
    - 颜色
    - 可选参数 (inset 内阴影)
- 盒模型
    - `box-sizing : border-box`
- 圆角
    - `boder-radius`
    - `boder-top-left-radius`
    - `boder-top-right-raius`
- 渐变
  - `background-image:linear-gradient(参数)`
    - 参数1: 方向或者角度 `to right/left/top/bottom` 或者 `45deg`
    - 参数二: 颜色值 可以加多个颜色 颜色值后面可以添加百分比
  - `background-image:radial-gradient(参数)`
    - 参数一: 半径 at 放射方向
    - 参数二: 后面可以加多个颜色 
```css
    animation: move 2s linear infinite; 
    @keyframs move{
        from{}
        to{}
    }
```
- 背景尺寸
  - `background-size:` 用来设置背景图像大小
    - 可以写固定像素   可以设置百分比   
    - 可以设置cover  会覆盖全部的盒子区域 保证图片比例不变形
    - 可以设置为contain 图片比例不变形 尽可能显示全部图片
- 过度动画
  - `transition:`
  - `transition-property` 过渡属性
  - `transition-duration`  过渡时间
  - `transition-timing-function`  过度速度形式
  - `transition-delay`  延迟
- `calc` 计算

- `2D`转换
  - `transform:scale(x,y)` 缩放
  - `transform:translate(x,y)` 移动
  - `transform:rotate(角度)` 旋转
  - `transform-origin:center top;`  改变旋转中心点  默认左右居中 上下居中
  - `transform:skew()` 斜切
- `transform-style:preserve-3d` 让当前盒子 真正呈现出3D空间
  - `perspective` 透视距离
- `3D`变换旋转
  - `transform:rotateX` 元素围绕着X轴进行旋转 负值往前转,正值往后转
  - `transform:rotateY` 元素围绕着Y轴进行旋转 正值往右转,负值往左转
  - `transform:rotateZ` 元素围绕着Z轴进行旋转 正值顺时针转,负值逆时针转
- `3D`位移
  - `transform:translateX` 元素沿着X轴位移 正值向右位移,负值向左位移
  - `transform:translateY` 元素沿着Y轴位移 正值向下,负值向上
  - `transform:translateZ` 元素沿着Z轴位移 正值往前,负值往后
- `3D`缩放
  - `transform:scaleX` 沿着X轴进行缩放
  - `transform:scaleY` 沿着Y轴进行缩放
  - `transform:scaleZ` 沿着Z轴进行缩放
- `backface-visibility:hidden` 让元素的背面隐藏
- 关键帧动画
```css
    #box{
    /* 调用动画 */
    /* animation: 简写*/
    /* animation-name: 定义好的动画名字 */
    /* animation-duration: 动画的总执行时间 */
    /* animation-timing-function: 动画速度形式 linear匀速 ease-in-out 慢快慢 */
    /* animation-delay:动画延迟时间 */
    /* animation-iteration-count:动画播放次数 */
    /* animation-fill-mode:动画播放之后的状态 forwards保持结束后的状态 */
    /* animation-direction:循环播放动画时 交叉动画 alternate交叉动画 */
    /* animation-play-state:动画播放的状态,paused暂停 running播放 */
    }
    /* 定义动画 */
    @keyframs 动画名字{
        /* from{
            初始状态从**开始  
        }
        to{
            结束状态**结束
        } */
        /* 也可以加百分比 */
        0% {

        }
    }
```
- `transitionend`事件 用这个事件 来判断当前的过渡是否完成

- 弹性盒子

##### 移动端
##### 背景裁切
- `background-clip`

##### 
- `touch`事件
- `touchstart` 手指开始触碰屏幕的时候 触发
- `touchmove`手指触屏之后的滑动 持续触发
- `touchend` 手指离开屏幕触发这个事件
- `touchcancle` 手指触碰屏幕 突然中断的时候触发


##### `ES6` 

##### `Vue`
- `methods`
