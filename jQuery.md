#  	jQuery

+ jQuery是对原生js代码的封装
+ 想要使用jQuery就要先将jQuery包引入
+ jQuery文件需要在js代码之前引入

```js
//引入方式
<script>jQuery.js</script>
```

+ jQuery对象和DOM对象

```js
//使用jQuery找到的对象叫jQuery对象
//使用原生的js方法找到的对象叫做DOM对象
//jQuery对象不能使用DOM方法，DOM对象也不能使用jQuery方法

//jQuery对象和DOM对象的互相转换
//DOM对象转换成jQuery对象
$(DOM对象)
//jQuery对象转换成DOM对象
jQuery对象[0]
```

## jQuery语法

### 基本选择器

```js
$('')
//使用id值查找标签
$('#dd')
//使用class值查找标签
$(".classname")
//使用标签名称查找标签
$("Tagname")
//配合使用
$("Tagname.classname")
```

### 组合选择器和层级选择器

```js
//组合选择器
$("#dd,.cc")  //,标签分组

//层级选择器
$('x y')//x后面所有的后代y
$('x > y')//x的所有儿子y
$('x + y')//找到紧挨着x后面的y
$('x ~ y')//x之后的所有兄弟y
```

### 基本筛选器

```html
<ul>
    <li id="l1">小阿牛</li>
<li>小憨憨牛</li>
<li>臭阿牛</li>
    <li id="l5"><span>坏阿牛</span></li>
<li>小牛牛</li></ul>
<script src="jQuery.js"></script>
<div title="xx">太白xx</div>
```



```js
//:first筛选出第一个标签
$('li:first')
//last筛选出标签里面的最后一个
$('li:last')
//筛选出索引等于index的那个元素
$('li:eq(1)')
//匹配所有索引值为偶数的元素
$('li:even')
//匹配所有索引值为奇数的元素
$('li:odd')
//匹配所有索引值大于给定值的元素
$('li:gt(index)')
//匹配所有索引值小于给定值的元素
$('li:lt(index)')
//移除所有满足not条件的标签
$('li:not(元素选择器)')
$('li:has(span)')
$('li:not(:has(span))')
```

### 属性选择器

```js
$("[title]")//找到标签里面有title属性的标签
$("[title='xx']")//找到title属性值为xx的标签
$("[title！='xx']")//找到title属性值不为xx的标签
```

### 表单筛选器

```html
<input type="text" disabled>
<input type="password">
<input type="radio" name="sex">male
<input type="radio" name="sex">famale
<input type="radio" name="sex">alex
<input type="checkbox" name="habby">抽烟
<input type="checkbox" name="habby">喝酒
<input type="checkbox" name="habby">烫头
```



```js
//找到input标签中所有type等于text的标签
$(":text")
//:password
//:file
//:radio
//:checkbox
//:submit
//:reset
//:button
```

### 表单对象属性筛选器

```js
//查看可用的input标签
$(":enabled")
//查看不可用的input标签
$(":disabled")
//查看被选中的input标签
$(":checked")
//查看被选中的select标签
$(":selected")
```

### 筛选器方法

```html
<ul>
    <li id="l1">小阿牛</li>
<li>小憨憨牛</li>
<li>臭阿牛</li>
    <li id="l5"><span>坏阿牛</span></li>
<li>小牛牛</li></ul>
<script src="jQuery.js"></script>
<div title="xx">太白xx</div>
```



```js
//找到下面的标签
//找到下一个兄弟标签
$("#l1").next()
$("#l1").next().next()
//找到该标签下面所有的兄弟标签
$("#l1").nextAll()
//直到找到该标签下面的某一个标签（不包含这个标签）
$("#l1").nextUntil("#l5")

//找到上面的标签
//找到上一个兄弟标签
$("#l5").prev()
//找到上面的所有兄弟标签
$("#l5").prevAll()
//直到找到上面某个标签为止
$("#l5").prevUntil("#l1")

//找到当前元素的父辈元素
$("#l5").parent()
$("#l5").parents()//查找当前元素的所有祖辈元素
//直到找到当前元素的某个祖辈元素为止
$("#l5").parentsUntil("body")

//儿子和兄弟元素
//找到儿子们
$("#l5").children()
//找到兄弟们
$("#l5").siblings()
$("#l5").siblings("#l1")

//find找子标签
$("ul").find("l1")
//找兄弟标签
$("li").filter("l5")
```

### 筛选器方法

```js
//.first获取到第一个元素
//.last获取到最后一个元素
//.not从指定元素的集合中删除与表达式匹配的元素
//.has
//.eq
```

### 类值操作(class)

```js
//添加类值
$(".c1").addClass("c2")
//删除类值
$(".c1").removeClass("c2")
//判断里面有没有某个类值
$(".c1").hasClass("c1")
//类值里面有就删除没有就添加
$(".c1").toggleClass("c2")
```

### css样式

```js
$(".c1").css("background-color","red")
$(".c1").css({"background-color":"yellow","width":"200px"})
```

### 位置操作

```js
//查看当前位置
$(".c1").offset()//查的是绝对位置（距离窗口的位置）
$(".c1").position()//查的是相对位置，（相对于父级标签的位置）
//设置位置
$(".c1").offset({"top":"50","left":"20"})
//查看滚轮向下滑动的距离
$(window).scrollTop();
//查看滚轮向右移动的距离
$(window).scrollLeft();
```

jQuery绑定事件的写法

```js
<script src="jquery.js"></script>
<script>
    $(".c1").click(function(){
    $(this).css({"background-color":"green"})
})
</script>
```

### 尺寸

```js
//获取盒子模型content的高度和宽度
$(".c1").height()
width()
//获取内容content的高度加两个padding的高度
innerHeight()
innerWidth()
//获取内容高度加两个padding高度加两个border高度。（不包括margin的高度，因为margin不是标签是标签和标签的距离）
outerHeight()
outWidth()
```

### 文本操作

```js
//text不认识标签
//html认识标签
//text标签拿到的是纯文本，html还会拿到里面的标签
$(".c1").text("<3>你好，太白</h3>")
$(".c1").html("<3>你好，太白</h3>")
```

### 值操作

```html
<body>
<label>username:<input type="text" name="username" id="username"></label>
<br>
sex:
<label><input type="radio" name="sex" value="1">female</label>
<label><input type="radio" name="sex" value="2">male</label>
<br>
hobby:
<label><input type="checkbox" name="hobby" value="1">smoking</label>
<label><input type="checkbox" name="hobby" value="2">drinking</label>
<br>
<label>city:<select name="" id="city">
    <option value="1">上海</option>
    <option value="2">北京</option>
    <option value="3">山东</option>
</select></label>
<label><select name="" id="author" multiple>
    <option value="1">老毛</option>
<option value="2">稻上飞</option>
<option value="3">周大圣人</option></select></label>
<script src="jQuery.js"></script>
</body>
```

```js
//拿到输入的值
var s = $("#username")
s.val();
//checkbox通过value来拿只能拿到一个值，想要拿到所有的被选中的值，只能通过循环的拿
for (var i in $(":checkbox:checked")){
    console.log($(":checkbox:checked")[i].value)
}
for (var i=0;i<$(":checkbox:checked").length;i++){
    console.log($(":checkbox:checked")[i].value)
}

//select多选
<label><select name="" id="author" multiple>
    <option value="1">老毛</option>
<option value="2">稻上飞</option>
<option value="3">周大圣人</option></select></label>

//设置值
//当type=text时
var a = $("#username").val("xx")
//当type=radio时
var a = $(":radio").val(["1"])
//select单选下拉框
var a = $("#city").val("1")
//select多选设置值
var a = $("#author").val(["1","2"])
//input多选设置值
var a = $(":checkbox").val(["1","2"])
```

### 属性操作

```js
//设置单个属性
$(".dd").attr("id","cc");
//设置多个属性
$(".dd").attr({"xx":"bb","age":"18"})
//获取属性值
$(".dd").attr("id");
//删除属性
$(".dd").removeAttr("xx");

//除了attr以外还有prop也可以对属性值进行操作，不过peop针对的是checked/selected/disabled……，之所以会有prop因为有些版本使用attr设置这些属性的时候会不生效。
//使用prop设置属性和使用attr设置属性还有一些不一样的地方
//使用attr查看checked属性的时候，如果有checked就会返回checked，如果没有就会返回undefined。使用prop查看属性，有checked就会返回true没有就会返回false

//使用attr设置checked
$(":radio").eq(0).attr("checked","checked")
//使用prop设置checked
$(":radio").eq(0).prop("checked",true)
//attr取消选中就有可能设置不了
$(":radio").eq(0).attr("checked",undefined)
//prop取消选中
$(":radio").eq(0).prop("checked",false)
```

### 文档处理和标签处理

```js
//appendTo
var dd = document.getElementById("dd")
var a = document.createElement("a")
a.setAttribute("href","http://wwww.baidu.com")
a.innerText = "百度"
$(a).appendTo("#dd")//把a标签添加到id为dd的标签里面去
$(a).appendTo($("#dd"))//也可以添加
//append
$("#dd").append(a)//把a标签添加到dd里面去
$("#dd").append("<a href='http://www.jd.com'>京东</a>")

//prepend和prependTO把标签添加到指定指定标签内部的前面
$("div").prepend($("a"))//把a标签放在div标签的后面
$(a).prependTo($("div"))
//after
$("div").after($("a"))//把a标签放在div标签的后面
$(a).insertAfter($("div"))
//before
$("div").before($("a"))//把a标签放在div标签的前面
$("a").insertBefore($("div"))


//清空标签
$("div").empty();
//删除标签
$("div").remove();

//替换标签
$("div").replaceWith($("a"))//就是使用a标签来替换div标签
$("div").replaceAll($("a"))//使用div标签来替换a标签

//克隆标签
$("div").clone()//复制一份标签
$("div").clone(true)//参数里面加一个参数true可以lian'to
```

### 事件

+ 事件的绑定方式

```js
//jQuery绑定事件方式方式一
$("#dd").click(function(){
console.log($("#dd").innerText())
})

//方式二	
$("#dd").on("click",function(){
    console.log($("#dd").innerText())
})
```

+ 常用事件

```
click//点击事件
focus//获得光标
blur//失去光标
change//域内容发生改变的时候发生的事件（多用于input标签和select标签）
hover//鼠标悬浮事件（hover事件分为两步，一步是鼠标放上去时触发的事件，一步是鼠标移下来是触发的事件）
示例：
	$('.cc').hover(function (){
        //第一步获得鼠标悬浮触发的事件
        $(this).css({"background-color":"green"})
    },
    //第二步鼠标移开的时候触发的事件
    function (){
        $(this).css({"background-color":"pink"})
    })
mouseenter//鼠标悬浮事件
mouseover//鼠标悬浮事件
//mouseenter和mouseover之间的区别，如果触发事件标签里面有子标签的话，标签绑定mouseenter事件，将鼠标移动到子标签里面去，事件不会再次触发，但是mouseover还会触发一次事件。

//一般来说键盘按下和键盘抬起是绑定在整个windows窗口的
keyup//键盘抬起事件
keydown//键盘按下事件
$(window).keydown(function (e){
        console.log(e.keyCode);//每一个键都有一个keyCode值，通过不同的key值来触发不同
    })

input//检测用户输入的内容(实时监测input框里面s)（只能使用on来绑定）
```

### 事件冒泡

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>事件冒泡</title>
    <style>
        #c1{
            height:200px;
            background-color:red;
        }
        #c2{
            height: 100px;
            width: 100px;
            background-color:black;
        }
    </style>
</head>
<body>
<div id="c1"><div id="c2"></div></div>
<script src="jQuery.js"></script>
<script>
    $('#c1').click(function (){
        alert("父级标签")
    })
    $("#c2").click(function () {
        alert("子标签");
        //防止冒泡事件的两种方式
        e.stopPropagation();
        return false
    })
</script>
</body>
</html>
```

### 移除事件

```js
off("click")
```

### 事件委托

+ 事件委托：在事件已经加载过去，新增加的标签想要绑定事件就需要使用事件冒泡原理，进行事件委托。将子标签需要触发的事件绑定到父级标签上面去。这样新增加进来的事件也会绑定事件。

```js
//事件委托必须通过on来进行委托
$('#dd').on('click','.c3',function (){
        alert('雪飞调教大壮，华坤很难受')
        var btn = document.createElement('button')
        console.log(btn)
        btn.innerText = '雪飞调教大壮，华坤很难受'
        btn.setAttribute('class','c3')
        document.getElementById('dd').append(btn)
    })
```

### 页面载入

```js
<script>
    ///window.onload表示在页面加载完以后才会加载里面的内容
    window.onload = function(){
		//script函数    
}
</script>
//window.onload有覆盖现象，会被后面的window.onload覆盖掉
//window.onload需要等待文件里面的图片视频全部加载完成以后才会被执行。
$(function (){
    //js代码
    //功能和window.onload一样，但是不会出现覆盖现象，还有就是只要文档里面的标签加载完以后，里面的代码就会加载。
})
```

# 动画

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>动画</title>
    <style>
        #d1{
            background-color:red;
            height:100px;
            width:200px;
            display: none;
        }
    </style>
</head>
<body>
<div id="d1"></div>
<script src="jQuery.js"></script>
</body>
</html>
```



```js
//两秒以后显现出来
$('#d1').show(2000)
//两秒以后隐藏
$('#d1').hide(2000)
//隐藏就显示显示就隐藏
$('#d1').toggle
//卷帘式显示
$('#d1').slideDown(2000)
//卷帘式隐藏
$('#d1').slideUp(2000)
//淡入淡出
$('#d1').fadeIn(2000)
$('#d1').fadeOut(2000)
$('#d1').fadeTo(2000)
$('#d1').fadeToggle(2000)
```

### 循环

```js
//each
$('li').each(function(k,v){
	//k是索引，v是列表元素
	console.log(k,v)
})

//使用each循环普通数组
var data = [1,2,3]
$.each(data,function(k,v){
	console.log(k,v)
})
//跳出循环
var data = [1,2,3]
$.each(data,function(k,v){
    if (k===1){
        return false
    }
	console.log(k,v)
})

//跳出本次循环
var data = [1,2,3]
$.each(data,function(k,v){
    if (k===1){
        return;
    }
	console.log(k,v)
})
```

### data

```js
//在标签上面储存任意相关数据，这个数据相当于全局变量可以在任意时候取出来。
//赋值
$('div').data("name","alex")
//取值
$('div').data('name')//没有值的话就会返回undefined
```

### 插件

```js
//就是往jQuery里面封装方法，在封装完以后就可以直接使用$.方法名调用
$.extend({
dazhuan:function (){
console.log('dazhuan不要出场费')
},
})
//调用
$.dazhuan()

//使用以上方法封装的方法，jQuery对象是调用不了的
$.fn.extend({
    xuefei:function(){console.log('我要出场费')}
})
//调用方法
$('div').xuefei()
```



