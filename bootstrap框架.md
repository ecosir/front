# bootstrap框架

+ bootstrap的两种引入方式
  + 可以通过下载bootstrap文件在本地直接将本地文件引入
  + 课可以将网址写在地址栏里面引入

```html
<!--通过下载文件到本地的引入-->
<link rel="stylesheet" href="./bootstrap-3.4.1-dist/css/bootstrap.min.css">
<!--通过网页的形式将bootstrap引入-->
<link rel="stylesheet" href="	https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css">
```

## 布局容器

```html
<!--container将页面的左右两边进行留白-->
<div class="container"></div>
<!--container-fliud 将整个页面全部铺满-->
```

### 栅格系统

```html
<!--row将屏幕分成12块-->
<!--col-md-2 取两块屏幕 屏幕宽度大于992时使用的格式-->
<!--屏幕宽度大于1200px时使用col-lg--->
<!--屏幕宽度大于768px使用col-sm->
<!--col-xs-会根据屏幕宽度自动调节-->
<div class="row">
    <div class="col-md-2">
    </div>
</div>
<!--如果十二占用的屏幕超过了十二份，那么就会自动换行-->

<!--列偏移-->
<!--col-md-offset-5就表示向右边移五格-->
<!-- --col-xs-offset-5和--col-lg-offset-5 -->

<!--列排序-->
<!--col-xs-2 col-xs-push-10表示向右推十份，col-xs-2 col-xs-pull-10表示向左拉两份-->
<div class="row">
    <div class="col-xs-2 col-xs-push-10">
    </div>
    <div class="col-xs=10 col-xs-pull-2">
    </div>
</div>


<!--嵌套列-->
<div class="row">
    <div class="col-xs-9">
        <div class="row">
            <div class="col-xs-6">
                
            </div>
        </div>
        
    </div>
</div>
<!--上面代码的意思就是将屏幕分成十二块以后，取九块，再将取到的九块分成十二块，再取六块-->

```



## table

+ 通过类值来操作table标签的样式。

```html
//table添加表格样式
//table-border为表格添加边框
//table-hover当鼠标光标移动到表格的上面时就会变颜色
//table-striped表格添加样式（表格变成灰白交替的颜色）

<table class="table table-bordered table-hover table-striped">
    <thead><tr><th>name</th><th>position</th></tr></thead>
    <tbody><tr><td>牛牛</td><td>teacher</td></tr></tbody>
```

# 图标

+ bootstrap上面的图标库
+ 阿里开源的图标库icon font

```html
//引入文件
<link rel="stylesheet" href="./download/font_3l2g8h11lga/iconfont.css">
//第一种设计方式
<input type="text" class="iconfont" value="&#xeafe;">
//第二种设计方式
<span class="iconfont" style="font-size:30px;color:darkorange">&#xeafe;</span>
```

+ font awesome矢量库（是使用的比较多的矢量图标库）

```html
<link rel="stylesheet" href="./font-awesome-4.7.0/css/font-awesome.css">
<i class="fa fa-search"></i>
<i class="fa fa-camera fa-2x"></i>
```



+ 使用这种图标想要设置他的颜色大小就直接使用字体的设置方式就行。
