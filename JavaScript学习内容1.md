# javascript

javascript代码必须要写在script标签里面。  
script标签既可以写在head标签里面也可以写在body标签里面  
写一个javascript代码就要写一个;  
javascript是一个动态类型语言（动态类型语言就是不用申明变量类型，写进去什么类型就是什么类型）  

## javascript引入

    <script src="text.js"></script>    src后面放文件地址  
        直接在body标签或者head标签里面写script标签  

（;）分号是javascript的结束  

## 申明变量

    var a = 10;    什么变量时可以不赋值  
    ## javascript的数据类型  

typeof 查看一个数据的数据类型。  
        var a = 10;  
    undefined    typeof a    'number'  

## 数值类型number

JavaScript不分小数和整数，只有（数值类型）number。  

## 字符串类型string

    字符串拼接  
    var b = "alexdsb"    undefined    var c = " taibaidsb"    undefined    var d = b + c    undefined    d    'alexdsb taibaidsb'  

## JavaScript类型转换

    var a = "3"    undefined    parseInt(a);    3    var b = parseInt(a);    undefined    typeof b    'number'  
    var b = "1.11";    undefined    parseFloat(b);    1.11  

## JavaScript里面字符串的常用操作

length查看字符串的长度  

    var a = "hello"    undefined    a.length;    5  

trim() 去除字符串的空白trimLift trimRight  

    var a = "  hello  "    undefined    a.trim();    'hello'  

charAt通过索引取字符串里面的字符，从0开始取索引  

    var a = "hello";    undefined    a.charAt(0)    'h'  

concat字符串的拼接  

    var a = "hello";    undefined    var b = "world";    undefined    a.concat(b);    'helloworld'  

indexOf查找字符串莫格元素的索引  

    var a = "hello";    undefined    a.indexOf("e");    1    a.indexOf("e",2) 表示从索引2开始找e。找不到就会返回-1  

字符串的切片 按照索引切片，顾头不顾尾  

    var a = "hello";    undefined    a.slice(2, 4);    'll'  

toUpperCase和toLowerCase大写变小写和小写变大写  
        var a = "hello";  
    undefined    var b = a.toUpperCase();    undefined    b;    'HELLO'    b.toLowerCase();    'hello'  
split分割  

    a.split("e");    ['h', 'llo']        a.split("e", 1);写几就返回几个数据  
    ['h']  

## 布尔值 true 和 false

    空字符、0、null、undefined、NaN都是false  
    其他的是true  

##null和undefined  
        null一般在需要指定或清空一个变量才会使用  
    undefined是声明了一个变量但是没有给变量赋值时。  

## 对象类型 object

在javascript里面个python里面一样一切皆对象  
javascript里面可以自定义对象  

    var b = new String("world");    undefined    b    {'world'}    typeof b    'object'  

# 复杂数据类型或者说引用数据类型

## 数组 array

数组的定义  

    var a = [1,2,3];    undefined    a    [1, 2, 3]    typeof a    'object'  
    var c = new Array([22, 33]);    undefined    c    [Array(2)]0: (2) [22, 33]length: 1[[Prototype]]: Array(0)    typeof c;    'object'## 数组的常用方法和属性  

1.索引取值console.log()  

    var a = ["123", "ABC"];    console.log(a[1]);    \\ABC  

2.查看数组元素个数  

    a.length  

3.push尾部追加元素  

    a.push(1);    ['123', 'ABC', 1]  

4.unshift头部增加元素  

    a.unshift(22);    [22, '123', 'ABC', 1]  

5.数组的切片slice  

    a.slice(1,3);    ['123', 'ABC']  

6.pop删除尾部元素  
        a.pop()  

7.reverse 反转数组(原数组改变)  

    反转前：[22, '123', 'ABC', 1]  
    a.reverse()    反转后 [1, 'ABC', '123', 22]  

8.头部移除shift  

    a.shift()  

9.join将数组变成字符串  

    [1, 'ABC', '123', 22]    a.join("");    '1ABC12322'  

10.concat数组拼接 （不改变原数组）  

    拼接前：[1, 'ABC', '123', 22]  
    var c = ["憨批", "小阿牛"];  
    a.concat(c);    拼接后：[1, 'ABC', '123', 22, '憨批', '小阿牛']  

11.sort排序  

sort排序是先将数组里面的元素转化成为字符串，在将字符串的首个元素  
取出，取出首个元素之后，在按照首个元素在ascii码表里面的大小来对比大小。  
        var a = [88,7,53,28,9];  
    a.sort();    [28, 53, 7, 88, 9]  
想要sort排序，就要为sort制定排序规则  
    使用函数制定排序规则  
    function sortNumber(a,b){return a-b};    a.sort(sortNumber);    [7, 9, 28, 53, 88]  
12.splice删除数组中的元素并且向数组中增加新的元素  
splice里面的参数，第一个参数是规定从哪里开始删除元素  
第二个参数是规定删除几个元素  
后面的参数则是要替换的内容  

    var a = [12,32,43,33];    a.splice(1,2,"aa","bb","cc");    [32, 43]  

## 自定义对象{}

    var a = {"a" : 123,"b" : "321"}    
    typeof a    'object'    
    a["a"];    123    
    a.a;    123  

## javascript循环

    for (var i in a){    console.log(i);    }    a    b  
    for (var i in a) {        console.log(a[i]);    }    123    321  

在javascript里面使用a.键是在for循环里面是取不到值的  

## 算数运算符

    + - * / ++ -- %    ++ 就是自加1 --就是自减1  

## 比较运算符

    > <  >= <= !=(弱不等于)   ==（弱等于）  ===（强等于） !==（强不等于）  

## 逻辑运算符

    &&（and） ||（or）   ！（not）  

## 赋值运算符

    = += -= *= /=  

## 流程控制

### 条件判断if else

    var a = 10;    if (a === 10){        console.log("yes");    }else{console.log("no");}    yes    var a = 11;    if (a === 10){        console.log("yes");    }else{console.log("no");}    no  

if - else if - else  

### switch

    var a = 11;    switch (a){        case 9:            console.log(999);            break;        case 10:            console.log(101010);            break;        case 11:            console.log(111111);            break;        default:            console.log("啥也不对")  
    }    111111  

### 循环

循环数组for  

    for (var i in a){        console.log(a[i]);    }    a b c        for (var i = 0; i<a.length; i++){  
        console.log(i,a[i]);    }    0,"a" 1,"b"  2,"c"  

while循环  
        var i = 1;  
    while (i < 5){    console.log(i);    i++;    }      
javascript里面的三元运算符  

    var a = 1;    var b = 2;    var c = a > b ? a:b;    如果a>b，c就等于a否则c就等于b  
    c = b  

python里面的三元运算符  
        a = 1  
    b = 2    a = 10 if a > b else 11    print(a) 11  

## 函数

    function 函数名(参数){函数的主体}  
    例如：function f1(){  
    console.log("111")}    匿名函数  
    
    var 函数名 = function(参数){函数主体}  
    示例：  
    var sum = function(a,b){    return a + b;    }    sum(1,2);    3  

自执行函数  
自执行函数在页面打开的时候就自己执行了  

(function(a,b){console.log(a, b)}) (2, 5);
