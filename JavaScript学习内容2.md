# JavaScript面向对象编程

```javascript
// 封装一个类
function Person(name){
    this.name = name
}
// 调用封装的类进行实例化

var p = new Person("taibai")p.name
Person.prototype.sum = function(a,b){
    return a+b
}p.sum(2,3)
5
```

## date对象

```js
// 实例化一个date对象
// 获取当前时间
var d = new Date()
d  结果： Sat Oct 08 2022 12:57:16 GMT+0800 (中国标准时间)
console.log(d.toLocaleString())

var d2 = new Date("2004/4/24 11:12");
console.log(d2.toLocaleString())
// 2004/4/24 11:12:00

```

### date对象里面的方法

```js
// 获取当前时间对象

var d = new Date()

d.getDate() // 获取当前日期
d.getDate()  // 获取当前星期0-6 周日是数字0
d.getMonth()  // 获取当前月份（0-11表示，0表示一月）
d.getFullYear()   // 获取当前完整年份
d.getHours()   // 获取小时


d.getMinutes() // 获取分钟
d.getSeconds() // 获取秒
d.getMilliseconds()   // 获取毫秒
d.getTime()  // 返回以毫秒计的时间戳
```

# json序列化

```js
var str1 = '{"name":"chao", "age":68}'
var obj1 = {"name":"chao", "age":68}
// 将json字符转换成为对象
var obj = JSON.parse(str1);
// 将对象转化成为JSON字符串
var str = JSON.stringify(obj1)

```

# RegExp对象

```js
//创建正则规则
var reg = new RegExp("^[a-zA-Z][a-zA-Z0-9_]{5,11}$")
//定义字符串
var s = "helloo"
//测试字符串是否符合正则规则
reg.test(s)
//正则规则的简写方式
var reg1 = /^[a-zA-Z][a-zA-Z0-9_]{5,11}$/;
//如果test方法里面什么都不写，那么就会默认在里面放一个undefined如果你定义的正则规则符合undefined那么就会返回你一个true


//正则的方法
s.smatch(/o/) //就表示匹配s字符串里面的o不过自会匹配第一个就返回
s.smatch(/o/g) // 表示把s字符串里面的所有o匹配出来
s.search(/o/) //表示匹配到元素索引位置，加不加g效果一样
s.split(/o/)// 表示按照正则表达式对字符串进行切割，得到一个新的值，原来的字符串不变
s.replace(/o/gi,"s")  // 表示按照正则规则来进行字符串的替换，后面加上i表示不区分大小写

//正则里面的坑
var reg = /a/g
var s = "alex is a sb"
reg.test(s)
//返回结果：true
reg.test(s)
// 返回结果：true
reg.test(s)
// 返回结果：false
re.test(s)
// 返回结果：true
reg.lastIndex 
```

# math对象

```js
var a = -10
Math.abs(a)  // 将a的绝对值返回
Math.exp(a)  //返回e的a次方
var a = 1.2
Math.floor(a) //舍去a的小数部分
var log(a)  // 返回以e为底的自然对数
Math.max(x,y)  // 返回x和y中的最大值
Math.min(x,y)   // 返回x和y中的最小值
Math.pow(x,y)  // 返回x的y次幂
Math.random()  // 返回0-1之间的随机数
Math.round(x)  // 把数四舍五入为最接近的整数
Math.sin(x)  //返回角的正弦
Math.sqrt(x)  // 返回数的平方根
Math.tan(x)  //返回角的正切
```

# BOM模型

## window对象

+ window对象是全局的对象，全局的变量和函数都归window对象

```js
//window对象里面的方法
//查看浏览器窗口的高度
window.innerHeight
// 查看浏览器内部的宽度
window.innerWidth
//打开新的窗口
window.open()
//关闭当前窗口（只能关闭用window.open打开的窗口）
window.close()

```

+ navigator对象

```js
// 拿到浏览器的全称
navigator.appName
// web浏览器厂商和版本的详细信息
navigator.appVersion
//客户端绝大部分信息
navigator.userAgent
// 拿到浏览器所在的操作系统
navigator.platform
```

### screen对象

```js
// 可用的屏幕宽度
screen.availWidth
// 可用的屏幕高度
screen.availHeight
```

### history对象

+ 浏览器的历史对象

```js
// 前进一页
history.forward()
//后退一页
history.back()
```

### window对象中的子对象location

```js
//获得当前页面的url
window.location.href
//指定当前的url
window.location.href = "https://www.bilibili.com/video/BV13J411H7u5?p=276&spm_id_from=pageDriver&vd_source=b2ddbd16bf7829fc298bf04bcba9be06"
//刷新页面
location.reload()
```

#### 弹窗

```js
//直接在浏览器窗口写是不起作用的，需要在js代码里面写
alert("aaa")
//确认框
confirm("你好")
prompt("请在下方输入内容","你的答案")
```



### 计时器

```js
//setTImeout一段时间以后做某些事情(通产搭配函数来使用)
setTimeout("js语句",毫秒)
setTimeout(js语句,毫秒)//没有延迟
//搭配函数使用setTimeout
var a = setTimeout(function (){
confirm("xxx")
}, 3000)
//clearTimeout清除即将要执行的计时器
clearTimeout(a)

//setInterval每隔一段时间就会做某事
var a = setInterval(function (){
    console.log("xxx")
},3000)
//clearInterval
```

# DOM模型

## 查找标签

### 直接查找

```html
<div class="c2" id="d2">
    <div class="cc" id="dd">待到秋来九月八，我花开后百花杀</div>
<div class="c1" id="d1">十年磨一剑，霜刃未曾试</div>
</div>
```



```js
//通过标签里面的id值来查找标签
document.getElementById("dd")
//通过标签的class值来查找标签，返回的是数组
document.getElementsByClassName("cc")
//通过标签名来查找标签,返回的是数组
document.getElementsByTagName("div")
```

### 间接查找

```js
//查找当前标签的父标签
var a = document.getElementById("cc")
a.parentElement;
//将标签里面的内容全部变成xx
a.parentElement.innerText = "xx"
//找到标签里面的所有子节点
var a = document.getElementsByClassName("c2")
a.children
//获得第一个子标签元素
a.firstElementChild
//获得最后一个子标签元素
a.lastElementChild
//获得上一个兄弟标签元素
a.nextElementSibling
//获得下一个兄弟标签元素
previousElementSibling
```

### 节点操作

```js
//创建节点
var a = document.createElement("a")


//添加节点
//找到节点
var d2 = document.getElementById("d2")
//创建节点
var a = document.createElement("a")
//为创建的节点添加文本内容
a.innerText = "百度"
//添加节点
d2.appendChild(a) //将a节点添加到d2节点的最后面
var dd = document.getElementById("dd")
d2.insertBefore(a,dd)//将a节点添加到dd节点的前面去

//删除标签
d2.removeChild(dd)


//替换标签
//找到节点
var d2 = document.getElementById("d2")
//创建节点
var a = document.createElement("a")
//为创建的节点添加文本内容
a.innerText = "百度"
var dd = document.getElementById("dd")
dd.replaceChild(a,dd)
```

### 文本操作

```js
//innerText不可以识别标签
//innerHTML可以识别标签
```



### 属性操作

```js
//创建标签
var a = document.createElememt("a")
a.innerText = "百度"
//设置属性
a.setAttribute("href", "http://www.baidu.com")
var d2 = document.getElementById("d2")
d2.appendChild(a)

//获取属性
a.getAttribute("href")

//删除属性
a.removeAttribute("href")

//如果是标签自带的属性那么就可以.属性名称来获得和设置属性的值		
a.href
a.href = "xxx"

//input标签输入值的操作
var inp = document.getElementById("inp")
inp.value //查看值
inp.value = "超"  //设置值

//select
var inp = document.getElementById("city")
```



### class操作

```js
//
var d2 = document.getElementById("d2")
d2.classList  //获取这个标签的class列表
d2.classList.add("xx2") //添加列表里面的值
d2.classList.remove("xx2")//删除class列表里面的值
d2.classList.contains("xx2")//查看当前有没有这个值，返回的是bool值
d2.classList.toggle("xx2)//当前的值有就删除没有就添加
```

### css操作

```js
var d = document.getElementById("d2")
d2.style.backgroundColor
d2.style.backgroundColor = "deeppink"
d2.style.css操作
//不能有横杆，把横杆去掉在讲首字母大写就可以了
```

### 事件

```
//onclick点击事件
//ondblclick双击对象事件
//onfocus获得光标时触发的事件
//onblur失去光标时触发的事件
//onchange标签里面的内容发生变化的时候触发（一般用在select标签）
//onkeydown 某个键盘键被按下触发的事件
//onkeypress某个按键被按下并且松开
//onkeyup某个按键被松开
//onload一张页面或者一幅图完成加载
//onmousedown鼠标键被按下
//onmousemove鼠标被移动
//onmouseout鼠标从某元素移开
//onmouseover鼠标移动到某个元素上
//onselect在文本框中的文本被选中是触发
```

```js
//设置选中
checked = true
$("[type='checkbox']")[2].checked = true
//设置不选中
checked = false

//查看是否被选中
var dd = document.getElementsByClassName("dd");
dd[0].checked
```

