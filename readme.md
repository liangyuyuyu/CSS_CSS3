# [CSS-菜鸟教程](https://www.runoob.com/css/css-tutorial.html)

**CSS 指层叠样式表 (Cascading Style Sheets)**

## css选择符(css选择器)有哪些？

01. 标签选择器 (如：body, div, p, ul, li)
02. 类选择器 (如：class="head", class="head_logo")
03. ID选择器 (如：id="name", id="name_txt")
04. 全局选择器 (如：*号)
05. 组合选择器 (如：.head .head_logo, 注意两选择器用空格键分开)
06. 后代选择器 (如：#head .nav ul li 从父集到子孙集的选择器)
07. 群组选择器 div, span, img {color: Red} 即具有相同样式的标签分组显示
08. 继承选择器 (包含选择器，如：div p, 注意两选择器用空格键分开)
09. 伪类选择器 (如：就是链接样式, a元素的伪类，4种不同的状态：link、visited、active、hover。)
10. 字符串匹配的属性选择符(^ $ *三种，分别对应开始、结尾、包含)
11. 子选择器 (如：div>p , 带大于号>)
12. 相邻选择器 (如：h1+p, 带加号+)
13. 兄弟选择器 ( A~B{...} )

## 多重样式优先级

内联样式(Inline style) > 内部样式(Internal style sheet) > 外部样式(External style sheet) > 浏览器默认样式

优先级逐级降低的选择器列表：

01. !important （尽量少用，会破坏样式表的级联规则）
02. 内联样式
03. ID选择器（ID selector，IS）

``` html
<style>
    #name {
        color: red;
    }
</style>
<!--下面文字是红色的-->
<p id="name">red text</p>
```

04. 伪类
05. 属性选择器（element selector，ES）：没有得到所有浏览器支持
06. 类选择器（class selector，CS）

``` html
<style>
    .value {
        text-align: center;
    }
</style>
<!--下面的文字是居中对齐的-->
<p class="value">center text</p>
```

07. 元素(类型)选择器（element selector，ES）

``` html
<style>
    p {
        font-style: italic;
    }
</style>
<!--下面的文字是斜体的-->
<p style="font-style:italic">italic text</p>
```

08. 通用选择器（*）

``` html
<!--使用html中任意标签元素字体颜色全部设置为红色：-->
<style>

    - {

        color: red;
    }
</style>

<body>
    <h1>标题为红色</h1>
    <p>段落也为红色</p>
</body>
```

## CSS 背景

| 属性 | 描述 |
| :- | :- |
|background|简写属性，作用是将背景属性设置在一个声明中|
|background-attachment|背景图像是否固定或者随着页面的其余部分滚动|
|background-color|设置元素的背景颜色|
|background-image|把图像设置为背景|
|background-position|设置背景图像的起始位置|
|background-repeat|设置背景图像是否及如何重复|

``` html
<style>
    html {
        width: 100%;
        height: 100%;
    }

    body {
        background-color: #b0c4de;
        background-image: url('assets/images/pic1.jpg');
        /* 
                no-repeat：不平铺 
                repeat-x：延x轴方向平铺
                repeat-y：延y轴方向平铺
                repeat：延x、y轴方向平铺
                space：界面左右显示一个 
            */
        background-repeat: no-repeat;
        /* background-position 属性改变图像在背景中的位置 x y */
        background-position: right top;
        /* 背景大小 width height*/
        background-size: 100% 100%;
        /* 设置背景图像是否固定或者随着页面的其余部分滚动 flexed：固定，scroll：滚动 */
        background-attachment: scroll;
    }

    /* 背景简写 */
    /* body {
            background: #b0c4de url('assets/images/pic2.png') no-repeat right top 100% 100%;
        } */
</style>
```

## CSS 文本格式

### 文本的对齐方式 text-align

| 值 | 描述 |
| :- | :- |
|left|	把文本排列到左边。默认值：由浏览器决定|
|right|把文本排列到右边|
|center|把文本排列到中间|
|justify|实现两端对齐文本效果|
|inherit|规定应该从父元素继承 text-align 属性的值|

``` html
<style>
    h1 {
        text-align: center;
    }

    p.date {
        text-align: right;
    }

    p.main {
        text-align: justify;
    }
</style>

<h1>CSS text-align 实例</h1>
<p class="date">2015 年 3 月 14 号</p>
<p class="main">
    “当我年轻的时候，我梦想改变这个世界；当我成熟以后，我发现我不能够改变这个世界，我将目光缩短了些，决定只改变我的国家；当我进入暮年以后，我发现我不能够改变我们的国家，我的最后愿望仅仅是改变一下我的家庭，但是，这也不可能。当我现在躺在床上，行将就木时，我突然意识到：如果一开始我仅仅去改变我自己，然后，我可能改变我的家庭；在家人的帮助和鼓励下，我可能为国家做一些事情；然后，谁知道呢?我甚至可能改变这个世界。”
</p>
```

### 文本修饰 text-decoration

text-decoration 属性用来设置或删除文本的装饰。

从设计的角度看text-decoration属性主要是用来删除链接的下划线：

``` html
<style>
    a {
        text-decoration: none;
    }
</style>

链接到: <a href="//www.runoob.com/">runoob.com</a>
```

也可以这样装饰文字：

``` html
<style>
    h1 {
        text-decoration: overline;
    }

    h2 {
        text-decoration: line-through;
    }

    h3 {
        text-decoration: underline;
    }
</style>

<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<h3>This is heading 3</h3>
```

### 文本转换 text-transform

* 文本转换属性：用来指定在一个文本中的大写和小写字母。
* 作用：可用于所有字句变成大写、小写字母、每个单词的首字母大写。

``` html
<style>
    p.uppercase {
        text-transform: uppercase;
    }

    p.lowercase {
        text-transform: lowercase;
    }

    p.capitalize {
        text-transform: capitalize;
    }
</style>

<p class="uppercase">This is some text.</p>
<p class="lowercase">This is some text.</p>
<p class="capitalize">This is some text.</p>
```

### 文本缩进 text-indent
* 文本缩进属性：用来指定文本的第一行的缩进。
``` html
<style>
    p {
        text-indent: 20px;
    }
</style>

<p>In my younger and more vulnerable years my father gave me some advice that I've been turning over in my mind ever since. 'Whenever you feel like criticizing anyone,' he told me, 'just remember that all the people in this world haven't had the advantages that you've had.'</p>
```

---
***

# 这是一级标题

## 这是二级标题

### 这是三级标题

#### 这是四级标题

##### 这是五级标题

###### 这是六级标题

这是一级标题
= 
这是二级标题
- 

# 这是一级标题 #

## 这是二级标题 ##

### 这是三级标题 ###

#### 这是四级标题 ####

##### 这是五级标题 #####

###### 这是六级标题 ######

* **这是加粗的文字**
* *这是倾斜的文字*`
* ***这是斜体加粗的文字***
* ~~这是加删除线的文字~~

* 不以结婚为目的谈恋爱，都是耍牛氓！

  > - 这是一级引用的内容
  > - 这是一级引用的内容
- 
+ 

>> 这是二级引用的内容

- 
+ 

>>> 这是三级引用的内容

- 
* 

* 一级无序列表内容

   * 二级无序列表内容
   * 二级无序列表内容
   * 二级无序列表内容

* 一级无序列表内容

   1. 二级无序列表内容
   2. 二级无序列表内容
   3. 二级无序列表内容
   4. 二级无序列表内容
   5. 二级无序列表内容

| 表头 | 表头 | 表头 |
| :- | :-: | -: |
|第一行|第一行|第一行|
|第二行|第二行|第二行|
|第三行|第三行|第三行|

`代码内容` 

``` 
代码内容
```

![图片alt](https://www.baidu.com/img/baidu_jgylogo3.gif)

