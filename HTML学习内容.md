# html学习内容

html文件就是整个网页的架构  
css就是给网页添加细节，给网页添加颜色，定制尺寸等  
js动态效果（生成可以点击的连接按钮）(javascript)  
jquery就是对js的一种封装  
bootstrap就是对上面所有内容的封装版  

浏览器  
客户端给服务端发送消息叫请求  
服务端给客户端发送消息叫响应  

"HTTP/版本 200（状态码） ok \r\n\r\n"  

html文件的标签  

```HTML
标签必须是封闭的，一个是自封闭，一个是组合封闭。  
<meta># 自封闭标签  
<h1></h1> # 组合封闭标签  
```

## 标签属性

    <h1>内容</h1> 将内容加粗加黑  
    
    url 就是统一资源定位器（网址），通过url找到你想要的东西  
    <meta http-equiv="refresh" content="2;URL=https://www.cnblogs.com/socialism/">    http-equiv是一个标签属性 refresh的意思就是刷新 content=2代表着这个网页两秒以后会跳转。  
    这一句上面那一句话的意思就是刷新两秒以后跳转到https://www.cnblogs.com/socialism/">  
    
    <meta name="keywords" content="搜索内容">定义 搜索的关键字  
    
    <h1></h1>到<h6></h6>都是加粗加大，h1最大，h6最小  
    
    <button>我是一个按钮</button>  
    
    <b>加粗</b>  
    
    <i>倾斜</i>  
    
    <u>下划线</u>  
    
    <s>删除</s>  
    
    <br>换行  
    
    <hr>线条  
    
    <p></p>段落标签  
    
    <div></div>独占一行  
    <span></span>  <span>不独占一行，没有任何效果</span>  

## a标签

+ 如果a标签没有href属性值的话就和文本标签没啥区别。如果有href属性没有值的话，就会刷新当前页面。如果不想让a标签刷新页面，那么就把href属性值设置成#。将href属性值设置成javascript:void(0);那么就会保留a标签的效果并且不会刷新页面，也不会在url后面添加#。
+ 当前的url后面加上#，那么就不会刷新当前页面

```html
<a href="javascript:void(0);"></a>
```



## 图片标签

    <img src="" alt="" titel="" width="" height="">显示图片。  
    src里面可以放网络绝对路径和同一个文件下的相对路径。
    alt里面放的是加载不出来图片的时候显示的内容,title是鼠标悬浮时的提示信息。
    width是定义图片的宽度，height是定义图片的高度。
    
    <a href="网址">域名</a>标签超链接标签 target属性_blank就是使用其他页面打开，_self就是使用当前页面打开某个网站

## 排序列表标签

    <ul> <li></li> </ul> 无序列表标签 type控制属性 当type="none"  
    时，前面的小圆点就不显示，等于square时前面的小圆圈就会变成小方块。等于circle时前面就会变成空心圆点  
    
    <ol><li></li><\ol>有序列表标签,可以使用type来控制显示的符号，默认是显示数字，设置type等于a或A时就会显示英文  
    type设置成I，还可以设置start，设置start就是设置开始序号的值。  

## 题列表标签（菜单）

     <dl>
        <dt></dt>
        <dd></dd>
        </dl>
         <dl>
            <dt>菜单1</dt>
            <dd>西红柿炒鸡蛋</dd>
             <dt>菜单2</dt>
            <dd>竹笋炒肉丝</dd>
         </dl>

## html中的特殊符号

    &nbsp;就表示一个空格
    &lt;就表示小于号
    &gt;表示大于号
    &amp;表示and符号
    &copy;表示版权标识
    &reg;表示注册标识

## 表格标签

```
<table border="" cellpadding=""> # border表示加边框，里面的值表示边框的宽度
    cellpadding设置文字与内边框的距离
    cellspacing设置内边框与外边框的距离
    
    <thead>  # 表头
    <tr>  # 表示一行
    <th> # 表示一个单元格
    </th>
    </tr>
    </thead>
    <tbody>  # 列表的主体部分
    <tr>
    <td></td> # 一个单元格
    </tr>
    </tbody>
    </table>

```



## form标签 表单标签 (将数据提交到后台)

    <from action="http://127.0.0.1:8001" method="post">
    	method可以设置请求的方式，默认为po
        action 指定数据提交的路径
        enctype可以更改提交数据的
        用户名：<input type="text",name="username">
        密码：<input type=password name="password">
        <br>
        <br>
        <input type='file'></input>
        # type=file表示传输文件，想要获取文件对象需要使用files[0]
        <input type="radio" name="sex" value="1"> male
        <input type="radio" name="sex" value="2"> female
        <br>
        <br>
        <input type="checkbox" name="hobby" value="a"> drink
        <input type="checkbox" name="hobby" value="b"> smoking
        <input type="checkbox" name="hobby" value="c"> perm
        <input type="submit" value="register"> # 将from标签里面的内容全部提交到指定地址
        <button>提交</button> # button也可以提交from表单中的值
        </from>     指定按钮显示的值


## input标签 用户标签 （可以写在from表单里面）

    方式1  
    <label for="username">用户名</label>  
    <input type="text" name="username" id="username"> # 普通的输入框  
    方式2  
    <label><input type=password name="password" id="password"readonly> # 输入的内容变成密文的</label>  
    readonly使得输入框只能看不能改，使用readonly数据还可以提交到后台去  
    disabled可以限制输入框和单选多选框的输入，不过使用了disabled以后数据就不能提交到后台去了  
    
    <input type="radio" name="sex" value="a"> male    <input type="radio" name="sex" checked="checked" value="b"> female  单选框  
    checked 默认选中      
    输入框里面name是分组，但是在选择框里面name是提交数据的一个值  
    选择框没有value数据就无法提交，提交的数据就是on  
    
    <input type="checkbox"> drink    <input type="checkbox"> smoking    <input type="checkbox"> perm  
    <input type="date"> 日期输入框  
    <input type="button">    <input type=reset>  # 重置from表单里面所有的内容  
    <input type=hidden>    <input type=file>  # 选择文件  
    <input type="submit"> # 提交按钮  
    value在输入框里面表示默认值  

## select和label标签（可以写在from表单里面）

    select是一个下拉伸输入框（下拉选择框）  
        <select name="" multiple>  
    <option value="" selected> 北京</option>  
    <option value=""> 上海</option>  
    <option value=""> 深圳</option>  
    </select>    select标签和option标签是固定搭配标签  
    没有value数据也可以提交，但是提交的是文本  
    在标签里面加一个multiple就是下拉多选  
    在option标签里面加一个selected就表示默认选中  

## textarea标签

        <textarea name="" id="" cols="30" rows="10"></textarea>  
    name是提交数据使用的，id是配合label标签使用的，  
    cols是设置输入的列数，rows是设置输入的行数  
    可以使用disable禁用文本框  

标签分类（超文本标记语言）  

    内敛标签：不独占一行内敛标签只能嵌套内敛标签  
     块级标签：自己独占一行，块级标签可以嵌套内敛标签和某些块级标签    \h1-h6\br\hr\p\div    p标签里面不能加块级标签也不能加p标签  
    # 去除网页的margin和padding使得网页更加丰满  
    再写html文档的时候都要写  
    body{    margin:0;    padding:0;    }
