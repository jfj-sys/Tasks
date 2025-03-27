# 1、CSS语法规则（写在<style></style>之中）

选择器+声明,写在<head></head>之间

```html
/* 给谁改标签{改什么样式}*/
<head>
    ...
    <style>
        p{
            color:red;
        }
    </style>
</head>
<body>
    <p>文本内容</p>
</body>
...
```

==注==：键值对后要加英文分号

# 2、CSS基础选择器

## 2.1标签选择器

## 2.2类选择器(==可以多次调用==)

```html
<style>
    .red {
        color: red;
    }
    .font {
        font-size: 35px;
    }
</style>
<body>
    <p class="red font">文本内容</p>
</body>
...
```

## 2.3id选择器（==只能调用一次==）

```html
<style>
    #red {
        color: red;
    }
</style>
<body>
    <p id="red">文本内容</p>
</body>
...
```

## 2.4通配符选择器

给所有标签修改样式，不需要调用

```html
<style>
    *red {
        color: red;
    }
</style>
<body>
    <p>文本内容</p>
</body>
...
```

# 3、CSS字体属性

## 3.1字体系列<font-family>

```html
<head>
    ...
    <style>
        p {
            font-family:"Microsoft YaHei",Arial;
        }
    </style>
</head>
<body>
    <p>文本内容</p>
</body>
...
```

## 3.2字体大小(font-size)

```html
body {
	font-size: 10px; 
}
```

px:像素  标题标签的内容要单独定义

## 3.3字体粗细(font-weight)

```html
<style>
    .bold {
        font-weight: 700;
    }
</style>
<body>
    <p class="bold">文本内容</p>
</body>
...
```

| 属性值  | 描述                      |
| ------- | ------------------------- |
| normal  | 默认值（不加粗）          |
| bold    | 定义粗体                  |
| 100-900 | 400等同于normal 700= bold |

## 3.4文字样式（font-style）

normal：标准体

italic:斜体

## 3.5字体复合属性

```html
<body>
    font: font-style font-weight font-size/line-height font-family;
</body>
...
```

==注：==不能更换顺序，各属性以空格隔开

==必须保留font-size font-family的属性==

# 4、CSS文本属性

## 4.1文本颜色

## 4.2对齐文本(text-align)

text-align: left/write/center

## 4.3装饰文本(text-decoration)

underline:下划线
line-through:删除线

## 4.4文本缩进（text-indent）

实现文本首行缩进

```html
div{
	text-indent: 10px;
}
p{
	text-indent: 2em
}
```

==注：==em是相对单位，为当前元素1个文字的大小

## 4.5行间距(line-height)

line-height: 26px;

# 5、CSS引入方式

## 5.1内部样式表

写到html页面内部，放到<head>标签中的<style>标签中

## 5.2行内样式表

在元素标签内部==style属性==中设定CSS样式

```html
<p style="color: pink;">文本内容</p>
```

## 5.3外部样式表

样式单独写到CSS文件中，之后把CSS文件引入到HTML文件页面中使用

引入外部样式表分两步：

1. 新建后缀名为.css的样式文件，把所有CSS代码都放入此文件中
2. 在HTML页面中，使用<link>标签引入这个文件

```css
<link rel="stylesheet" herf="css文件路径">
```

rel:定义当前文档与被链接文档之间的关系，指定为"stylesheet"，表样式表文件

定义外部样式表文件的RUL，可以是相对路径或绝对路径

# 6.Emmet语法

# 7.CSS的复合选择器

## 7.1后代选择器

```html
元素1 元素2 {样式声明}
```

==表示选择元素1中的所有元素2，给元素2中的内容修改样式，两个元素可以是任意选择器==

```html
<style>
    ol li {
        color: red;    
    }
    ol li a {
        color: pink; 
    }
    .nav li a{
        color: blue;
    }

</style>
<body>
    <ol>
        <li>文本1</li>
        <li><a herf="#">文本2</a></li>
    </ol>
     <ul>
   	   <li>文本3</li>
          <li><a herf="#">文本4</a></li>
    </ul>
    <ul class="nav">
         <li><a herf="#">文本5</a></li>
    </ul>
    
</body>
```
## 7.2子元素选择器

只能选择作为某元素的==最近的一级子元素==

```css
元素1 > 元素2（样式声明）
```

```html
<style>
    .nav>a{
        color: pink;
    }
</style>
...
<body>
    <div class="nav">
        <a herf="#">文本1</a>
        <p>
            <a herf="#">文本1</a>
        </p>
    </div>
    
</body>
```

## 7.3并集选择器

```html
元素1，元素2 {样式声明}
```



```html
<style>
    div,
    p {
        color: pink;
    }
</style>
...
<body>
    <div>
      文本1  
    </div>
    <p>
	文本2
    </p>
</body>
```

## 7.4伪类选择器

### 链接伪类选择器

```html
a:link  /*选择所有未被访问过的链接*/

a:visited   /*选择所有已被访问过的链接*/

a:hover /*选择鼠标指针位于其上的链接 */

a:active /*选择活动链接（鼠标按下未弹起的链接）*/
```

==注：按照 l v h a 的顺序写，a链接要单独指定样式==

### :focus伪类选择器

焦点就是光标，一般input类表单元素才能获取

```html
input:focus{
	background-color: yellow;
}
```

# 8、CSS的元素显示模式

## 8.1块元素

1. 独占一行
2. 高度、宽度、外边距及内边距都可以控制
3. 里面可以放任何元素
4. 默认宽度时父级的100%

==注：==文字类（<p> <h>）的元素不能使用块元素

## 8.2行内元素

1. 一行内可以放多个行内元素
2. 高、宽直接设置无效
3. 行内元素只能放文本或其他行内元素
4. 链接里不能再放链接
5. a里面可以放块级元素

## 8.3行内块元素

```html
<img/> <input/> <td> 同时具有块元素和行内元素的特点
```

## 8.4元素显示模式转换

行内元素转为块元素：display:block;

块元素转为行内元素:  display:inline;

转换为行内块元素：  display:inline-block;

# 9、CSS的背景

## 9.1背景颜色

```html
background-color: red;
```

## 9.2背景图片（background-image）

```html
background-image: url(图片地址);
```

## 9.3背景平铺（background-repeat）

```html
background-repeat: repeat;
background-repeat: no-repeat;
background-repeat: repeat-x;
background-repeat: repeat-y;
```

## 9.4背景图片位置(background-position)

```html
background-position: x y;
```

x y可以是方位名词或精确单位

方位名词：两个值顺序可以调换，效果相同

精确单位、混合单位：两个值不能调换，效果不同

## 9.5背景图像固定(background-attachment)

```html
background-attachment : scroll; 背景图像随内容滚动
background-attachment : fixed;  背景图像固定
```

## 9.6背景复合写法

```html
background: 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置;
background: pink url() repeat fixed top;
```

## 9.7背景色半透明

```html
background: rgba(0,0,0,.4);
```

最后一个参数是alpha透明度，取值在0~1之间

可以将0.4简写为 .4

# 10、CSS三大特性

## 10.1层叠性

```html
<head>
    <style>
    div{
        color: red;
    }
    div{
        color: pink;
    }
    </style>
</head>
<body>
<div>文本内容</div>
</body>
```

相同选择器给设置相同的样式，样式冲突，哪个样式离结构进，就执行哪个样式

## 10.2继承性

子标签继承父标签的某些样式（text- ,font-,line-这些元素开头的可以继承，以及color属性）

### 行高的继承

```html
body{
	font: 12px/1.5 Microsoft YaHei;
}
```

1.5表示子元素的行高为当前设置子元素行高的1.5倍

## 10.3优先级

| 选择器               | 选择器权重 |
| -------------------- | ---------- |
| 继承或*              | 0，0，0，0 |
| 元素选择器           | 0，0，0，1 |
| 类选择器，伪类选择器 | 0，0，1，0 |
| ID选择器             | 0，1，0，0 |
| 行内样式style=“”     | 1，0，0，0 |
| !important           | 无穷大     |

# 11、盒子模型

## 11.1边框（border）

```html
border-width: 5px;
border: 5px solid pink; /* 复合写法*/
border-top: pink; /* 单独设定上边框的样式*/
```

| 属性         | 作用                                         |
| ------------ | -------------------------------------------- |
| border-width | 定义边框粗细，单位为px                       |
| border-style | 边框样式(solid:实线 dashed:虚线 dotted:点线) |
| border-color | 边框颜色                                     |

## 11.2表格细线边框

```html
border-collapse: collapse; /*把相邻边框合并到一起*/
```

## 11.3内边距(padding)

padding-top  padding-bottom padding-left padding-right

```
padding-top: 10px ;
```

|                              |                                                              |
| ---------------------------- | ------------------------------------------------------------ |
| padding: 5px;                | 上下左右都有5像素内边距                                      |
| padding: 5px 10px;           | 上下内边距为5像素，左右内边距为10像素                        |
| padding: 5px 10px 20px;      | 上内边距为5像素，左右内边距为5像素，下内边距为20像素         |
| padding: 5px 10px 20px 30px; | 上内边距为5像素，右内边距为10像素，下内边距为20像素，左内边距为30像素 |



## 11.4外边距（margin）

margin-top  margin-bottom margin-left margin-right

```html
margin-top: 20px;
```

### 实现块级盒子水平居中

1. 盒子必须指定宽度
2. 盒子左右的外边距都设置为auto

```html
.header{ 
	width: 960px;
	margin: 0 auto;
}
```

### 行内元素和行内块元素水平居中

给父元素增加 text-align: center;

## 11.5嵌套块元素塌陷

对于两个嵌套关系（父子关系）的块元素，父元素有上边距同时子元素也有上外边距，此时父元素会坍塌较大的外边距值

==解决方案：==

1. 可以为父元素定义上边框
2. 可以为父元素定义上内边框
3. 可以为父元素添加overflow:  hidden;

```html
...
<style>
    ...
    .father {
        border: 1px solid transparent;
        padding: 1px;
        overflow: hidden;
    }
</style>
```

## 11.6清除内外边距

```html
...
<style>
    ...
    *{
        margin: 0;
        padding: 0;
    }
```

# 12、浮动(float)

让多个块级元素在一行内排列显示

==多个块级元素纵向排列找标准流，多个块级元素横向排列找浮动==

```
选择器 { float: 属性值（left,right,none）; }
```

## 12.1浮动的特性

1. 脱离标准流的控制，移动到指定位置
2. 浮动的的盒子==不再保留原先的位置，可由其他标准流盒子占有==
3. 浮动元素具有行内块元素的性质

## 12.2浮动布局注意点

### 浮动元素与标准流父级搭配使用

==先用标准流的父元素排列上下位置，之后内部子元素采取浮动排列位置==

### 一浮全浮

一个盒子里有多个盒子，如果一个盒子浮动，其他盒子也已应该浮动

浮动的盒子只会影响（压住）浮动盒子后面的标准流，不会影响前面的标准流

## 12.3清除浮动

```
选择器{clear: 属性；}
```

| 属性值 | 描述               |
| ------ | ------------------ |
| left   | 清除左侧浮动的影响 |
| right  | 清除右侧浮动的影响 |
| both   | 清除左右两侧       |

### 清除浮动的方法

1. 额外标签法

```html
<head>
    <style>
        ...
        .clear{
            clear: both;
        }
    </style>
</head>
<body>
    <div class="box">
        <div>文本1</div>
        <div>文本1</div>
        <div class="clear"></div> /*新增的元素必须是块元素*/
    </div>
</body>
```

2. 父级添加overflow

```html
<head>
    <style>
        .box{
            overflow:  hidden;
            ...
        }
        .clear{
            clear: both;
        }
    </style>
</head>
<body>
    <div class="box">
        <div>文本1</div>
        <div>文本1</div>
        <div class="clear"></div> /*新增的元素必须是块元素*/
    </div>
</body>
```

3. :after伪元素法

```html
<style>
    .clearfix:after{
        content: "";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
    } 
    .clearfix {
        zoom: 1;
    }
   
</style>
```

4. 双伪元素清除浮动

```html
<style>
    .clearfix:before,.clearfix:after{
        content: "";
        display:tablel;
    } 
    .clearfix:after{
        clear:both;
    }
    .clearfix {
        zoom: 1;
    }
   
</style>
```

# 13、定位position（定位模式+边偏移）

让盒子自由在盒子内移动位置或者固定屏幕中的某个位置，并且可以压住其他盒子

## 13.1定位模式

position属性的四个值：

| 值       | 语义     |
| -------- | -------- |
| static   | 静态定位 |
| relative | 相对定位 |
| absolute | 绝对定位 |
| fixed    | 固定定位 |

## 13.2边偏移

| 边偏移属性 | 示例         | 描述                                           |
| ---------- | ------------ | ---------------------------------------------- |
| top        | top: 80px    | 顶端偏移量，定义元素相对于其父元素上边线的问题 |
| bottom     | bottom: 80px | 底部偏移量，定义元素相对于其父元素下边线的问题 |
| left       | left: 80px   | 左侧偏移量，定义元素相对于其父元素左边线的问题 |
| right      | right: 80px  | 右侧偏移量，定义元素相对于其父元素右边线的问题 |

## 13.3静态定位

按照标准流特性摆放位置

```
选择器 {position: static; }
```

## 13.4相对定位

```
选择器 {position: relation;}
```

 特点：

1. 相对自己原来的位置来移动
2. ==原来在标准流的位置继续占有==，后面的盒子仍然以标准流的方式对待它

## 13.5绝对定位

```
选择器 {position: absolute; }
```

特点：

1. 如果没有父级或父级没有定位，以浏览器为准定位
2. 父级有定位，则以==最近一级带有定位的==祖先元素为参考点移动位置
3. 绝对定位==不再占有原先的位置==

## 13.6固定定位

固定定位是元素固定于浏览器可视区的位置，==浏览器滚动时元素位置不会改变==

```
选择器 { position: fixed; }
```

特点：

1. 以浏览器的可视窗口为参照点移动元素
2. 固定定位==不占有原先的位置==

固定定位技巧——固定在版心右侧位置：

1. 让固定定位的盒子left 50% 走到浏览器可视区（版心）的一半位置
2. 让固定定位的margin-left：版心宽度的一半距离多走版心宽度的一半位置

## 13.7粘性定位(sticky)

```
{position: sticky;top: 10px; }
```

特点：

1. 以浏览器的可视窗口为参照点移动元素
2. ==占有原先的位置==
3. 必循添加top left right bottom其中一个才有效

## 13.8定位的叠放次序

```
选择器{ z-index: 1;}
```

- 数值可以是正整数、负整数或0，数值越大，盒子越靠上
- 属性值相同，后来者居上
- 数字后不能加单位
- 只有定位的盒子才有z-index的属性














