# CSS

------

1.CSS是什么

2.CSS怎么用（快速入门）

3.***CSS选择器（重点+难点）***

4.美化网页（文字、阴影、超链接、列表、渐变）

5.盒子模型

6.浮动****

7.定位

8.网页动画（特效效果）



## 1.CSS是什么

CSS的优势：

1.内容和表现分离

2．网页结构变现统一，可以实现复用

3.样式十分的丰富

4.建议使用独立于html的css文件

5.利用SEO，容易被搜索引擎收录



## CSS的3种导入方式

就近原则

行内样式、内部样式、外部样式



扩展；外部样式的两种写法

- 链接式：

  

- 导入式：





选择器：

------

基本选择器

1、标签选择器

2、类选择器

3、id选择器

------

层次选择器

1.后代选择器：在某个元素的后面   祖爷爷、爷爷、爸爸

```html
body p{
	background: blueviolet;
}
```



2.子选择器：一代（只有一个的意思）、儿子

```html
body>p{
	background: chartreuse;
}
```



3.相邻兄弟选择器：同辈

```html
.active + p {
    background: brown;
}
```

4.通用选择器：当前选中元素向下的所有兄弟元素

```
/*通用选选择器*/
.active~p{
    background: darkblue;
}
```



------

结构伪类选择器：













------

属性选择器：





浮动：

父级边框的塌陷问题：

1.增加父级高度 

```css
#father{
    border:1px #00 solid;
    height:800px;
}
```



2.增加一个空的div标签，清除浮动

```css
<div class = "clear"></div>
.clear{
 	clear:both;
    margin:0;
    padding:0;
}
```



3.overflow

在父级元素中，增加一个overflow：hidden;



4.在父类中添加一个伪类

```css
#father：after{
    content: '';
    dispaly:block;
    clear:both;
}
```



小结：

1.浮动元素后面增加空div：简单，代码中尽量避免空div

2.设置父元素的高度：简单，元素假设有了固定的高度，就会被限制

3.overflow：简单 下来的一些场景使用

4.在父类中添加一个伪类：after （推荐），写法稍微复杂没有副作用，推荐使用！



## 5.对比：

display：反向不可控制

float：浮动起来会脱离标准文档流。所以要解决父级边框塌陷的问题



## 6.定位

6.1 相对定位

```css
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        body{
            padding: 20px;
        }
        div{
            margin: 10px;
            padding: 5px;
            font-size: 12px;
            line-height: 25px;
        }
        #father{
            border: 1px solid #666;
        }
        #first{
            background-color: #C850C0;
            border: 1px dashed #dac90c;
            position: relative;
            top: -20px;
            left: 20px;
        }
        #second{
            background-color:sandybrown ;
            border: 1px dashed rgba(12, 208, 197, 1);
        }
        #thrid{
            background-color: aqua;
            border: 1px dashed #6ac61c;
        }
    </style>
</head>
<body>
<div id="father">
    <div id="first">第一个盒子</div>
    <div id="second">第二个盒子</div>
    <div id="thrid">第三个盒子</div>
</div>

</body>
</html>
```

***相对定位是相对自己的原始位置***







6.2 绝对定位

定位：基于xx定位，上右下做

1.没有父级元素定位的前提下，相对于浏览器定位

2.假设父级元素存在定位，我们通常会相对于父级进行偏移。







6.3 z-index























































