

# 1、JavaScript书写位置

1. 内部

   ```html
   <body>
       ......
       <script>
       </script>
   </body>
   ```

2. 外部

   在内部引入

   ```html
   <body>
       <script scr="js路径 "></script>
   </body>
   ```

# 2、JavaScript注释

1. 单行注释

   符号：//

   快捷键：ctrl + /

2. 块注释

   符号：/* */

   快捷键：shift+alt+a

# 3、输入输出语法

## 3.1输出

```html
document.write('要输出的内容，可以写标签') // 向body内输出内容
```

```html
alert('要出的内容') // 页面弹出警告对话框
console.log('') // 在在控制台打印
```

## 3.2输入

```html
prompt('请输入您的你姓名：')
```

# 4、变量

## 4.1声明变量和赋值

```html
let 变量名
let age = 18
let age = 18,name = 'lij'  //同时声明多个变量
console.log(age,name)
```
## 4.2常量

概念：使用 const 声明的变量称为“常量”。

使用场景：当某个变量永远不会改变的时候，就可以使用 const 来声明，而不是let。

命名规范：和变量一致
# 5、数组

```html
let names = ['lisa','jack','mark']
let arr = [1,2,'pink',true]
let nums = [1,2,34,56]
console.log(names[2])
console.log(names.length) // 获取数组长度
```

## 5.1数组中增加新元素

```
arr.push(元素1，元素2，元素3…)  // 添加元素到数组的末尾，并且返回数组的新长度
arr.unshift(新增内容) // 将一个或多个元素添加到数组的开头，并返回该数组的新长度 
```

## 5.2删除数组中的数据

```
arr.pop() // 删除数组中最后一个元素
arr.shift() // 删除数组中第一个元素
arr.splice(起始位置，删除几个元素) // 删除指定元素
```



# 6、常量

==不允许更改值，声明时必须初始化==

```html
const G = 9.8
```

# 7、数据类型

## 7.1基本数据类型

```html
数字型
let num = 10
let num2 = 11.11  
console.log(4 % 3) // 求模

字符串(单引号、双引号、反引号)
let str1 = 'pink'
console.log('我今年' + 19)  // +拼接

let age = 19
document.write(`我今年${age}岁了`)  // 模板字符串，用反引号

布尔值（boolean）(true/false)
let isCool = true
console.log(isCool)
console.log(3>4) // 返回false

未定义类型（undefined）
let num // 声明一个变量，没有赋值

空类型（null）
let obj = nulla

let str = 'j'
console.log(typeof str) // 检测数据类型
```

==注：==undefined表示没有赋值。null表示赋值了，但内容为空

### 转换为布尔型

1. 有字符串的加法 “ ” +1 ，结果为1
2. 减法 - 只能用于数字，它会使空字符串“ ”转换为0
3. null经过数字转换之后会变为0
4. undefined经过数字转换之后会变为NaN

# 8、运算符

==：左右两边值是否相等

===：左右两边是否类型和值都相等

！=：不等值

！==：类型和值不全等



| 优先级 | 运算符     | 顺序         |
| ------ | ---------- | ------------ |
| 1      | 小括号     | ()           |
| 2      | 一元运算符 | ++ -- ！     |
| 3      | 算术运算符 | 先* / 后 + - |
| 4      | 关系运算符 | > >= < <=    |
| 5      | 相等运算符 |              |
| 6      | 逻辑运算符 | 先&& 后\|\|  |
| 7      | 赋值运算符 | =            |
| 8      | 逗号运算符 | ，           |

## 三元运算符

```
条件？满足条件执行的代码 : 不满足条件执行的代码
```

## 逻辑中断

短路：只存在于&& 和|| 中，当满足一定条件会让右边代码不执行

| 符号 | 短路条件          |
| ---- | ----------------- |
| &&   | 左边为false就短路 |
| \|\| | 左边为true就短路  |



# 9、分支语句

## switch语句

```html
switch(数据){
	case 值1:
        代码1
        break
    case 值2:
        代码2
        break
	defalt:
    case 值3:
        代码3
}
```

# 10、函数

```
function 函数名(){
	函数体
}

函数名() //调用
```

## 匿名函数（无法直接使用）

**函数表达式**

```html
let fn = function(x,y){
	console.log(x + y)
}
fn(1,3) //不能在匿名函数声明前使用
```

**立即执行函数**(无需调用，立即执行，==末尾必须加分号==)

```html
(function () { console.log(11) })();
(function () { console.log(11) }());
```

# 11、对象（一种数据类型）

```html
let 对象名 = {
	属性名：属性值,
	方法名：函数
}  // 声明对象

对象.属性 = 新值 // 修改、新增属性

对象名['属性名'] // 查属性：用于属性名中带有字符串
对象名.属性名 // 查属性

```

方法

```
方法名：function(){

}
```

## 遍历对象

遍历数组

```html
...
<script>
    let arr = ['pink','red','white']
    for (let k in arr){
        console.log(k) // 数组的下标 索引号 但是k是字符串
    }
</script>
...
```

**遍历对象**

```html
...
<script>
	let obj = {
        uname: 'djx',
        age: 19,
        gender:'男'
    }
    // 遍历对象
    for(let k in obj){
        console.log(k) // 属性名 'uname' 'age'
        console.log(obj.k) // 等同于 console.log(obj.'uname') 是错误的
        console.log(obj[k])
    }
</script>
...
```

## 内置对象

**Math**

Math.round()：四舍五入

## 随机数函数

```html
Math.random()  // 随机数函数，返回一个0-1之间，并且包括0不包括1的随机小数
Math.floor(Math.random() * (10 + 1))  // 生成0 - 10的随机整数
Math.floor(Math.random() * (M-N + 1)) +N // 生成N-M之间的随机数
```



# 12、PIs

## 12.1获取DOM对象

1. 选择匹配的第一个元素

```
document.querySelector('css选择器') // 返回值为选择器匹配的第一个元素，一个HTMLElement对象
```

```html
...
<body>
    <div class='box'>123</div>
    <div class='box'>abc</div>
    <ul>
        <li>测试1</li>
        <li>测试2</li>
        <li>测试3</li>
    </ul>
    <script>
        const box = document.querySelector('div')
        const box = document.querySelector('.box')  // 获取第一个盒子，即123
        const li = document.querySelector('ul li:first-child') // 获取ul中的第一个li
    </script>
</body>
...
```

2. 选择匹配的多个元素

```
document.querySelectorAll('css选择器')  // 返回值为选择器匹配的NodeList 得到伪数组
```

```html
...
<body>
    <ul>
        <li>测试1</li>
        <li>测试2</li>
        <li>测试3</li>
    </ul>
    <script>
        const lis = document.querySelectorAll('ul li') 
        // 遍历
        for(let i = 0; i < lis.length; i++){
            console.log(lis[i])
        }
    </script>
</body>
...
```

==伪数组==：

- 有长度有索引的数组
- 没有pop() push()等数组方法，想要得到里面的每一个对象，需要便利获得

## 12.2操作元素内容

### 元素.innerText属性

==只识别文本，不能解析标签==

```html
...
<body>
    <div class='box'>文字内容</div>
    <script>
        const obj = {
            name: 'ljh'
        }
        console.log(obj.name)
        const box = document.querySelector('.box')  // 获取元素
        console.log(box.innerText)  // 获取文字内容
        box.innerText = '<strong>新文字内容</strong>'  //  修改文字内容,不解析标签
    </script>
    
</body>
...
```

### 元素.innerHTML属性(解析标签)

将文本内容添加/更新到任意标签位置

==能识别文本，会解析标签==，多标签建议使用模板字符

```html
...
<body>
    <div class='box'>文字内容</div>
    <script>
        const obj = {
            name: 'ljh'
        }
       const box = document.querySelector('.box')  // 获取元素
       console.log(box.innerHTML)
       box.innerHTML = '<strong>更换内容</strong>'
    </script>
    
</body>
...
```

## 12.3操作元素属性

### 操作元素常用属性

```
对象.属性 = 值  // 通过js修改标签元素属性，如通过scr修改图片
```

```html
...
<body>
    <img scr='image/pic1.jpg' alt=''>
    <script>
        const img = document.querySelector('img')
        img.scr = 'image/pic2.jpg'
    </script>
</body>
...
```

### 操作元素样式属性

1. 通过style属性操作css

```
对象.style.样式属性 = 值
box.style.width = '200px'
box.style.marginTop = '15px'
box.style.backgroundColor = 'pink'  // 用小驼峰命名
```

### 通过类名修改样式

**1.操作类名（className)操作CSS**

```
元素.className = 'active'
```

```html
...
<style>
    .box {
            width: 1200px;
            height: 460px;
            margin: 100px auto;
            background-color: blanchedalmond
        }
</style>
...
<body>
    <div></div>
    <script>
        const div = document.querySelector('div')
        div.className = 'box' // 添加类名
    </script>
</body>
```

==注：==会覆盖原先的类，如果要添加类要保留之前的类名

**2.通过classList修改样式**

```
// 追加一个类,类名不加.
元素.classList.add('类名')
// 删除一个类
元素.classList.remove('类名')
//切换一个类
元素.classList.toggle('类名')
```

### 操作表单元素属性

```html
<body>
	<input type='text' value='电脑'>
    <script>
    	const uname = document.querySelector('input')
        console.log(uname.value)  // 获取值 获取表单里面的值用的 表单.value
        uname.type = 'password'
    </script>
</body>
```

- 表单属性中添加就有效果，移除就没有效果，一律使用布尔值表示，如果为true代表添加了该属性，如果是false代表移除了该属性
- 比如：disabled checked selscted

```html
<body>
	<input type='checkbox' name='' id=''>
    <script>
    	const ipt = document.querySelector('input')
        console.log(ipt.checked)  //false
        ipt.checked = true
    </script>
</body>
```

### 

