# css（cascading style sheet）层叠样式表

就是控制html中的标签样式  
CSS代码写法：选择器:{css代码属性:属性值}  

## CSS代码引入

```html
方式一  
在head标签里面写  
<style>        
p{background-color:green;height:100px;width:100px}    
</style>    
方式二  
直接在标签里面写style  
<span  style="background-color:green;height:100px;width:100px">
不独占一行，没有任何效果
</span>  
方式三  
在head标签里面通过link标签引入  
<link rel="stylesheet" href="text.css">  
```

## link 引入文件

```html
<link rel="stylesheet" href="text.css">    
rel是文件样式，href是文件名  
```

## css选择器

## 基本选择器

```html
元素选择器：<style>div{color:red}</style>
把所有div标签里面的内容全部变成红色
id选择器：<style>#大壮{color:red}</style>
类选择器：.类名<style>.c1{color: red}</style>
<div id="xuefei" class="c1">雪菲</div>
<div id="阿牛" class="c1">阿牛</div>

div.c1就表示只有c1类里面额div标签才会被改变颜色
组合选择器
```

## 组合选择器

```html
<div>
    <a href="">百度</a>
<div>
    <a href="">京东</a>
</div>
</div>
<style>div a{color: red }</style> 
就表示把div标签里面的所有a标签标红

# 儿子选择器
<div>
    <a href="">百度</a>
<p>
    <a href="">京东</a>
</p>
</div>
<style>div>a{color: red }</style>
表示把所有父级标签是div的a标签标红
```

## 毗邻选择器

```html
<p>坏阿牛</p>
<div>
        <a href="">百度</a>
    <p>
        <a href="">京东</a>
    </p>
    </div>
<p>小阿牛</p>
<style>div+p{color: red}</style>
就是将div下面的第一个p标签标红

<style>div~p{color:red}</style>
表示将div下面的所有p标签标红
```

## 属性选择器

```html
属性选择器一般用在input标签里面
<div title="111">div1</div>
<div>div2</div>
<style>div[title]{color: red}</style>
表示具有title属性的div标签标红
属性选择器还可以搭配正则表达式来使用
```

# 分组选择器

```html
<div>div2</div>
<div>div3</div>
<p>p1</p>
<style>div,p{color: red}</style>
将所有的div标签和p标签都标红
```

## 伪类选择器

+ a标签不会继承父级标签的颜色，想要改变a标签的颜色只有先选中a标签  

```html
主要是使用于a标签
a标签自带的效果时在网址未被访问之前字体颜色是蓝色，在网址被
访问过后字体颜色是紫色
<style>a:link{color: green}</style> 设置网址没被访问之前zhuan字的颜色
<style>a:visited{color: yellow}</style>设置网址被访问以后转载字的颜色
<style>a:hover{color: blue}</style> 设置鼠标放到转载字上面时字体的颜色 应用的比较多，可以使用在其他标签上面
<style>a:active{color: red}</style> 设置鼠标点下去还没抬起来时鼠标的颜色
<a href="http://www.xiaohuar.com">校花</a>
<style>input:focus{color: pink}</style>
当输入框获得光标以后，输入框将会变成粉色
```

## 伪元素选择器

```html
<p>我是一个p标签</p>
<style>p:first-letter{content:"憨牛";color:pink;font-size:20px}
p:before{content:"hhh";color:yellow}
P:after{content:"hhh";color:pink}</style>
first-letter表示对p标签里面第一个字进行操作
before可以在p标签的前面插入内容并且可以对插入的内容进行操作
after标签可以对p标签后面插入内容并且可以对插入的内容进行操作
```

## 选择器的优先级

优先级：谁的优先级高就显示谁的颜色，在同样优先级的情况下，谁在后面就显示谁的颜色  

继承的优先级是最低的  

元素的优先级大于继承  

类的优先级大于元素  

id的优先级大于类  

内联样式选择器大于id选择器（就是将标签颜色直接在标签内部设置）  

！import大于一切  
！import就是将一个标签设置成为最重要标签，但是一般不用。  

## 设置高度宽度

只有块级标签才能设置高度宽度，内联标签是不可以设置高度宽度的，内联标签的高度宽度是由内联标签里面的内容来决定的。  

```css
<style>div{height: 100px ;width:100px ;
background-color:pink}</style>

<style>span{height:100px;width:100px;
background-color:purple}</style>
```

## 字体属性

### 字体设置


    <style>div{font-family:"宋体","楷体","微软雅黑"}</style>  
​    如果浏览器支持宋体就会选择宋体来渲染，不支持宋体就会选择楷体来渲染  

### 字体大小  
浏览器默认字体是16号，超过十六就变大了，小于十六就变小了  

```css
<style>div{font-size:20px}</style>
```

​      

### 设置字体粗细

```css
<style>div{font-weight:bold}</style>
```

normal是正常

bold是加粗     

bolder是更粗  

lighter是更细  

100~900 400是normal 700是bold  

inherit 继承父元素字体的粗细  

### 字体的颜色设置

rgb:#十六进制  

rgb:(, , )  

rgba:(, , ,透明度)  

color:颜色  

### 文字属性

文字对齐  
文字默认左上角对齐  

```html
<style>div{text-align:center}</style>
center文字居中
right右对齐
left左对齐 默认值
justify 两端对齐
line-height:40px垂直居中
```

文字装饰  
text-decoration    

```html
text-decoration:none
<style>div a{text-decoration:none}</style>
将a标签的下划线去掉
```

none标准文本   
underline下划线  

overline 文本上的线  

line-through 穿过文本的线，类似于删除线  

inherit 继承父标签  

首行缩进  

text-indent:32px 首行文字缩进两个字符  

## 背景属性

设置背景图片  

    <style>div{background-image:url("path");background-repeat:
    background-position:center center;no-repeat;width:600px;height:600px}</style>
    no-repeat不平铺
    repeat-X将图片横向平铺
    repeat-Y就是纵向平铺
    什么都不写就是默认将整个背景板铺满
    
    九宫格布局
        left top左上角
        left center左边的中间
        left bottom 左边的下面
        center
        right
        100px 50px就是距离左边100px，距离上面50px
    这个支持简写
    background-image:url("path") no-repeat left center
    background-attachment:fixed;把一张图片固定在一个地方，怎么滑动都不会改变位置    

## 边框

    <style>div{
            border-style: solid;
            border-color: orange;
            border-width: 2px;
            width: 200px;
            height: 200px;
        }</style>
    
    border-style设置边框线 solid设置边框线为实线
    dashed设置边框线为虚线（连成虚线的图形为方形）
    dotted设置边框虚线（连成虚线的图形为圆形）
    border-left-style设置边框线的左边
    border-right-style设置边框线的右边
    border-top-style 设置上边框
    border-bottom-style 设置下边框
    border-left-width 设置左边框边框线的宽度
    
    border-color设置边框颜色
    
    border-width设置边框线的宽度
    width设置边框的宽度
    height设置边框的高度
    
    简写：border:10px solid red
    单独设置边框简写：border-left:10px dashed red
    border-radius:50%;圆角设置 50%就可以使方形变成圆形。
    
    display:inline把一个块级标签改成内联标签
    inline-block将标签设置成为内联标签，但是可以设置标签的宽度高度
    none标签将会被隐藏起来，并且不占用 之前的空间
    block就是将内联标签变成块级标签
    visibility:hidden;将标签隐藏，但是依然占着以前的位置
    
    padding表示内容和边框之间的距离也有上下左右四个方向
    padding-left:10px;
    padding-bottom:5px;
    padding-right:10px;
    padding-top:5px
    简写： padding: 10px 20px;10px表示上下，20px表示左右
    padding:10px 15px 20px 25px;按照上右下左顺时针顺序

注意：如果设置0的话就不要带上px单位  

    <div>
    <span class="c1">
        举头望明月，
    </span>
    <span class="c2">
        低头思故乡！
    </span>
    </div>
    .c2{margin-left:100px;}将c2标签距离左边标签100px远

如果使垂直方向上下两个标签都设置了外边距（margin），那么取两者之间的  
最大值，如果是水平方向设置外边距，那么就取两个外边距之和。  

## 浮动 float

    <div class="c1"></div>
    <div class="c2"></div>
    .c1{background-color: red;
    width:100px;
    height:100px;
    display:inline-block}
    .c2{background-color:deeppink;
    width:100px;
    height:100px;
    float:right}

浮动会造成父级标签塌陷问题  
父级标签塌陷的原因：两个子标签浮动了，没有子标签撑起父级标签，所以父级标签就会塌陷  

解决浮动塌陷问题：  
1.设置父级标签的高度  
2.清除左右浮动的元素 clear:both使用clear清除左右浮动的元素  
3..clearfix:after{content:""; display:block; clear:both}  
清除浮动的最标准写法就是第三种写法还要将clearfix类名添加到父级标签里面去  

## overflow溢出标签

    .c3{width:200px;
        height:100px;
        border: 1px solid pink;
        overflow:hidden}
    将显示尺度以外的内容隐藏起来
    
    .c3{width:200px;
        height:100px;
        border: 1px solid pink;
        overflow:auto}
    显示一个下拉框，可以拉动看框里面的内容
    visible默认值，内容不会被修剪，会显示在元素框之外
    hidden内容会被修剪，并且元素框以外的内容是不能看见的
    scroll内容会被修剪，但是浏览器会显示滚动条，一边查看其他内容
    auto内容会被修剪，但是浏览器会显示滚动条，一边查看其他内容

## 定位

    position:relative相对定位，相对于自己原来的位置定位（保留原来阿位置）
    在使用left top right bottom来控制移动的方向
    left是控制往右移  right往左移 top往下移 bottom往上移
        
    absolute绝对定位，保不留原来的位置
    在使用了绝对定位以后，绝对定位会去寻找父标签的相对定位
    （position:relative）父标签没有就会继续往上去寻找。找不到
    相对定位的话就会以body标签为标准进行定位
        
    fixed就是固定定位，这个定位是根据浏览器的窗口来的，
    也可以说是根据body标签来的。将一个标签固定在一个位置，
    无论怎么滑动滚轮都不会变动标签的位置。

## z-index(显示优先级) and opacity(透明度)

```
z-index:10
z-indx:20
z-index:20的显示优先级要比z-index:10高，也就是z-index:20会显示在10的上面

opacity是整个标签的透明度，rgba就是背景颜色的透明度。
```

### 隐藏内容

+ 父级标签隐藏以后子标签也会隐藏起来

```
.c1{display:none}//将内容隐藏
```

# body标签

+ 有一些标签会自带margin和padding属性
+ 为了我们的内容能够铺满整个页面，我们会将body标签里面的margin和padding属性直接去掉。(基本上没写一个网页我们都会设置margin和padding属性)

```css
body{
	margin:0;
	padding:0;
}
```

