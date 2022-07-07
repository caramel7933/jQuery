## `1`- jQuery 属性操作

- 单选题

    关于jQuery,以下描述正确的是:

```
    A，prop() 可以获取和设置普通属性，但是表单属性 disabled / selected / checked 等就无能为力了

    B，attr() 可以获取和设置普通属性，但是自定义属性就无能为力了

    C， data()可以自定义属性，且不会出现在标签上

    D，以上答案均正确
```

答案: C

解析: 

A选项，prop() 可以操作表单属性 disabled / selected / checked等，且只适合他操作。

B选项，attr() 可以自定义属性

## `2`- jQuery 文本属性值

- 单选题

    下列方法，可以获取 input 中 value 属性的方法是:

```
A，html()

B，text()

C，val()

D，三个方法都不可以
```

答案: C

解析: 

​	A选项，类似 innerHTML 属性

​	B选项，类似 innerText 属性

​	C选项，类似value属性

## `3`- jQuery 元素操作

- 多选题

    下列 jQuery 的元素操作，说法正确的是:

```
    A，each() 可以遍历jQuery对象中的每一个元素，但是回调函数中的对象为DOM对象

    B，jQuery 创建元素只有 $('标签') 这一种方法

    C，append() 和 prepend() 功能完全相同，可以交换使用

    D，remove() 和 html() 都可以删除元素
```

答案: AD

解析: 

​	B选项，html() 识别标签，所以也可以用它创建元素。

​	C选项，append() 和 prepend() 前者添加到父元素的最末尾，后者添加到最前面。

## `4`- jQuery 的尺寸操作

- 多选题

    以下说法，正确的是：

```
    A，height() 既可以获取 height 值，也可以设置 height 值

    B，css('height')和height()获取的结果完全一样，只不过 height() 更简单一点儿

    C，height() 和 innerHeight() 和 outerHeight() 方法获取的盒子属性不一样

    D，以上说法都正确
```

答案: AC

解析: 

B选项: css('height')获取的是字符串带有单位，height() 获取的是数值，无单位

## `5`- jQuery 位置操作

- 多选题

    下列 jQuery 方法，描述错误的是：

```
    A，offset()方法用于获取盒子距离整个页面的距离，和父盒子是否有定位没有关系

    B，position()获取的是距离所有父盒子中，嵌套自己最近的父盒子的距离，可以获取，也可以赋值

    C，scrollTop()和scrollLeft()可用于获取盒子或者页面顶部和左侧的超出（或者卷起）部分

    D，animate()可以让页面滑动到顶端或者指定位置，使用方法需要两个参数：animate( scrollTop, 值); 
```

答案: BD

解析: 

B选项，position() 只能获取值，不能赋值

D选项，animate() 滑动页面的正确用法是传递一个对象：animate( {scrollTop: 值} )

## `6`- 代码题

- 单选题

    运行一下代码，正确的输出结果是：

```html
<body>
  	<style>
        div {
            height: 100px;
            width: 200px;
            background-color: pink;
            margin: 10px;
            padding: 20px;
            border: 10px solid red;
        }
    </style>

    <div></div>
    <script	src='http://code.jquery.com/jquery-latest.js'>
    <script>
        $(function() {
            console.log($("div").innerWidth());
        })
    </script>
</body>
```

```
    A，120

    B，140px

    C，220

    D，240
```

答案：D

解析：

1. innerWidth() / innerHeight()  获取设置元素 width和height + padding 大小 

2. 不带单位

## `7`- 综合题

- 多选题

    下列说法，错误的是：

```
    A，attr()和 prop()都可以操作普通属性，前者更适合自定义属性操作，后者更适合操作表单属性disabled、selected、checked等

    B，html() 和text() 功能一样，可以替换使用

    C，after() 是把调用者作为父元素，把参数作为子元素，放到调用者的最末尾

    D，scrollTop() 操作页面时，只可以获取页面被卷去的部分，不能赋值修改页面的显示位置
```

答案：BCD

解析：

B选项，错误在于html()识别标签，text()不识别标签

C选项，错误在于after()方法是以兄弟节点的形式插入节点

D选项，scrollTop() 既可以获取页面被卷去的部分，也可以进行赋值修改

## `8` - 按键变色

- 题目描述

    按键变色主要考察事件对象event的属性的使用，可以类比DOM中的event获取按键值：

    1）按下键盘键触发事件

    2）根据所按键盘的字母给盒子上自定义背景色

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jQuery.min.js"></script>
    <style>
        .wrap {
            width: 400px;
            height: 400px;
            margin: 100px auto 0;
        }
        .wrap h1 {
            text-align: center;
        }
        .wrap div {
            width: 400px;
            height: 300px;
            text-align: center;
            line-height: 300px;
            font-size: 30px;
            background: darkorchid;
        }
    </style>
</head>
<body>
    <div class="wrap">
        <h1>按键改变颜色</h1>
        <div id="bgChange">
            keyCode为: <span id="keyCodeSpan"></span>
        </div>
    </div>
    <script>
        $(function() {
            //需求：在整个页面按下键盘上的键，判断Unicode编码，设置背景和内容;
             //绑定事件(keydown可以获取组合键；keyCode/charCode)
                //keydown--keyCode;     keypress--charCode;
                //82:r; y:89; s:83; 
                $(document).on("keydown", function(event) {
                    $("#keyCodeSpan").text(event.keyCode);
                    switch(event.keyCode) {
                        case 82:
                            $("#bgChange").css("background", 'orange');
                            break;
                        case 89:
                            $("#bgChange").css("background", 'pink');
                            break;
                        case 83:
                            $("#bgChange").css("background", 'blue');
                            break;
                        default: 
                            $("#keyCodeSpan").text("无此键位");
                            $("#bgChange").css("background", "darkorchid");
                    }
                });
            })
    </script>
</body>
```

## `9`- 背景色插件

- 题目描述

    点击按钮，改变div的背景色，jQuery中的animate()不能实现背景色渐变，需要引入插件

- 训练目标

  学会使用插件

- 训练提示

  1.先引入jQuery，然后在引入jQuery插件：jquery.color.js

  2.常规调用animate() 该方法得到增强

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jQuery.min.js"></script>
    <script src="js/jquery.color.js"></script>
    <style>
        div {
            width: 200px;
            height: 200px;
            margin: 100px;
            background-color: orange;
        }
    </style>
    <script>
        $(function () {
            //点击按钮，改变背景色

            $("button").on("click", function () {
                //通过css也可以实现，但是我们要的是循序渐进的改变颜色；（ animate() ）
                var json = {
                    "background-color":"#f40",  // 必须是 background-color， 只写 background 无效
                    "width":600
                };
                $("div").animate(json,2000);
            });
        });
    </script>
</head>
<body>
    <button>改变背景色</button>
    <div></div>
</body>
</html>
```

## `10`- 五星好评

- 题目描述

    鼠标进入五角星，当前和之前的所有五角星变为实心，后面的是空心。点击记录该五角星，鼠标移开后该记录点之前所有变为实心，之后的所有变为空心

- 训练目标

  培养使用jQuery综合处理需求能力

- 训练提示

  1.鼠标进入某个五角星，当前和之前的所有五角星变为实心，后面的是空心

  2.鼠标点击某个五角星，记录该五角星

  3.鼠标移开后该记录点之前所有变为实心，之后的所有变为空心

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jQuery.min.js"></script>
    <style>
        body {
            font-family: "simsun";
        }
        ul {
            list-style: none;
        }
        .comment {
            font-size: 40px;
            color: #ff1100;
        }
        .comment li {
            float: left;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <ul class="comment">
        <li>☆</li>
        <li>☆</li>
        <li>☆</li>
        <li>☆</li>
        <li>☆</li>
    </ul>
    <script>
        $(function() {
            //空心五角星和实心五角星
            var KX_WJX = "☆";
            var SX_WJX = "★";

            //需求1：鼠标进入哪个li，当前的和之前的所有全部变为实心五角星;
            $(".comment>li").on("mouseenter", function () {
                //当前的和之前的所有全部变为实心五角星;其他的变为空心;
                $(this).text(SX_WJX).prevAll("li").text(SX_WJX);
                $(this).nextAll("li").text(KX_WJX);
            });

            //需求2：鼠标移开ul, 默认全部空心，如果点击过某一个就以他为基准，之前的全部实心;
            $(".comment").on("mouseleave", function () {
                //如果有类名，就要以类名为参考点;
                if($(".current").length == 0){
                    //等于0就说明没有点击过;
                    $(".comment>li").text(KX_WJX);
                }else{
                    //不等于0，肯定等于1；就说明点击过，那么就以他为参考点;
                    $(".current").text(SX_WJX).prevAll("li").text(SX_WJX)
                    $(".current").nextAll("li").text(KX_WJX);
                }
            });

            //需求3：鼠标点击哪个li，这个li就是参考li;(当前的添加类，其他的删除类)
            $(".comment li").on("click", function() {
                $(this).addClass("current").siblings("li").removeAttr("class");
            })
        })
    </script>
</body>
```