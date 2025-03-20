# JavaScript 简要手册
# [2025.3.21进度 - 异常处理](https://www.runoob.com/js/js-errors.html)

## 引入
1. 可以在HTML文档中放入不限数量的脚本`script`
2. `Javascript`脚本代码可被放置在HTML页面的`<body>`和`<head>`部分中
3. HTML中的`Javascript`脚本代码必须位于`<script>`与`</script>`标签之间
4. 通常的做法是把函数放入`<head>`部分中，或者放在页面底部。这样就可以把它们安置到同一处位置，不会干扰页面的内容
5. 可以通过`<script src="JavaScript.js"></script>`来外部引入`JavaScript`脚本

## 语法
- 注释:
> ```javascript
> // 这是一段行注释
> /* 这是
>     片段注释 */
> ```

- 变量:
> ```javascript
> // 在ES6之后，推荐使用let来定义一个变量
> // 当然也可以使用var指定全局变量
> // 全局变量属于window属性
> var s; // s 是函数/全局范围内变量,如果在全局作用域中声明,s会成为全局对象的属性
> let x; // x 是块范围内变量,如果在全局作用域中声明,x不会成为全局对象的属性
> const y; // 定义常量y,一旦定义后，将不能被修改
> ```

- 使用`function fn()`来定义一个函数。
> 定义一个名为`MyFunc`的函数:
> ```javascript
> function MyFunc(){
>   // My code here
> }
> ```

- 正则表达式  
**Pendding:** [正则表达式相关](https://www.runoob.com/js/js-regexp.html)  
  

- 作用域与生命周期
> 与多数语言相同，不做阐述

## 数据类型
1. 值类型(基本类型)：字符串（String）、数字(Number)、布尔(Boolean)、空（Null）、未定义（Undefined）、Symbol
2. 引用数据类型（对象类型）：对象(Object)、数组(Array)、函数(Function)，还有两个特殊的对象：正则（RegExp）和日期（Date）
3. **JavaScript 拥有动态类型。这意味着相同的变量可用作不同的类型**
4. 变量的数据类型可以使用 typeof 操作符来查看:
> ```javascript
> var x; // typeof x 将返回undefined
> var x = 5; // typeof x 将返回number
> var x = "John"; // typeof x 将返回string
> ```
- 运算符：
> 与多数语言相同，不做阐述
- 空值:
> ```javascript
> // 通常来说，当一个变量被定义但是却并没有被赋值
> // 此时则等价于: Value = undefined
> let Value; 
> Value = null; // null可以用于清空变量
> ```

- 字符串: 可以为`""`,也可以为`''`
> ```javascript
> let Str1 = "JavaScript Here";
> let Str2 = 'Hello';
> ```

- 数组:
> ```javascript
> let Array = [40, 100, 1, 5, 25, 10];
> ```

- 对象:
> ```javascript
> let person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
> ```

- 显式声明对象类型
> ```javascript
> let x = new Number(10); // 显式的声明x是值为10的数值类型
> ```

- **构造函数类型**
> 使用`constructor`属性返回对象的`构造函数`
> ```javascript
> "John".constructor // 返回函数 String()  { [native code] }
> {name:'John', age:34}.constructor // 返回函数 Object()  { [native code] }
> false.constructor // 返回函数 Boolean() { [native code] }
> ```

- **类型转换**  
值得一提的是，`JavaScript`可以通过自身的`隐式类型转换`  
和用户调用函数而实现的`强制类型转换`  
这与绝大多数语言相同

**强制类型转换**
> 如，使用`string()`函数来**强制**将一个类型转换为**字符串类型**
> ```javascript
> String(x)         // 将变量 x 转换为字符串并返回
> // 或是这样
> x.toString()      // 将变量 x 转换为字符串并返回
> ```

**一元运算符**
> Operator + 可用于将变量转换为数字
> ```javascript
> var y = "5"; // y 是一个字符串
> var x = + y; // x 是一个数字
> // 如果y为一个不可转换位数字的变量，那么一元运算符也会将其转换为数字
> // 不过他的值为NaN (Not a Number)
> ```



## 函数
- 使用`function`关键字来创建一个函数
> ```javascript
> function func() { // 无参函数
>     // Code here
> }
> function func_arg(arg1, arg2) { // 带参函数
>     // Code here
> }
> function func_ret(num1, num2) { // 带参函数
>     return num1 * num2; // 使用return返回乘积，自动匹配类型
>     // return; // 如果直接使用return则代表退出函数
> }
> ```

- 语法操作
> 这里的语法操作指的是使用内置语法来进行例如`循环` `条件判断` `分支`等操作  
> 这里的语法与多数语言基本相同，故不作多阐述

## 对象
**在 JavaScript中，几乎所有的事物都是对象。**
- 定义一个对象
> ```javascript
> var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
> // 等价于
> var person = {
>     firstName:"John",
>     lastName:"Doe",
>     age:50,
>     eyeColor:"blue"
> };
> ```

- 访问对象属性
> 使用`.`操作符，或是`[]`操作符来访问对象属性

- 创建对象方法
> 创建一个对象的方法需要确保在一个对象内，而不是全局

> ```javascript
> let Person = {
>    firstName: "John",
>    lastName: "Simon",
>    GetFullName : function(){ // 创建一个名为GetFullName的函数方法
>       return this.firstName + " " + this.lastName; // 返回当前对象的全名
>    }
> }
> ```
- 对象方法
> 就像`C++`中调用成员函数，使用`ClassEntity.func();`来调用一个对象方法





## 输出
- 使用`console.log()`将数据写入到浏览器的控制台

- 使用`window.alert()`弹出警告框

- 使用`document.write();`函数来对内容输出
> 只能在HTML输出流中使用 `document.write`
> 如果在文档已加载后使用它（比如在函数中）,则会覆盖整个文档  

> 如:
> ```javascript
> <script>
> document.write("<h1>Hello JavaScript!</h1>");
> </script>
> ```
> 这将会以<strong>HTML</strong>中的`h1`标题来输出内容:Hello JavaScript!

- **模板字符串**
> ```javascript
> const name = 'Runoob';
> const age = 30;
> // 这将输出name变量与age变量
> const message = `My name is ${name} and I'm ${age} years old.`;
> ```



## 事件
下面是一些常见的HTML事件的列表:

| 事件          | 描述                    |
|-------------|-----------------------|
| onchange    | HTML元素改变              |
| onclick     | 用户点击HTML元素            |
| onmouseover | 鼠标指针移动到指定的元素上时发生      |
| onmouseout  | 用户从一个 HTML 元素上移开鼠标时发生 |
| onkeydown   | 用户按下键盘按键              |
| onload      | 浏览器已完成页面的加载           |

- 使用`alert()`函数来对事件作出反应
> 如:
> ```javascript
> <button type="button" onclick="alert('欢迎!')">点我!</button>
> ```
> 通过`<button>`来创建一个按钮，并使用`onclick`来监听事件发生。使用`alert()`
> 函数来对事件做出响应。

## 对HTML中的元素进行操作
- 通过`document.getElementById("Name")`来对HTML中的`id`为`Name`的元素进行查找
  ***这个方法是 HTML DOM 中定义的。***  
  ***DOM (Document Object Model)（文档对象模型）是用于访问 HTML 元素的正式 W3C 标准。***

- 通过`innerHTML`来对变量进行修改
> 如:
> ```javascript
> function EditCont()
> {
> Text=document.getElementById("demo");  // 找到元素
> Text.innerHTML="Hello JavaScript!";    // 改变内容
> }
> ```
> 这个例子会寻找到HTML中id为`demo`的元素，并且修改为`Hello JavaScript!`

- 使用`src`获取当前元素的完整路径
> `src`是一个属性，通常用于获取`<img>` `<script>` `<iframe>`等标签中的`<src>`的内容 (即完整路径)。

- `style.color` 用于设定当前中元素的`color`属性 
> 事实上`style`可以用于修改元素中的任何一种属性

- `isNaN()`用于判断一个值是否是非数字值。如果传入的值无法被转换为数字，则返回`true`否则返回`false`