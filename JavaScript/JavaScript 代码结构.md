## 2.1 JavaScript 代码结构

`JavaScript` 程序可以在`<script>`标签的帮助下插入到`HTML`文档的任何地方。当浏览器遇到`<script>`标签，代码会自动运行。

```html
<!DOCTYPE HTML> 
<html> 
    <body>  
        <p>script 标签之前...</p> 
        <script>   alert('Hello, world!')  </script>  // JavaScript 代码块
        <p>...script 标签之后</p> 
    </body>
</html>
```

## 2.2 外部脚本

如果有大量的`JavaScript`脚本代码，我们可以将它单独放到一个文件，通过`src`特性添加到`HTML`文件。此处，`/path/script.js`是脚本文件从网站根目录开始的**绝对路径**。

```html
<script src="/path/script.js"></script>
```

我们还可以通过一个完整的`URL`地址调用脚本文件

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js"></script>
```

如果要使用多个脚本，那就添加多个`<script>`标签

```html
<script src="/path/script1.js"></script>
<script src="/path/script2.js"></script>
<script src="/path/script3.js"></script>
...
```

一般来说，只有比较简单的脚本才会嵌入在`HTML`文件中，更复杂的脚本文件通过`src`特性放到单独的文件中去调用。这样做的好处是，使用独立文件的好处是浏览器会下载它，然后将它保存到浏览器的**缓存**中；其他页面想要相同的脚本就会从缓存中获取，而不是下载它。所以文件实际上只会下载一次，起到节省流量和页面加载速度更快的作用。

## 2.3 注意事项

一个单独的`<script>`标签不能同时拥有`src`特性和内部包裹的代码：

```html
<script src="file.js">
  alert(1) // 此内容会被忽略，因为设定了 src
</script>
```

为了使上面的例子工作，我们需要分成两个标签：

```html
<script src="/path/file.js"></script>
<script>
  alert(1)
</script>
```

## 语句

`alert()`语句提供显示消息的功能

```html
<script> 
    alert('Hello')
	alert('World')	 //分行写增加可读性
</script>
```

~~写`JavaScript`程序提倡使用**分号**，那是为了迎合你之前的编程习惯~~，而一般习惯的做法是不必加分号，程序只需分行写即可。

## 2.4 严格模式

严格模式的`ES5`提出的规范，它的好处是：

>- 消除代码运行的一些不安全之处，保证代码运行的安全；
>- 提高编译器效率，增加运行速度；
>- 为未来新版本的Javascript做好铺垫。

为了避免报一些列不明原因的错误，日常开发一般是禁用严格模式，在此不做过多赘述。严格模式可以通过`use strict;`的表达式声明。

## 2.5 变量

使用`let`关键字创建变量

```javascript
let message; 
let message = '0xFFFF', number = 123; //声明多个变量
```

**注：同一个变量进行重复声明会触发`error`，所以一个变量应该只被声明一次。**

- 变量名可以包含字母、数字、＄、_
- 首字符必须非数字
- 区分大小写
- 保留字（let、class、return、function）不能用作变量名
- 严格模式下，未经变量声明就赋值会报错（为了兼容旧脚本）；如果不用严格模式的话，未经变量声明可以赋值。

```javascript
let $ = 1
let _ = 0
let 1userName = 'rookie' // 错误声明
```

## 2.6 常量

使用`const`声明变量：

```javascript
const loveNumber = 1119 //常量不能被修改，否则报错
```

- 常常采用大写声明常数（方便记忆），增加可读性
- 使用大写和下划线`_`作为常量名

```javascript
const COLOR_RED = "#F00"
const COLOR_BLUE = "#00F"
const COLOR_ORANGE = "#FF7F00" //颜色对应的十六进制值很难记忆，这个值是不会变化的，于是就用大写字母来表示
```

注：建议采用**驼峰命名法**来声明变量，**新建**变量比**重用**变量更好，至少在调试程序方面赢得了宝贵时间！

## 2.7 数据类型

JavaScript 中有 8 种基本的数据类型（7 种原始类型和 1 种引用类型）。

- Number 类型：代表整数和浮点数；特殊数值，如`Infinity`、`-`和`NaN`。

   `NaN`代表一个计算错误，不正确的或者一个未定义的数学操作得到的结果，任何对`NaN`的进一步操作都会返回`NaN`，数学运算是安全的，最坏的情况下我们只会得到一个`NaN`，而不会导致脚本停止！

- BigInt 类型：用于表示**任意长度**的**整数**。

- String 类型：可以用 " "、' '、`` 来表示字符串，而反引号表示**功能扩展**，在反引号中的字符串中使用 ${...} ，**内部的表达式被计算**，计算结果会成为字符串的一部分。

- Boolean 类型：`true`和`false`

- object 类型：用于保存**数据集合**和**更复杂的实体**，是一种特殊类型，上述所有类型都被称为**原始类型**。 

- symbol 类型：用于创建对象的唯一标识符。

## 2.8 特殊值

- null 值：不属于上述任何一种类型，仅仅代表 “无” 、“空”、“值未知” 的变量。

- undefined 值：含义是未被赋值。

  ```javascript
  let cardID 
  alert (cardID) // 弹出 undefined 值，变量未定义#
  ```

### 2.8.1 typeof 运算符

用于返回参数的类型，在处理不同类型的值的时候，例如进行数据类型检验时，经常用到它！

```javascript
typeof 参数 
typeof (参数) //返回数据类型
...
typeof (Math) // 返回 object 
typeof (null) // 返回 object ，旧脚本的错误，实际上 null 并不是 object 类型，而是一个特殊值
typeof (alert) // 返回 function ，因为 alert 是一个函数
```

### 2.8.2 alert 交互函数

由于我在使用 Chrome 浏览器作为 JavaScript 的开发环境，下面展示的是一个**模态窗**，意味着用户不能与页面的其他部分进行交互，直到它们处理完模态窗口，即**用户按下确定的按钮**。

![alert](../img/alert20201018215510.png)

## 2.8.3 prompt  交互函数

`prompt`函数接收两个参数，弹出模态窗，`title`是显示给用户的文本，`default`是指定`input`框的初始值（可选）。

```javascript
// result = prompt(title, [default]) 
let age = prompt('How old are you?', 100) //显示文本 How old are you? ；输入框键入 100
```

![prompt](../img/prompt20201018221729.png)

## 2.8.4 confirm

`confirm` 函数显示一个带有 `question` 以及确定和取消两个按钮的模态窗口。点击确定返回 `true`，点击取消返回 `false`。

```javascript
// result = confirm(question)
let isBoss = confirm("Are you the boss?") 
alert isBoss //确定返回 true ，点击取消返回 false
```

![confirm](../img/confirm20201018222207.png)

上述三个方法都有共同的限制：

- 模态窗口的确切位置由浏览器决定。通常在页面中心。
- 窗口的确切外观也取决于浏览器。我们不能修改它。









