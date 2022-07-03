## `1`- 下拉菜单

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jquery.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        ul {
            list-style: none;
        }
        a {
            text-decoration: none;
            font-size: 14px;
        }
        .nav {
            margin: 100px;
        }
        .nav>li {
            position: relative;
            float: left;
            width: 88px;
            height: 41px;
            text-align: center;
        }
        .nav li a {
            display: block;
            width: 100%;
            height: 100%;
            line-height: 41px;
            color: #666;
        }
        .nav>li>a:hover {
            background: #eee;
        }
        .nav ul {
            display: none;
            position: absolute;
            top: 41px;
            left: 0;
            width: 100%;
            border-left: 1px solid #FECC5B;
            border-right: 1px solid #FECC5B;
        }
        .nav ul li {
            border-bottom: 1px solid #FECC5B;
        }
        .nav ul li a:hover {
            background-color: #FFF5DA;
        }
    </style>
</head>
<body>
    <ul class="nav">
        <li>
            <a href="javascript:;">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="javascript:;">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="javascript:;">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="javascript:;">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="javascript:;">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
    </ul>
    <script>
        $(function() {
            $(".nav>li").mouseover(function() {
                $(this).children("ul").show();
            });
            $(".nav>li").mouseout(function() {
                $(this).children("ul").hide();
            })
        })
    </script>
</body>
```

## `2`- 淘宝服饰精品案例

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="../../jquery.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            font-size: 12px;
        }
        ul {
            list-style: none;
        }
        a {
            text-decoration: none;
        }
        .wrapper {
            overflow: hidden;
            width: 250px;
            height: 248px;
            margin: 100px auto 0;
            border: 1px solid pink;
            border-right: 0;
        }
        #left, #content {
            float: left;
        }
        #left li {
            background: url(lili.jpg) repeat-x;
        }
        #left li a {
            display: block;
            width: 48px;
            height: 27px;
            border-bottom: 1px solid pink;
            line-height: 27px;
            text-align: center;
            color: black;
        }
        #left li a:hover {
            background-image: url(abg.gif);
        }
        #content {
            border-left: 1px solid pink;
            border-right: 1px solid pink;
        }
    </style>
</head>
<body>
    <div class="wrapper">
        <ul id="left">
            <li>
                <a href="javascript:;">女靴</a>
            </li>
            <li>
                <a href="javascript:;">雪地靴</a>
            </li>
            <li>
                <a href="javascript:;">冬裙</a>
            </li>
            <li>
                <a href="javascript:;">呢大衣</a>
            </li>
            <li>
                <a href="javascript:;">毛衣</a>
            </li>
            <li>
                <a href="javascript:;">棉服</a>
            </li>
            <li>
                <a href="javascript:;">女裤</a>
            </li>
            <li>
                <a href="javascript:;">羽绒服</a>
            </li>
            <li>
                <a href="javascript:;">牛仔裤</a>
            </li>
        </ul>
        <div id="content">
            <div>
                <a href="#"><img src="女靴.jpg"></a>
            </div>
            <div>
                <a href="#"><img src="雪地靴.jpg"></a>
            </div>
            <div>
                <a href="#"><img src="冬裙.jpg"></a>
            </div>
            <div>
                <a href="#"><img src="呢大衣.jpg"></a>
            </div>
            <div>
                <a href="#"><img src="毛衣.jpg"></a>
            </div>
            <div>
                <a href="#"><img src="棉服.jpg"></a>
            </div>
            <div>
                <a href="#"><img src="女裤.jpg"></a>
            </div>
            <div>
                <a href="#"><img src="羽绒服.jpg"></a>
            </div>
            <div>
                <a href="#"><img src="牛仔裤.jpg"></a>
            </div>
        </div>
    </div>
    <script>
        $(function() {
            // 1. 鼠标经过左侧的小li 
            $("#left li").mouseover(function() {
               // 2. 得到当前小li 的索引号
                var index = $(this).index();
                // 3. 让右侧盒子相应索引号的图片显示出来
                $("#content div").eq(index).show();
                // 4. 让其余的图片（就是其他的兄弟）隐藏起来
                // $("#content div").eq(index).siblings().hide();
                // 链式编程
                $("#content div").eq(index).show().siblings().hide();
            })
        })
    </script>
</body>
```

## `3`- tab栏切换

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jquery.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        ul {
            list-style: none;
        }
        .tab {
            width: 978px;
            margin: 100px auto;
        }
        .tab_list {
            height: 39px;
            border: 1px solid #ccc;
            background-color: #f1f1f1;
        }
        .tab_list li {
            float: left;
            height: 39px;
            line-height: 39px;
            padding: 0 20px;
            text-align: center;
            cursor: pointer;
        }
        .tab_list .current {
            background-color: #c81623;
            color: #fff;
        }
        .item {
            padding: 20px 0 0 20px;
        }
        .item {
            display: none;
        }
    </style>
</head>
<body>
    <div class="tab">
        <div class="tab_list">
            <ul>
                <li class="current">商品介绍</li>
                <li>规格与包装</li>
                <li>售后保障</li>
                <li>商品评价（50000）</li>
                <li>手机社区</li>
            </ul>
        </div>
        <div class="tab_con">
            <div class="item" style="display: block;">
                商品介绍模块内容
            </div>
            <div class="item">
                规格与包装模块内容
            </div>
            <div class="item">
                售后保障模块内容
            </div>
            <div class="item">
                商品评价（50000）模块内容
            </div>
            <div class="item">
                手机社区模块内容
            </div>
        </div>
    </div>
    <script>
        $(function() {
            $(".tab_list li").click(function() {
                $(this).addClass("current").siblings().removeClass("current");
                var index = $(this).index();
                $(".tab_con .item").eq(index).show().siblings().hide();
            })
        })
    </script>
</body>
```

## `4`- 简洁版滑动下拉菜单

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jquery.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        ul {
            list-style: none;
        }
        a {
            text-decoration: none;
            font-size: 14px;
        }
        .nav {
            margin: 100px;
        }
        .nav>li {
            position: relative;
            float: left;
            width: 80px;
            height: 41px;
            text-align: center;
        }
        .nav li a {
            display: block;
            width: 100%;
            height: 100%;
            line-height: 41px;
            color: #333;
        }
        .nav>li>a:hover {
            background-color: #eee;
        }
        .nav ul {
            display: none;
            position: absolute;
            top: 41px;
            left: 0;
            width: 100%;
            border-left: 1px solid #FECC5B;
            border-right: 1px solid #FECC5B;
        }
        .nav ul li {
            border-bottom: 1px solid #FECC5B;
        }
        .nav ul li a:hover {
            background-color: #FFF5DA;
        }
    </style>
</head>
<body>
    <ul class="nav">
        <li>
            <a href="#">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
        <li>
            <a href="#">微博</a>
            <ul>
                <li>
                    <a href="">私信</a>
                </li>
                <li>
                    <a href="">评论</a>
                </li>
                <li>
                    <a href="">@我</a>
                </li>
            </ul>
        </li>
    </ul>
    <script>
        $(function() {
            // 方法一 
            $(".nav>li").mouseover(function() {
                $(this).children("ul").stop().slideDown();
            });
            $(".nav>li").mouseout(function() {
                $(this).children("ul").stop().slideUp();
            })

            // 方法二
            $(".nav>li").hover(function() {
                $(this).children("ul").stop().slideDown(200);
            }, function() {
                $(this).children("ul").stop().slideUp(200);
            })

            // 方法三
            $(".nav>li").hover(function() {
                // stop 方法必须写到动画的前面
                $(this).children("ul").stop().slideToggle(150);
            })
        })
    </script>
</body>
```

## `5`- 王者荣耀手风琴效果

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="../jquery.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        img {
            display: block;
        }
        ul {
            list-style: none;
        }
        .king {
            overflow: hidden;
            width: 852px;
            margin: 100px auto;
            padding: 10px;
            background: url(images/bg.png) no-repeat;
        }
        .king li {
            position: relative;
            float: left;
            width: 69px;
            height: 69px;
            margin-right: 10px;
        }
        .king li.current {
            width: 224px;
        }
        .big {
            width: 224px;
            display: none;
        }
        .king li.current .big {
            display: block;
        }
        .king li.current .small {
            display: none;
        }
        .small {
            position: absolute;
            top: 0;
            left: 0;
            width: 69px;
            height: 69px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="king">
        <ul>
            <li class="current">
                <a href="#">
                    <img src="images/m1.jpg" alt="" class="small">
                    <img src="images/m.png" alt="" class="big">
                </a>
            </li>
            <li>
                <a href="#">
                    <img src="images/l1.jpg" alt="" class="small">
                    <img src="images/l.png" alt="" class="big">
                </a>
            </li>
            <li>
                <a href="#">
                    <img src="images/c1.jpg" alt="" class="small">
                    <img src="images/c.png" alt="" class="big">
                </a>
            </li>
            <li>
                <a href="#">
                    <img src="images/w1.jpg" alt="" class="small">
                    <img src="images/w.png" alt="" class="big">
                </a>
            </li>
            <li>
                <a href="#">
                    <img src="images/z1.jpg" alt="" class="small">
                    <img src="images/z.png" alt="" class="big">
                </a>
            </li>
            <li>
                <a href="#">
                    <img src="images/h1.jpg" alt="" class="small">
                    <img src="images/h.png" alt="" class="big">
                </a>
            </li>
            <li>
                <a href="#">
                    <img src="images/t1.jpg" alt="" class="small">
                    <img src="images/t.png" alt="" class="big">
                </a>
            </li>
        </ul>
    </div>
    <script>
        $(function() {
            // ① 鼠标经过某个小li 有两步操作：
            // ② 当前小li 宽度变为 224px， 同时里面的小图片淡出，大图片淡入
            // ③ 其余兄弟小li宽度变为69px， 小图片淡入， 大图片淡出
            $(".king li").mouseenter(function() {
                $(this).stop().animate({
                    width: 224
                }).find(".small").stop().fadeOut().siblings(".big").stop().fadeIn();
                $(this).siblings("li").stop().animate({
                    width: 69
                }).find(".small").stop().fadeIn().siblings(".big").stop().fadeOut();
            })
        })
    </script>
</body>
```

## `6`- 高亮显示（隔行变色）

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jQuery.min.js"></script>
    <style>
        li {
            font: 22px/30px "simsun";
            cursor: pointer;
            margin: 5px;
            color: brown;
        }
    </style>
</head>
<body>
    <ul>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
        <li>以色侍人，色衰而爱驰也;以才侍人，才进得久，互赏而终...</li>
    </ul>
    <script>
        $(function() {
            fn();
            $("ul li").mouseover(function() {
                fn();
                $("ul li").mouseover(function() {
                    $(this).css("background", "#eee");
                })
            })
        })
        function fn() {
            $("ul li:odd").css("background", "skyblue");
            $("ul li:even").css("background", "hotpink");
        }
    </script>
</body>
```
## `7`- 突出显示

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jquery.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        ul {
            list-style: none;
        }
        body {
            background: #000;
        }
        .wrap {
            width: 630px;
            height: 394px;
            margin: 100px auto 0;
            padding: 10px 0 0 10px;
            border: 1px solid #fff;
        }
        .wrap li {
            float: left;
            margin: 0 10px 10px 0;
        }
        .wrap li img {
            display: block;
        }
    </style>
</head>
<body>
    <div class="wrap">
        <ul>
            <li><a href="#"><img src="images/01.jpg" alt=""/></a></li>
            <li><a href="#"><img src="images/02.jpg" alt=""/></a></li>
            <li><a href="#"><img src="images/03.jpg" alt=""/></a></li>
            <li><a href="#"><img src="images/04.jpg" alt=""/></a></li>
            <li><a href="#"><img src="images/05.jpg" alt=""/></a></li>
            <li><a href="#"><img src="images/06.jpg" alt=""/></a></li>
        </ul>
    </div>
    <script>
        $(function() {
            //需求1：鼠标进入哪个li，当前透明度为1，其他的为0.4;
            $(".wrap li").mouseenter(function() {
                $(this).stop().fadeTo(200, 1).siblings("li").stop().fadeTo(200, .4);
            });
            //需求2：鼠标移开wrap，所有li透明度为1;
            $(".wrap").mouseleave(function() {
                $("li").stop().fadeTo("200", 1);
            })
        })
    </script>
</body>
```

## `8`- 切换盒子背景色

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jquery.min.js"></script>
    <style>
        button {
            width: 100px;
            height: 50px;
            font-size: 22px;
        }
        div {
            width: 300px;
            height: 300px;
            margin: 30px 0;
            background-color: khaki;
        }
        .current {
            background: violet;
        }
    </style>
</head>
<body>
    <button>切换</button>
    <div>
        牡丹虽好空入目，枣花最小结实诚;
    </div>
    <script>
        $(function() {
            $("button").click(function() {
                $("div").toggleClass("current");
            })
        })
    </script>
</body>
```

## `9`- 关闭右下角小广告

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jquery.min.js"></script>
    <style>
        .ad {
            display: none;
            position: fixed;
            right: 0;
            bottom: 0;
            width: 230px;
            height: 120px;
            background-image: url(images/ad.jpg);
        }
        .ad span {
            position: absolute;
            right: 0;
            top: 0;
            width: 40px;
            height: 18px;
            background-image: url(images/h.jpg);
            cursor: pointer;
        }
    </style>
</head>
<body>
    <!--整个广告-->
    <div class="ad">
        <!--关闭按钮-->
        <span></span>
    </div>
    <script>
        $(function() {
            // 需求1：页面加载完毕，ad这个盒子，先滑入在滑出，在淡入;
            $(".ad").slideDown(1000).slideUp(1000).fadeIn(1000);

            //需求2：点击span淡出我们的视野;(隐藏)
            $(".ad span").click(function() {
                $(".ad").fadeOut(200);
            })


            // 链式编程
            $(".ad").slideDown(1000).slideUp(1000).fadeIn(1000).find("span").click(function() {
                $(".ad").fadeOut(200);
            })
        
        })
    </script>
</body>
```

## `10`- jQuery入口函数和顶级对象

- 单选题

    关于jQuery,以下描述正确的是:

```
    A，$(function(){})这种入口函数等同于window.load

    B，$(window).ready(function(){})这种入口函数等同于window.load

    C， jQuery中的入口函数相当于JS中的DOMContentLoaded事件，因此jQuery无法实现window.onload同样的功能

    D， jQuery中的顶级对象$和jQuery是一回事儿
```

答案: D

解析: 选项ABC，都错了，正确写法为\$(window).load()；D选项，是正确的 可以验证 console.log($=== jQuery)