## `1`- jQuery对象和DOM对象

- 单选题

    关于获取元素,以下获取到单个元素的方法是:

```
    A，jQuery对象就是DOM对象

    B，jQuery对象可以转换为DOM对象，但是DOM对象无法转换为jQuery对象

    C， jQuery对象转换为DOM对象的方法有两种：jQuery对象[索引值]和jQuery对象.get(索引值)

    D， DOM对象转换成jQuery对象的方法有一种：$(DOM对象)[0]
```

答案: C

解析: 

​	A选项，jQuery对象和DOM对象不一样

​	B选项，jQuery对象和DOM对象可以相互转换

​	D选项，后面多出来一部分：[0]

## `2`- jQuery选择器

- 多选题

    关于获取元素,以下获取到"目标元素"所在a链接的有:

```html
    <div>
        <ul>
            <li>
    	        <a href='#' class='aaa' id='ccc'>皮鞋</a>
            </li>
            <li>
    	        <a href='#' class='bbb' id='bbb'>帽子</a>
            </li>
            <li>
    	        <a href='#' class='ccc' id='aaa'>目标元素</a>
            </li>
        </ul>
    </div>
```

```
    A，$('ul li a:eq(3)')

    B，$('ccc')

    C，$('#aaa')

    D，$('a:last')
```

答案: CD

解析: A选项索引值应该为 2 ; B选项类名前应该加点

## `3`- jQuery样式操作

- 多选题

    以下说法，正确的是：

```
    A，css() 既可以获取属性值，也可以设置属性值

    B，css() 有两种设置属性值方式，一种是传递两个参数 第一个属性，第二个值；第二种可以传递一个对象，对象中属性和值以键值对形式存在

    C，jQuery中有三种常见的类操作方法：addClass() / removeClass() / toggleClass();

    D，addClass()不会像原生js中的className属性一样覆盖原有的属性值
```

答案: ABCD

解析: 全部正确

## `4`- jQuery动画效果

- 多选题

    关于动画效果，下列描述正确的是：

```
    A，show()和hide()所能完成的效果，toggle()可以切换完成

    B，slideDown()和slideUp()和slideToggle()可以设置动画完成时间

    C，fadeIn()和fadeOut()和fadeToggle()和fadeTo()是可以设置回调函数的，于动画完成后执行

    D，以上说法至少有一项是错误的
```

答案: ABC

解析: ABC均正确，则D错误

## `5`- jQuery自定义动画

- 多选题

    关于自定义动画，说法正确的是：

```
    A，自定义动画可以设置4个参数分别为：样式，时间，动画类型，回调函数

    B，animate()中，除了样式其他参数都可以省略或自带默认值 

    C，回调函数的执行，是在所有样式全部达到目标值后才执行的

    D，animate()可以模拟显示隐藏、滑入滑出、淡入淡出等动画，使用原则为哪个方便用哪个
```

答案：ABCD

解析：全部正确

## `6`- 综合题

- 多选题

    下列说法，错误的是：

```
    A，链式编程和隐式迭代是 jQuery 的两大优点，能够达到快速开发的目的

    B，stop() 用于停止动画队列，设置动画之前可先停止动画排队，这样可以避免动画堆积

    C，有了 hover() 事件，就没有必要再使用 mouseenter() / mouseleave() 了

    D，利用 jQuery 实现排他思想的思路是: 先统一设置所有元素的样式，然后找出特殊的单独处理
```

答案：CD

解析：AB选项为正确选项。

C选项错误在hover() 如果只传递一个函数那么鼠标进入和移出都执行同一个函数，没有两个事件单独写灵活，且有些复杂逻辑，可能只需要绑定某一个特定事件

D选项错误在于，jQuery实现排他思想是特殊元素特殊处理，其他兄弟元素单独处理

## `7`- 全选案例

- 题目描述

    全选案例，模拟购物车模块中的全选需求：

    1）点击上面的全选，下面全部选中

    2）下面的input如果全部选中，上面的input同步选中

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jQuery.min.js"></script>
    <style>
        * {
            padding: 0;
            margin: 0;
        }
        .wrap {
            width: 300px;
            margin: 100px auto 0;
        }
        table {
            border-collapse: collapse;
            border-spacing: 0;
            border: 1px solid #c0c0c0;
        }
        th,
        td {
            border: 1px solid #d0d0d0;
            color: #404060;
            padding: 10px;
        }
        th {
            background-color: #09c;
            font: bold 16px "微软雅黑";
            color: #fff;
        }
        td {
            font: 14px "微软雅黑";
        }
        tbody tr {
            background-color: #f0f0f0;
        }
        tbody tr:hover {
            cursor: pointer;
            background-color: #fafafa;
        }
    </style>
</head>
<body>
    <div class="wrap">
        <table>
            <thead>
                <tr>
                    <th>
                        <input type="checkbox" id="j_cbAll">
                    </th>
                    <th>课程名称</th>
                    <th>所属学院</th>
                </tr>
            </thead>
            <tbody id="j_tb">
                <tr>
                    <td>
                        <input type="checkbox"/>
                    </td>
                    <td>JavaScript</td>
                    <td>前端与移动开发学院</td>
                </tr>
                <tr>
                    <td>
                        <input type="checkbox"/>
                    </td>
                    <td>css</td>
                    <td>前端与移动开发学院</td>
                </tr>
                <tr>
                    <td>
                        <input type="checkbox"/>
                    </td>
                    <td>html</td>
                    <td>前端与移动开发学院</td>
                </tr>
                <tr>
                    <td>
                        <input type="checkbox"/>
                    </td>
                    <td>jQuery</td>
                    <td>前端与移动开发学院</td>
                </tr>
                <tr>
                    <td>
                        <input type="checkbox"/>
                    </td>
                    <td>HTML5</td>
                    <td>前端与移动开发学院</td>
                </tr>
                <tr>
                    <td>
                        <input type="checkbox"/>
                    </td>
                    <td>CSS3</td>
                    <td>前端与移动开发学院</td>
                </tr>
            </tbody>
        </table>
    </div>
    <script>
        $(function() {
            //需求1: 点击上面的input，下面所有input的checked和上面的保持一致;
            $("#j_cbAll").change(function() {
                $("#j_tb input").prop("checked", $(this).prop("checked"));
            })
            //需求2: 点击下面的每一个input，下面所有input被选中的个数为6个上面才被选中，否则不被选中;
            $("#j_tb input").change(function() {
                if ($("#j_tb input:checked").length === $("#j_tb input").length) {
                    $("#j_cbAll").prop("checked", true);
                } else {
                    $("#j_cbAll").prop("checked", false);
                }
            })
        })
    </script>
</body>
```

## `8`- 移动选项

- 题目描述

    点击左右移动按钮，选中项移动到另一侧

- 训练目标

  能够获取元素，添加元素

- 训练提示

  1.把一侧的所有元素，添加到另一侧

  2.把一侧的所有选中元素，添加到另一侧

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jQuery.min.js"></script>
    <style>
        select {
            width: 200px;
            height: 300px;
            font-size: 22px;
            color: #fff;
            background-color: darkorange;
        }
    </style>
</head>
<body>
    <select name="" id="sel1" size="4" multiple>
        <option value="">香蕉</option>
        <option value="">大鸭梨</option>
        <option value="">苹果</option>
        <option value="">大西瓜</option>
    </select>

    <button>&gt;&gt;&gt;</button>
    <button>&lt;&lt;&lt;</button>
    <button>&gt;</button>
    <button>&lt;</button>

    <select name="" id="sel2" size="4" multiple>

    </select>

    <script>
        $(function() {
            //需求1：点击前两个按钮，一侧的所有option移动到另一侧的select标签中;
            $("button").eq(0).click(function() {
                //左侧所有option全部移动到右侧select中(不用for循环)
                // $("#sel2").append($("#sel1 option"));
                fn("#sel2", "#sel1 option");
            });
            $("button").eq(1).click(function() {
                //右侧所有option全部移动到左侧select中(不用for循环)
                // $("#sel1").append($("#sel2 option"));
                fn("#sel1", "#sel2 option");
            });

             //需求2：点击后两个按钮，一侧的所有option中"被选中"的全部移动到另一侧的select标签中;
             $("button").eq(2).click(function() {
                // $("#sel1 option:selected").append("#sel2");
                fn("#sel1 option:selected", "#sel2");
             });
             $("button").eq(3).click(function() {
                // $("#sel2 option:selected").append("#sel1");
                fn("#sel2 option:selected", "#sel1");
             });

             //优化封装
            function fn(str1,str2) {
               //右侧所有option全部移动到左侧select中(不用for循环)
               $(str1).append($(str2));
            }
        })
    </script>
</body>
```

## `9`- 动态输入

- 题目描述

    点击添加能够添加选项，点击GET能够删除选项

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jQuery.min.js"></script>
    <style>
        * {
            padding: 0;
            margin: 0;
        }
        .wrap {
            width: 410px;
            margin: 100px auto 0;
        }
        table {
            border-collapse: collapse;
            border-spacing: 0;
            border: 1px solid #c0c0c0;
        }
        th,
        td {
            border: 1px solid #d0d0d0;
            color: #404060;
            padding: 10px;
        }
        th {
            background-color: #09c;
            font: bold 16px "微软雅黑";
            color: #fff;
        }
        td {
            font: 14px "微软雅黑";
        }
        td a.get {
            text-decoration: none;
        }
        tbody tr {
            background-color: #f0f0f0;
        }
        tbody tr:hover {
            cursor: pointer;
            background-color: #fafafa;
        }
        .btnAdd {
            width: 110px;
            height: 30px;
            font-size: 20px;
            font-weight: bold;
        }
        .form-item {
            position: relative;
            height: 100%;
            line-height: 36px;
            padding-left: 100px;
            padding-right: 20px;
            margin-bottom: 34px;
        }
        .form-item .lb {
            display: block;
            position: absolute;
            left: 0;
            top: 0;
            width: 100px;
            text-align: right;
        }
        .form-item .txt {
            width: 300px;
            height: 32px;
        }
        .mask {
            display: none;
            position: absolute;
            top: 0px;
            left: 0px;
            width: 100%;
            height: 100%;
            background: #000;
            opacity: 0.8;
        }
        .form-add {
            position: fixed;
            top: 30%;
            left: 50%;
            margin-left: -197px;
            padding-bottom: 20px;
            background: #fff;
            display: none;
        }
        .form-add-title {
            position: relative;
            background-color: #f7f7f7;
            border-width: 1px 1px 0 1px;
            border-bottom: 0;
            margin-bottom: 15px;
        }
        .form-add-title span {
            display: block;
            width: auto;
            height: 18px;
            padding: 8px 0px 10px;
            margin-right: 10px;
            font-size: 16px;
            font-family: 宋体;
            font-weight: bold;
            color: rgb(102, 102, 102);
            text-indent: 12px;
            text-align: left;
            overflow: hidden;
        }
        .form-add-title div {
            position: absolute;
            right: 10px;
            top: 6px;
            width: 16px;
            height: 20px;
            font-size: 30px;
            line-height: 16px;
            cursor: pointer;
        }
        .form-submit {
            text-align: center;
        }
        .form-submit input {
            width: 170px;
            height: 32px;
        }
    </style>
</head>
<body>
    <div class="wrap">
        <div>
            <input type="button" value="添加数据" id="j_btnAddData" class="btnAdd">
        </div>
        <table>
            <thead>
                <tr>
                    <th>课程名称</th>
                    <th>所属学院</th>
                    <th>已学会</th>
                </tr>
            </thead>
            <tbody id="j_tb">
                <tr>
                    <td>JavaScript</td>
                    <td>前端与移动开发学院</td>
                    <td><a href="javascrip:;" class="get">GET</a></td>
                </tr>
                <tr>
                    <td>css</td>
                    <td>前端与移动开发学院</td>
                    <td><a href="javascrip:;" class="get">GET</a></td>
                </tr>
                <tr>
                    <td>html</td>
                    <td>前端与移动开发学院</td>
                    <td><a href="javascrip:;" class="get">GET</a></td>
                </tr>
                <tr>
                    <td>jQuery</td>
                    <td>前端与移动开发学院</td>
                    <td><a href="javascrip:;" class="get">GET</a></td>
                </tr>
            </tbody>
        </table>
    </div>
    <div id="j_mask" class="mask"></div>
    <div id="j_formAdd" class="form-add">
        <div class="form-add-title">
            <span>添加数据</span>

            <div id="j_hideFormAdd">x</div>
        </div>
        <div class="form-item">
            <label class="lb" for="j_txtLesson">课程名称：</label>
            <input class="txt" type="text" id="j_txtLesson" placeholder="请输入课程名称" required>
        </div>
        <div class="form-item">
            <label class="lb" for="j_txtBelSch">所属学院：</label>
            <input class="txt" type="text" id="j_txtBelSch" value="前端中的黄埔军校">
        </div>
        <div class="form-submit">
            <input type="button" value="添加" id="j_btnAdd">
        </div>
    </div>
    <script>
        $(function() {
            //需求1：点击j_btnAddData，显示 mask和 form表单;
             $("#j_btnAddData").click(showOrHide);
            //需求2：点击j_hideFormAdd，隐藏mask和form表单;
            $("#j_hideFormAdd").click(showOrHide);
            //需求3：点击j_btnAdd，添加一个tr到tbody中;
            $("#j_btnAdd").on("click", function() {
            //获取两个input里面的值，往tr里面的td中设置内容;  
                var val1 = $("#j_txtLesson").val();       
                var val2 = $("#j_txtBelSch").val();
                // 如果两个值为空字符串或者空格，不能添加;
                if (val1 == "" || val2 == "") {
                    alert("内容不能为空！");
                    $("#j_txtLesson").val("");
                    $("#j_txtBelSch").val("前端中的黄埔军校");
                    return false;
                }
                var tr = $("<tr></tr>");
                var str = "<td>"+  val1 +"</td>" + "<td>"+ val2 +"</td>" + "<td> <a     href='javascript:;' class='get'>GET</a> </td>";
                tr.html(str);
                //添加到tbody中
                $("#j_tb").append(tr);
                // 添加完数据，隐藏两个盒子
                showOrHide();
                // 初始化值，第一个清空，第二个默认值
                $("#j_txtLesson").val("");
                $("#j_txtBelSch").val("前端中的黄埔军校");
            });
            //需求4：点击a.get，删除他所在的tr;
           $("#j_tb").on("click",".get", function () {
               $(this).parents("tr").remove();
           })
        })

        // 显示和隐藏函数
        function showOrHide() {
            $("#j_mask").toggle();
            $("#j_formAdd").toggle();
        }
    </script>
</body>
```

## `10`- 固定顶部导航栏

- 训练目标

    能够获取元素尺寸，获取页面被卷去的部分，能够设置样式

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="jQuery.min.js"></script>
    <style>
        * {
            padding: 0;
            margin: 0;
        }
        img {
            vertical-align: top;
        }
        .top {
            width: 1500px;
            margin: 0 auto;
        }
        #Q-nav {
            width: 1500px;
            margin: 0 auto;
            overflow: hidden;
        }
        .main {
            width: 1000px;
            margin: 0 auto;
        }
    </style>
</head>
<body>
    <!--第一张图片-->
    <div class="top" id="top">
        <img src="top.png" alt=""/>
    </div>
    <!--第二张图片-->
    <div id="Q-nav">
        <img src="nav.png" alt=""/>
    </div>
    <!--第三张图片-->
    <div class="main" id="main">
        <img src="main.png" alt=""/>
    </div>
    <script>
        $(function() {
            //需求：页面滚动，如果被卷去的头部超过第一个盒子的高，给第二个盒子加固定定位，第三个盒子加上padding;
            $(window).on("scroll", function() {
                //判断：页面被卷去的顶部的高
                if($(window).scrollTop() >= $("#top").height()) {
                    //第二个盒子加定位，第三个盒子加padding;
                    var json = {
                        position: 'fixed',
                        top: 0,
                        left: '50%',
                        'margin-left': -$("#Q-nav").width() / 2,
                        'margin': '0, auto'
                    };
                    $("#Q-nav").css(json);
                    $("#main").css("padding-top",$("#Q-nav").height());                
                } else {
                    var json = {
                        position: 'static',
                        top: 0,
                        left: 0,
                        width: '1500px',
                        margin: '0 auto'
                    };
                    $("#Q-nav").css(json);
                    $("#main").css("padding-top",0);
                }
            })
        })
    </script>
</body>
```