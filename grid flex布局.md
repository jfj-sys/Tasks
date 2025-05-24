# Grid布局（二维布局）

## 容器属性 grid-template-*

想要多少行或者列，就填写相应的属性值的个数，不填写就自动分配

grid-template-columns:

grid-template-rows:

```htmml
div {
    display: grid;
    width: 600px;
    height: 600px;
    grid-template-columns: 100px 100px 100px; //每列的宽度
    grid-template-rows: 100px 100px 100px 100px; //每行的宽度

}
```

### fr(fraction)

为了方便表示比例关系

grid-template-rows: repeat(4,1fr);   表示宽度平均分成4份

grid-template-rows:1fr 2fr 3fr;  分别占盒子宽度的1：2：3

### minmax()

函数产生一个长度范围

grid-template-rows: 1fr minmax(150px,1fr);

### auto

表示由浏览器自己决定长度

grid-template-rows:100px auto 100px;

### 网格线

可以用方括号定义网格线名称，方便以后的引用

grid-template-rows:[c1] 100px [c2] 100px [c3] 100px [c4];

## 容器属性grid-row-gap / grid-column-gap

表示item相互之间的距离

grid-row-gap：20px;

grid-column-gap : 20px;

gap : 20px 20px;

## 容器属性 grid-template-areas

一个区域由单个或多个单元格组成，由自己决定

```html
grid-template-areas:'a b c'
					'd e f'
					'g h i'

grid-template-areas: 'a a a'
					 'b b b'
					 'c c c'
//区域不需要利用，使用(.)表示
grid-template-areas:'a . c'
					'd . f'
					'g . i'
```

## 容器属性grid-auto-flow

划分网格后，容器的子元素会按照顺序，自动放置在每一个网格，默认先行后列

```html
grid-auto-flow:row // 先行后列
grid-auto-flow:column // 先列后行
```

### grid-auto-flow：raw dense

## 容器属性justify-items / align-items

设置单元格内容的水平和垂直的对齐方式

justify-items：start | end | center | stretch

justify-items：start; // 内容在网格左侧对齐

place-items: center center // 水平和垂直方向上都居中

## 容器属性justify-content / align-content

设置整个内容区域的水平和垂直的对齐方式

justify-content / align-content : start | end | center | stretch | space-around | space-between | space-evenly;

## 容器属性 grid-auto-columns / grid-auto-rows

设置多出来的项目宽和高

## 项目属性 grid-column-start / grid-column-end / grid-row-start / grid-row-end

同来指定item的具体位置，根据在哪根网格线

grid-column: 2 / 4 // 本列从第2列开始到第四列介绍 

## 项目属性 grid-area

指定项目的位置

## 项目属性justify-self / align-self / place-self

justify-self : start | end | center | stretch





# flex布局

## 父项常见属性

### flex-direction  设置主轴方向

```
flex-direction:row
```



| 属性值         | 说明           |
| -------------- | -------------- |
| row            | 默认值从左到右 |
| row-reverse    | 从右到左       |
| column         | 从上到下       |
| column-reverse | 从下到上       |

### flex-wrap 设置子元素是否换行

| nowrap | 默认值，不换行 |
| ------ | -------------- |
| wrap   | 换行           |

### align-items 设置侧轴上的子元素排列方式（==单行==）

| 属性值     | 说明         |
| ---------- | ------------ |
| flex-start | 从上到下     |
| flex-end   | 从下到上     |
| center     | 挤在一起居中 |
| stretch    | 拉伸         |

### align-content  设置侧轴上的子元素排列方式（==多行==）

| 属性值        | 说明                                 |
| ------------- | ------------------------------------ |
| flex-start    | 默认值在侧轴的头部开始排列           |
| flex-end      | 在侧轴的尾部开始排列                 |
| center        | 在中间显示                           |
| space-around  | 子项在侧轴平分剩余空间               |
| space-between | 子项在侧轴先分布两头，在平分剩余空间 |
| stretch       | 设置子项元素高度平分父元素高度       |

### flex-flow  flex-direction和 flex-wrap的复合属性

## 子项常见属性

### flex属性 表示子项占多少份数

flex：1

### align-self 控制子项自己在侧轴上的排列方式





# 媒体查询

## rem

相对于html元素的字体的大小

em是相对于父元素字体大小

- 用@media查询，可以针对不同的媒体类型定义不同的样式
- @media可以针对不同的尺寸设置不同的样式

## 语法

```
@media mediatype and | not | only (media feature){

}
```

- 媒体类型mediatype 

  

## 媒体特性 (media feature)

| 值        | 解释说明                           |
| --------- | ---------------------------------- |
| width     | 定义出设备中页面可见区域的宽度     |
| min-width | 定义输出设备中页面最小可见区域宽度 |
| max-width | 定义输出设备中页面最大可见区域宽度 |

