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













