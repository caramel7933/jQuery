## `1`- 旋转木马

- 训练目标

  综合练习，使用jQuery解决复杂需求逻辑

- 训练提示

  1.5张图片位置信息设置为一个数组，数组中有五组数据

  2.页面加载的时候，五张照片分别设置为数组中的样式

  3.点击左右两侧按钮，改变数组中样式的位置，重新加载

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="css/demo.css">
    <script src="js/jQuery.min.js"></script>
    <script src="js/demo.js"></script>
</head>
<body>
    <div class="wrap" id="wrap">
        <div class="slide" id="slide">
            <ul>
                <li><a href="#"><img src="images/slidepic1.jpg" alt=""/></a></li>
                <li><a href="#"><img src="images/slidepic2.jpg" alt=""/></a></li>
                <li><a href="#"><img src="images/slidepic3.jpg" alt=""/></a></li>
                <li><a href="#"><img src="images/slidepic4.jpg" alt=""/></a></li>
                <li><a href="#"><img src="images/slidepic5.jpg" alt=""/></a></li>
            </ul>
            <div class="arrow" id="arrow">
                <a href="javascript:;" class="prev"></a>
                <a href="javascript:;" class="next"></a>
            </div>
        </div>
     </div>
</body>
</html>
```

```css
@charset "UTF-8";
/*初始化  reset*/
blockquote,body,button,dd,dl,dt,fieldset,form,h1,h2,h3,h4,h5,h6,hr,input,legend,li,ol,p,pre,td,textarea,th,ul{margin:0;padding:0}
body,button,input,select,textarea{font:12px/1.5 "Microsoft YaHei", "微软雅黑", SimSun, "宋体", sans-serif;color: #666;}
ol,ul{list-style:none}
a{text-decoration:none}
fieldset,img{border:0;vertical-align:top;}
a,input,button,select,textarea{outline:none;}
a,button{cursor:pointer;}

.wrap{
    width:1200px;
    margin:10px auto;
}
.slide {
    position: relative;
    height:500px;
}
.slide li{
    position: absolute;
    top:0;
    left:200px;
}
.slide li img{
    width:100%;
}
.arrow{
    opacity: 0;
}
.prev,.next{
    position: absolute;
    width:76px;
    height:112px;
    top:50%;
    margin-top:-56px;
    background: url(../images/prev.png) no-repeat;
    z-index: 99;
}
.next{
    right:0;
    background-image: url(../images/next.png);
}
```

```js
$(function() {
    var arrOfJson = [
        {   //  1
            width:400,
            top:70,
            left:50,
            opacity: 0.2,
            "z-index":2
        },
        {  // 2
            width:600,
            top:120,
            left:0,
            opacity: 0.8,
            "z-index":3
        },
        {   // 3
            width:800,
            top:100,
            left:200,
            opacity: 1,
            "z-index":4
        },
        {  // 4
            width:600,
            top:120,
            left:600,
            opacity:0.8,
            "z-index":3
        },
        {   //5
            width:400,
            top:70,
            left:750,
            opacity: 0.2,
            "z-index":2
        },
    ];
    //需求1：页面加载的时候所有li标签按照arrOfJson中的样式滑动过去;
    $("#slide li").each(function(index, domEle) {
        $(domEle).css("z-index",arrOfJson[index]["z-index"]);
        $(domEle).animate(arrOfJson[index], 1000);
    });

    // 鼠标经过箭头显示隐藏
    $("#wrap").hover(function() {
        $("#arrow").fadeTo(100,1);
    }, function() {
        $("#arrow").fadeTo(100,0);
    });

    var bool = true;  // 节流阀

    //需求2：点击右侧按钮，删除数组中的第一个，添加到最末尾;
    $(".next").click(function() {
        if (bool) {
            bool = false;
            var first = arrOfJson.shift();
            arrOfJson.push(first);
            $("#slide li").each(function(index, domEle) {
                $(domEle).css("z-index",arrOfJson[index]["z-index"]);
                $(domEle).animate(arrOfJson[index], 1000, function() {
                    bool = true;
                });
            });
        };
    });

    //需求3：点击左侧按钮，删除数组中的最后一个，添加到最前面;
    $(".prev").click(function() {
        var last = arrOfJson.pop();
        arrOfJson.unshift(last);
        $("#slide li").each(function(index, domEle)  {
            $(domEle).css("z-index",arrOfJson[index]["z-index"]);
            $(domEle).animate(arrOfJson[index], 1000);
        });
    });
})
```

## `2`- jQuery 事件注册

- 单选题

    关于jQuery事件事件注册,以下描述正确的是:

```
    A，点击事件绑定，jQuery中仅有 click() 一种绑定形式

    B，jQuery中的click()，不会出现事件逻辑覆盖

    C，jQuery中的click()，一定会出现事件逻辑覆盖

    D，以上答案均不正确
```

答案: B

解析: 

A选项，除了click()还有bind() / delegate() / on() 方法，都可以绑定click事件

C选项，click() 不会出现事件逻辑覆盖

## `3`- jQuery 拷贝对象

- 多选题

    以下说法，正确的是：

```
    A，jQuery中的可以使用$.extend()实现对象拷贝

    B，$.extend()的第一个参数为复制的时候选择深层还是浅层复制，深层复制则属性中的复杂数据类型会被重新创建一份儿

    C，$.extend()的第二个参数开始是将要拷贝的对象，未来即将被合并

    D，$.extend()的最后一个参数是合并的目标对象，所有合并的对象信息都会出现在这个对象当中。
```

答案: AB

解析: 

CD选项: 解释错误，说法反了正确说法为：

​$.extend()的第二个参数是合并的目标对象，所有合并的对象信息都会出现在这个对象当中

$.extend()的最后一个参数是将要拷贝的对象，未来即将被合并

## `4`- jQuery 多库共存

- 单选题

```
    下列 jQuery 方法，描述正确的是：

    A，一个项目中，无法同时使用多个版本的jQuery

    B，jQuery的顶级对象只能使用jQuery或者$，无法进行修改

    C，$.noConflict()或者jQuery.noConflict()可以实现jQuery的多库共存

    D，一个项目，没有同时存在多个版本的jQuery的必要
```

答案: C

解析: 

AB选项，jQuery是可以多库共存的，也就是可以同时存在多个jQuery版本，且顶级对象可以自定义

D选项，一个项目中同时存在多个版本的jQuery就可以使用不同版本jQuery的特性，是有必要的，且大型项目开发存在遗留问题，非常容易出现多库共存


## `5`- jQuery 插件

- 单选题

    下列有关jQuery插件的说法正确的是：

```
    A，jQuery的插件机制没用，没必要使用插件

    B，jQuery的插件使用本质就是: 使用别人已经写好的代码复制html 、 css、js，调整必要的参数就可以实现很强大的功能

    C，bootstrap是一个开源框架，可以不依赖jQuery独立运行，所以不包含所谓的插件

    D，以上答案均正确
```

答案：B

解析：

A选项，jQuery插件是jQuery非常强大的组成部分，很多插件可以直接在项目中修改并使用

D选项，bootstrap是基于jQuery实现的框架，包含很多插件

## `6`- 代码题

- 单选题

    运行下面代码，点击li标签后，正确的输出结果是：

```html
<body>
  	<ul>
        <li>我是原生土著li1</li>
        <li>我是原生土著li2</li>
        <li>我是原生土著li3</li>
        <li>我是原生土著li4</li>
        <li>我是原生土著li5</li>
    </ul>

	<script>
        $(function () {
            $("li").on("click",fn1)
            $("li").on("click",fn2)
            $("li").on("click",fn3)

            $("li").off("click",fn2);

            //总结：怎么绑定的事件怎么解绑;(一把钥匙开一把锁)

            function fn1(){
                console.log(111);
            }
            function fn2(){
                console.log(222);
            }
            function fn3(){
                console.log(333);
            }
        });
    </script>
</body>
```

```
    A，111 和 222

    B，111 和 333

    C，222和 333

    D，无任何输出
```

答案：B

解析：

B选项，off只是解绑了 fn2 逻辑，所以点击li后，fn1和fn3的逻辑依然会执行