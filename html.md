# 前端学习

## html

### vscode使用

1.新建文件 Ctrl + N 

2.保存 Ctrl + S

3.Ctrl + + - - 字体加大减小

输入！号建立骨架

```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title></title>
</head>

<body>

</body>

</html>
```



<!DOCTYPE>文档类型声明 告诉游览器使用哪种HTML版本来显示网页

注意：必须位于文档最前面 不是一个HTML标签

<html lang="en"> 告诉游览器或者搜索引擎这是哥英文网站，本页面采取英文显示

<meta charset="UTF-8">必须写，采取 UTF-8来保存文字，不写就好乱码
### HTML常用标签

标题标签<h1>--<h6> 作为标题使用，每个标题加粗，独占一行

段落标签 <p></p> 

换行标签<br />

#### 文本格式化标签 

突出重要性，比平台文字更重要

| 语义   | 标签                      | 说明                   |
| :----- | ------------------------- | ---------------------- |
| 加粗*  | <strong></strong> <b></b> | 推荐strong，语义更强烈 |
| 倾斜*  | <em></em> <i></i>         | 推荐em                 |
| 删除线 | <del></del> <s></s>       | 推荐del                |
| 下划线 | <ins></ins> <u></u>       | 推荐ins                |

<div和<span没有语义就是盒子，用来装内容

</div>标签用来布局，但是一行只能放一个，大盒子

<span 小盒子，一行多个

#### 图像标签

1. <img> 用于定义图像

   <img src="图像URL" alt=" ”/>  

| 属性   | 属性值   | 说明                                    |
| ------ | -------- | --------------------------------------- |
| src    | 图片路径 | 用于指定图像文件的路径和文件名          |
| alt    | 文本     | 替换文本 图像显示不出来的时候用为你替换 |
| title  | 文本     | 提示文本 鼠标放到图像上提示的文字       |
| width  | 像素     | 设置图像宽度                            |
| height | 像素     | 设置图像高度                            |
| border | 像素     | 设置图像边框粗细                        |

注意1.可以拥有多个属性，必须在标签名后面。

​		2.属性之间不分先后顺序，标签名与属性，属性与属性之间均以空格分开

​		3.属性采取键值对的格式，即key='value'的格式，属性=’属性值‘

##### 相对路径

：以引用文件位置作为参考建立的路径。

| 相对路径   | 符号 | 说明                                                       |
| ---------- | ---- | ---------------------------------------------------------- |
| 同一级路径 |      | 图像文件位于HTML文件同一级 如<img src="baidu.gif"/>        |
| 下一级路径 | /    | 图像文件位于HTML文件下一级 如<img src="images/baidu.gif"/> |
| 上一级路径 | ../  | 图像文件位于HTML文件上一级 如<img src=""../baidu.gif />    |

绝对路径：目录下的绝对路径

#### 超链接标签<a>

格式：<a href="跳转目标" target="目标窗口的弹出方式",> 文本或图像 </a>

| 属性   | 作用                                                         |
| ------ | ------------------------------------------------------------ |
| href   | 用于指定链接目标的url地址，必须属性，当为标签应用href属性时，它具有超链接功能  如果是文件 就下载。 |
| target | 用于指定链接页面的打开方式，_self为默认值，_blank为在新窗口中打开方式 |

锚点链接：定位

在链接文本的href属性中，设置属性值为#名字的形式，如<a href="#two" >第二集 </a

找到目标位置标签，里面添加一个id属性=刚才的名字。如：<h3 id = "two">第二集介绍</h3

注释标签和特殊字符

注释：<!-- 注释语句--> 快捷键 ctrl + /

#### 特殊字符

![image-20220908153016791](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220908153016791.png)

#### 表格标签

</table>是用于定义表格的标签

</tr> 标签用于定义表格中的单元格，必须嵌套在table中

</td> 用于定义表格中的单元格，必须嵌套在tr

字母td指表格数据，即数据单元格内容

</th>表头单元格 位于第一行或者第一列，表头单元格文本加粗居中显示

| 属性名       | 属性值              | 描述                                             |
| ------------ | ------------------- | ------------------------------------------------ |
| align        | left、center、right | 规定表格相对周围元素的对齐方式                   |
| border       | 1或“ ”              | 规定表格单元是否拥有边框，默认为“”，表示没有边框 |
| celllpadding | 像素值              | 规定单元边沿与其内容之间的空白，默认1像素        |
| cellspacing  | 像素值              | 规定单元格之间的空白，默认为2像素                |
| width        | 像素值或百分比      | 规定表格宽度                                     |

##### 表格结构标签

<thead 头部区域 内部必须有<tr标签 一般位于第一行

<tbody 主体区域 用于放数据本体

以上两个标签都放在table'

合并单元格

跨行合并：rowspan=“合并单元格个数”

跨列合并：colspan=“合并单元格个数”

目标单元格

跨行：上侧

跨列：左侧

合并后删除多余单元格

#### 列表标签

##### 无序列表

ul 列表项使用<li 标签定义 没有顺序是并列的 ul里面只能放li li里面可以放任何标签

##### 有序标签

ol 里面只能放li标签

##### 自定义列表

用于术语，名词的解释和描述，没有任何项目符号

<dl> 标签用于定义描述列表，该标签会与<dt>(定义项目/名字)和<dd>(描述每一个项目/名字)一起使用

#### 表单标签

表单通常由表单域，表单控件和提示信息

##### 表单域

 <form>用于定义表单域 接受表单元素信息提供给服务器

```
<form action="ulr地址" method="提交方式" name=“表单域名称”>
	各种表单元素控件
</form>
```

| 属性   | 属性值   | 作用                                            |
| ------ | -------- | ----------------------------------------------- |
| action | url地址  | 用于指定接受并处理表单数据的服务器程序的url地址 |
| method | get/post | 用于设置表单数据的提交方式，其取值为get或post。 |
| name   | 名称     | 用于指定表单的名称，以区分同一页面的多个表单域  |

##### 表单控件(表单元素)

###### <input

```
<input type="属性值"  />
```

| 属性值   | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| button   | 定义可点击按钮 通过JavaScript启动脚本                        |
| checkbox | 定义复选框                                                   |
| file     | 定义输入字段和浏览按钮，供文件上传                           |
| hidden   | 定义隐藏的输入字段                                           |
| image    | 定义图像形式的提交按钮                                       |
| password | 定义密码字段，该字段中的字符被掩码                           |
| radio    | 定义单选按钮                                                 |
| reset    | 定义重置按钮，重置按钮会清楚表单中的索引数据                 |
| submit   | 定义提交按钮。提交按钮会把表单数据发送到服务器               |
| text     | 定义单行的输入字段，用户可在其中输入文本，默认宽度为20个字符。 |

| 属性      | 属性值       | 描述                                |
| --------- | ------------ | ----------------------------------- |
| name      | 由用户自定义 | 定义input元素的名称                 |
| value     | 由用户自定义 | 规定input元素的值                   |
| checked   | checked      | 规定此input元素收藏加载时应当被选中 |
| maxlength | 正整数       | 规定输入字段中的字符的最大长度      |

<input> 其他属性

1.name和value是每个表单元素都有的属性值，主要给后台人员使用

2.name表单元素的名字，要求单选框和复选框都要由相同的name值

######  <label标签

input元素定义标注

用于绑定一个表单元素，当点击标签内文本时，游览器会自动将焦点转到或选择对应的表单元素上，用来增加用户体验

```
<label for='sex'>男</label>
<input type="radio" name="sex" id="sex" />
```

###### select下拉表单

```
<select>
	<option>选项1</option>
	<option>选项2</option>
</select
```

1.至少包含一堆option

2.option中定义selected = ’selected‘时，当前项为默认选中项

###### textarea文本域

多行文本输入控件

```
<textarea rows='3' cos='20'>
	文本内容
</textarea>
cols每行的字符数
rows显示的行数
```



## CSS

CSS：选择器以及一条和多条声明

基础选择器

选择器分为基础选择器和复合选择器

标签选择器：设置某一类标签同一样式

类选择器：单独选择一个或者几个标签

```
.类名 {
	属性1： 属性值1
}
<p class='类名'> wadad </p>
```

多类名 可以写多个类名 用空格隔开

id选择器

```
#id名 {
	属性1： 属性值1
}
```

只能使用一次

通配符选择器

选取页面中索引元素

```
* {
	属性1： 属性值1
}
```



| 基础选择器   | 作用                    | 特点                               | 使用情况     | 用法     |
| ------------ | ----------------------- | ---------------------------------- | ------------ | -------- |
| 标签选择器   | 可以选出所有相同的标签  | 不能差异化选择                     | 较多         | p {}     |
| 类选择器     | 可以选出1个或者多个标签 | 可以根据需求选择                   | 非常的       | .nav  {} |
| id选择器     | 一次只能选择1个标签     | id属性只能在每个HTML文档中出现一次 | 一般和js配合 | #nav {}  |
| 通配符选择器 | 选择所有标签            | 选择的太多，由部分不需要           | 特殊情况使用 | * {}     |

css字体属性

定义字体系列，大小，粗细和文字样式

font-family定义字体系列

font-size 字体大小 单位px

font-weight :

| 属性值  | 描述                                             |
| ------- | ------------------------------------------------ |
| normal  | 默认(不加粗)                                     |
| bold    | 定义粗体(加粗)                                   |
| 100-900 | 400等同于normal，700等同于bold，数字后面不跟单位 |

font-style：

| 属性值 | 作用                               |
| ------ | ---------------------------------- |
| normal | 默认值，浏览器会显示标准的字体样式 |
| italic | 浏览器会显示斜体                   |

一般让斜体标签(em，i)不倾斜

复合属性简写

```
font: font-style  font-weight  font-size/line-height  font-family
不能打断顺序
font： italc 700 16px  后两个不能省略
```

| 属性        | 表示     | 注意点                                               |
| ----------- | -------- | ---------------------------------------------------- |
| font-size   | 字号     | px像素单位                                           |
| font-family | 字体     | 实际工作按团队要求写字体                             |
| font-weight | 字体粗细 | 记得加粗是700或bold 不加粗是normal或400 数字不跟单位 |
| font-sytle  | 字体样式 | 倾斜是italic 不倾斜是normal 最常用normal             |
| font        | 字体连写 | 字体连写是有顺序 不能换位子 字号和字体必须同时出现   |

文本属性

外观：颜色，对齐，装饰，缩进，行间距。

文本颜色

color：red

| 表示         | 属性值           |
| ------------ | ---------------- |
| 预定义颜色值 | red，green，bule |
| 十六进制     | #FF0000，#FF6600 |
| RGB代码      | rgb(255,0,0)     |

对齐文本

text-align：left center right

装饰文本

text-decoration

| 属性值       | 描述                    |
| ------------ | ----------------------- |
| none         | 默认，没有装饰线        |
| underline    | 下划线，链接a自带下划线 |
| overline     | 上划线                  |
| line-through | 删除线                  |

文本缩进

text-indent 缩进多少像素 em代表一个文字大小

行间距

line-height 

CSS引入方式

1.行内样式表(行内式)

​	标签内部写

```
<p style="color:pink;"> wwww </p>
```

2.内部样式表(嵌入式)

​	写html内部 style标签中

​	一般放在head里面

3.外部样式表(链接式)

​	把样式单独写在CSS文件中，然后引用。

```
<link rel="stylesheet" href="css文件路径">
```

| 属性 | 作用                                                         |
| ---- | ------------------------------------------------------------ |
| rel  | 定义当前文档与被链接文档之间的关系                           |
| href | 定义所链接外部样式表文件的URL，可以是相对路径，也可以是绝对路径 |

Emmet语法

使用缩写提高速度

1.生成标签直接输入标签名按tab键即可，比如 div+tab

2.如果想生成多个相同标签 加上* div*3

3.如果有父子级关系 用> ul>li

4.如果有兄弟级关系的标签用 +

5.如果生成带有类名或者id名字，直接写.demo 或者#two tab键

6.如果生成div类名有顺序，用自增符号$

7.如果想生成的标签内部写内容用{}



css简写

快速格式化代码

复合选择器

准确高效的选择目标标签

由两个或者多个基础选择器，通过不同的方式组合而成

后代选择器 子选择器 并集选择器 伪类选择器



后代选择器 选择父元素里面的子元素

```
元素1 元素2 {样式声明}
```

子选择器 亲儿子

```
元素1>元素2 {样式说明}
```

并集选择器

竖着写 最后一个选择器不加逗号

```
元素1，元素2{样式说明}
```

伪类选择器

用于向某些选择器添加特殊的效果，比如给链接添加特殊效果，或者选择第一个，第n个元素。伪类选择器书写最大的特点是用冒号：表示

链接伪类

```
a:linke			选择所有未被访问的链接
a:visited		选择所有已被访问的链接
a:hover			选择鼠标指针位于其上的链接
a:active		选择活动链接(鼠标按下未弹起的链接)
```

按照LVHA的顺序声明

：focus

选取获得焦点的表单元素

焦点就是光标，一般情况<input>表单元素才能获取，因此选择器也主要针对表单元素而言

```
input：focus {
	background-color：yellow
}
```

元素显示模式：块元素 行内元素

块元素：h1-h6 p div ul ol li

1.比较霸道，自己独占一行

2.高度，宽度，外边距以及内边距都可以控制

3.宽度默认是容器(父级宽度)的100%

4.是一个容器及盒子，里面可以放行内或者块级元素

注意：

1.文字类标签不能用块元素。

2.<p>标签用于存放文字，不能放块级元素，特别是div

3.h1-h6也不可以

行内元素：a strong b em ....

特点：

1.相邻行元素在一行上，一行显示多个。

2.高，宽直接设置是无效的

3.默认宽度就是本身内容的宽度。

4.行内元素只能容纳文本或其他行内元素。

注意：

链接里面不能再放链接

特殊情况<a>里面可以放快级元素

行内块元素：特殊标签 img input td 同时具有块元素和行内元素的特点

特点：

1.和相邻行内元素在一行上，但是他们中间会有空白缝隙，一行可以显示多个

2。默认宽度就是本身内容宽度

3.高度，行高，外边距以及内边距都可以设置

元素显示模式转换

display：block inline inline-block

Snipaste 截图工具

快捷键

1.F1可以截图，同时测量大小，设置箭头，书写文字

2.F3在桌面置顶显示

3.点击图片，alt可以取色 按下shift切换取色模式

4.按下esc取消图片显示

单行文字垂直居中：让文字行高等于盒子的高度

CSS背景

通过CSS背景属性，可以给页面元素添加背景样式。

背景属性可以设置背景颜色，背景图片，背景平铺，背景图片位置，背景图像固定。

背景颜色 background-color

一般情况默认值是transparent(透明)



背景图片background-image

描述了元素的背景图像，实际开发见logo或者一些装饰小图片，优点便于控制位置(精灵图也是一种运用场景)

```
background-image：none | url (url)
```

背景平铺background-repeat

```
background-repeat: repeat | no-repeat |repeat-x | repeat-y
```

页面可以i添加背景图片，也可以添加背景颜色。

背景图片位置

```css
background-position:x y;
x坐标 y坐标，可以使用方位名词或者精确单位
length 百分比 由浮点数和单位标识符组成
position top|center bottom left center right
省略的水平
```

背景图像固定

baackground-attachment 是否根据页面滚动

scroll：背景图像随对象内容滚动

fixed：背景图像固定

复合写法

当使用简写属性时，没用特定的书写顺序，一般习惯约定为：

background：背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置

- 背景颜色半透明

background：rgba(0，0，0，0.3)；0.3习惯写0；  

CSS三大特性

层叠性：样式冲突就近原则

继承性：子标签会继承父标签某些样式(text-,font-,line-,color)

行高的继承性

```css
body {
	font：12px/1.5 Microsoft YaHei；
}
```

- 行高可以跟单位可以不跟单位
- 如果子元素没用设置行高，则会继承父元素的行高为1.5
- 此时子元素的行高是：当前子元素的文字大小*1.5

优先级

- 选择器不同，执行层叠性

  ![image-20220927114034517](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220927114034517.png)

复合选择器会有权重叠加

盒子模型

边框（border）

border设置边框宽度 样式 粗细

```css
bireder：birder-width || border-style || border-color
```

```css
border-style:solid实线边框 dashed虚线边框 dotted 点线边框
```

```css
缩写格式：
border：1px solid red；没有顺序
```

```css
边框分开写法：
border-top：1px solid red；
```



内边距（padding）

```css
padding-left / right/top/bottom
```

| 值的个数                    | 表达意思                                                 |
| --------------------------- | -------------------------------------------------------- |
| padding：5px                | 1个值，代表上下左右都5像素内边距                         |
| padding：5px 10px           | 2个值，代表上下内边距是5像素 左右内边距是10像素          |
| padding：5px 10px 20px      | 3个值，代表上内边距5像素 左右内边距10像素 下内边距20像素 |
| padding：5px 10px 20px 30px | 4个值，上是5像素 右10像素 下20像素 左是30像素 顺时针     |

如果盒子本身没有指定width/height属性，则此时padding不会撑开盒子大小

外边距（margin）

```
margin-right-left-top-bottoom
```

外边距可以让块级盒子水平居中，但是必须满足两个条件：

- 盒子必须指定宽度width
- 盒子左右的外边距都设置为auto

```css
.header{width：960px； margin：0 auto；}
```

三种写法

- margin-left：auto； margin-right auto；
- margin：auto；
- mamrgin：0 auto；、

注意：以上方法是让块级元素水平居中，行内块元素或者行内元素水平居中给其父元素添加text-align：center。

嵌套块元素垂直外边距的塌陷

对于两个嵌套关系的块元素，父元素有上外编剧同时子元素也有上外边距，此时父元素会塌陷较大的外边距值

解决方案：

1. 可以为父元素定义上边框
2. 可以为父元素定义上内边距
3. 可以为父元素添加overflow：hidden；
4. ![image-20220927183705230](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220927183705230.png)

清除内外边距

网页元素默认带有内外边距，而且不同游览器默认的也不一致，一次无码在布局时先清除。

```css
*{
	padding：0； 清除内边距
	margin：0；	清除外边距
}
```

注意：行内元素为了照顾兼容性，尽量只设置左右内外边距，不要设置上下内外边距。但是转换为块级和行内块元素就可以了

PS操作

![image-20220927185157284](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220927185157284.png)

去掉li前面的项目符号]

```css
list-style:none
```

圆角边框

```css
border-redius:length
length:参数或百分比
设置不同圆角顺时针
分开写 top-；eft top-rigth
```

盒子阴影

```css
box0shadow:h-shadow v-shadow blur spread color inset;
```

![image-20220928194156673](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220928194156673.png)

文字阴影

```css
text-shadow：h-shadow v-shadow blur color
```

![image-20220928194809035](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220928194809035.png)



CSS浮动 

float属性用于创建浮动框，将其移动到一边，直到左边缘或右边缘及包含块或另一个浮动框的边缘

```css
选择器 { float：属性值；}
none：不浮动
left：向左浮动；
right：向右浮动；
```

浮动特性：

1.脱离标准普通流的控制（浮）移动到指定位置（动），俗称脱标

2.浮动的盒子不再保留原先位置

3.浮动元素会具有行内块元素特性

任何元素都可以浮动，不管原先是什么模式的元素，添加浮动之后具有行内块相似的特性

- 如果块级盒子没有设置宽度，默认宽度和父级一样宽，但是添加浮动后，他的大小根据内容决定
- 浮动的盒子中间没有缝隙的，是紧挨这一起的
- 行内元素同理

为了约束浮动元素位置，无码网页布局一般采取的策略是：

先用标准流的父元素排列上下位置，之后内部子元素采取浮动排列左右位置，复合网页布局第一准则。

注意点：

1.浮动和标准流的父盒子搭配

​	先用标准流的父元素排列上下位置，之后内部元素采取浮动排列左右位置

2.一个元素浮动了，理论上其余兄弟元素也要浮动。

​	一个盒子里面有多个子盒子，如果其中一个盒子浮动了，那么其他兄弟也应该浮动，以防引起问题。浮动的盒子只会影响后面的标准流，不会影响前面的标准流

清除浮动

```css
选择器 { clear：属性值；}
left：不允许左侧有浮动元素
rigth不允许右侧有浮动元素
both同时清除左右两侧浮动的影响
```

 清除浮动采取闭合浮动

清除浮动的方法

- 额外标签法也称隔墙法，是W3C推荐的做法

  在浮动元素末尾添加一个空的标签，例如<div style="clear.both“>或者其他标签

  标签必须是块级元素。

- 父级添加overflow属性

  给父级添加overflow属性，将其属性值设置为hidden，auto或scroll 

- 父级添加after伪元素

  ：after方式是额外标签法的升级版。也是给父元素添加

  ```css
  .clearfix:after {
  	content:"";
  	display:block;
  	clear:both;
  	visibility:hidden;
  }
  .clearfix {
  	*zoom:1;
  }
  ```

  

- 父级添加双伪元素                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          

```css
.clearfix:before,.clearfix:after {
	content:"";
	display:table;
}
.clearfix:after{
	clear:both;
}
.clearfix{
 *zoom:1;
}
```

PS切图

图层切图

最简单方法：右击图层 -> 快速导出png。

但是很多情况下，我们需要合并图层在导出：

1.选中需要的图层：图层菜单 -> 合并图层（ctrl+e）

2.右击 -> 快速导出为PNG



切片切图

1. 利用切片选中图片

- ​	利用切片工具手动划出

​	2.导出选中的图片

​	文件菜单 -> 导出 -> 存储为web设备所用格式 -> 选择我们要的图片格式 -> 存储.

 PS插件切图

Cutterman插件，一间切图

CSS属性书写顺序

![image-20220929140805396](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220929140805396.png)

![image-20220929141201366](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20220929141201366.png)

实际开发中，我们不会直接用链接a而是用li包含链接（li+a）的做法

浮动的盒子不会有外边距合并的问题



定位

 将盒子定在某个位置，所以定位也是在摆放盒子，按照定位的方式移动盒子

定位=定位模式+边偏移

定位模式用于指定一个元素在文档中的定位方式，边偏移则决定了该元素的最终位置

 

定位模式决定了元素的定位方式，它通过CSS的position属性来设置

static静态定位	relative相对定位	absolute绝对定位	fixed固定定位

边偏移

![image-20221013084834141](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221013084834141.png)

静态定位是元素默认定位方式，无定位的意思

选择器 { position：static；}



相对定位 relative

相对原来的位置而言

选择器 {position：relative}

移动参照原来位置

移动了原位置保留



绝对定位 absolute

相对于祖先元素而言

特点：

1. ​	如果没有祖先元素或者父元素没有定位，以浏览器为准
2.   如果有，按照最近一级的有定位祖先元素作为参考
3. 绝对定位不再占有原来位置 脱标

子绝父相

子级是绝对定位的话，父级要用相对定位。

1.子级绝对定位，不会占有位置，可以放到父盒子里面的任何地方，不会影响他的兄弟盒子。

2.父盒子需要加定位限制子盒子在父盒子内显示。

3.父盒子布局时，需要占有位置，因此父亲只能时相对定位



固定定位fixed

固定游览器可视窗口2的某个位置，游览器滚动元素位置不变。

小技巧固定在版心一侧

1.让固定定位的盒子left：50%，走到浏览器一半位置

2.让固定定位的盒子margin-left：版心宽度一半距离，夺走版心宽度的一半位置就可以让固定定位的盒子贴着版心右侧对齐了。

粘性定位sticky

```css
选择器 {position:sticky;top:10px}
```

1.以浏览器的可视窗口为参照点移动元素

2.粘性定位占有原先的位置

3.必须添加top，left，right，bottom其中一个才有效。

![image-20221013131015419](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221013131015419.png)

定位叠放次序 z-index z轴

```css
选择器 {z-index:1;}
1.数值可以是正整数，负整数或0，默认auto，数值越大，盒子越靠上
2.如果属性相同，按书写顺序，后来在居上
3.不能加单位
4.只有定位的盒子有z-index属性
```

绝对得盒子居中

加了绝对定位的盒子不能通过margin：0 auto水平居中，但是可以通过以下计算方法实现水平和垂直居中

1.left：50% 让盒子的左侧移动到父级元素的水平中心位置。

2.margin-left：-100px：让盒子向左移动自身宽度一半

 定位特殊特性

绝对定位和固定定位也和浮动类似。

1.行内元素添加绝对或固定定位，可以直接设置高度和宽度。

2.块级元素添加绝对或者固定定位，如果不给宽度或者高度，默认大小是内容的大小。

绝对定位会完全压住盒子

浮动元素不同，只会压住它下面标准流的盒子，但是不会压住下面标准流盒子的文字

总结

![image-20221013135604475](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221013135604475.png)

元素的显示和隐藏

display 属性（重点）

none隐藏对象 block显示对象

隐藏后不再占有原来位置



visibility：visible可见 hidden隐藏

隐藏后继续占有原来的位置

overflow溢出

scroll显示滚动条 auto溢出显示滚动条 hidden隐藏

有定位慎用。



CSS高级技巧

精灵图

渐少服务器接受和发送的次数，提高效率。

1.针对背景图片的使用，将小的图片合成大图片

2.移动背景图片位置，使用background-position

3.移动距离是x和y坐标

4.精确测量，每个小背景图片的大小和位置（x轴右边走是正值，左边走是负值，y轴同理

字体图标：展示是图标 实际是字体

1.轻量级 

2.灵活性，随便改变颜色大小

3.兼容性

如果遇到一些结构样式都简单的小图标用字体图标。

如果遇到复杂的就用精灵图。

1.下载字体图标

2.引入 把fonts文件夹放在页面根目录下面 通过css复制

3.追加 

```css
@font-face {
  font-family: 'icomoon';
  src:  url('fonts/icomoon.eot?p4ssmb');
  src:  url('fonts/icomoon.eot?p4ssmb#iefix') format('embedded-opentype'),
    url('fonts/icomoon.ttf?p4ssmb') format('truetype'),
    url('fonts/icomoon.woff?p4ssmb') format('woff'),
    url('fonts/icomoon.svg?p4ssmb#icomoon') format('svg');
  font-weight: normal;
  font-style: normal;
  font-display: block;
}
```

网站icomoon字库 阿里iconfont字库

CSS三角

```
div{
	width:0
	height:0
	font-size:0 兼容性
	line-height:0;  兼容性
	border:50px solid transparent;
	border-left-color:pink;
}
```



用户界面样式

更改用户鼠标样式 cursor

```css
li {cursor:pointer}
```

![image-20221013193709867](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221013193709867.png)

轮廓线 outline

给表单添加outline：0；或者outline：none；样式后，就可以去掉默认蓝色边框。

文本域右下角取消：resize：none； 文本域标签放在一行



vertica-align 实现图片表单的文字对齐

设置元素的垂直对齐方式，但是只针对行内元素或者行内快元素。

![image-20221013194605027](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221013194605027.png)

解决图片底部默认空白缝隙

bug：行内块元素会和文字的基线对齐

解决方法

1.给图片添加vertical-align：middle|top|bottom。

2.把图片装换成块级元素display：block；



单行文字溢出用省略号

必须满足三个条件

```
1.先强制一行内显示文本
white-space：nowrap；
2.超出部分隐藏
overflow：hidden；
3.文字用省略号代替超出部分
text-overflow：ellipsis；
```

多行文本溢出用省略号

多行文本溢出显示省略号，有较大兼容性问题，适合于webKit浏览器或移动端（移动端大部分是webKit内核）

```css
overflow:hidden;
text-overflow:ellipsis;
弹性伸缩盒子模型显示
display：-webkit-box;
限制在一个块元素显示的文本的行数
-webkit-line-clamp：2
设置或检索伸缩和对象的子元素排列方式
-webkit-box-orient：vertical；
```

常见布局技巧

1.margin负值运用

让每个盒子margin往左侧移动-1px正好压住相邻盒子边框

2.鼠标经过某个盒子的时候，提高盒子的层级即可（如果没定位加相对定位（保留位置），如果有得，则加z-index）

3.行内块巧妙运用

4.css三角强化

```css
width:0;
height:0;
border-color:transparent red transparent transparent;
border-style:solid;
border-width:22px 8px 0 0;
```

css初始化

提高

html5

新增语义化标签

- \<header> ：头部标签

- \<nav>:导航标签

- \<article>:内容标签

- \<section>:定义文档某个区域

- \<aside>:侧边栏标签

- \<footer>:尾部标签

  ![image-20221014132526996](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014132526996.png)

多媒体标签

1.音频：\<audio>

```
<audio src='文件地址' controls='controls'></audio>
```

![image-20221014133718466](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014133718466.png)

2.视频：\<video> 尽量放mp4

```html
<video src='文件地址' controls='controls'></video>
```

![image-20221014133107070](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014133107070.png)

input表单

![image-20221014134008589](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014134008589.png)

表单属性

![image-20221014134435866](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014134435866.png)

CSS3新特性

新增选择器

1.属性选择器

根据类的属性进行选择，这样可以不要借助于类或者id选择器

![image-20221014135211774](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014135211774.png)

注意：类选择器械，属性选择器，伪类选择器，权重为10；

2.结构伪类选择器

根据文档结构选择，常用于父级选择器里面的子元素

![image-20221014141649785](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014141649785.png)

nth-chlid（n） 

even偶数 odd奇数  公式

![image-20221014152545599](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014152545599.png)

nth-child 不区分孩子的标签

nth-of-type（）会把指定的type更改

3.伪元素选择器

可以用css创建新标签元素，而不需要html标签，简化html结构

| 选择符   | 简介                     |
| -------- | ------------------------ |
| ::before | 在元素内部的前面插入内容 |
| ::after  | 在元素内部的后面插入内容 |

![image-20221014153928040](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014153928040.png)

css3盒子模型

通过box-sizing来指定盒模型，有两个值：即可指定为content-box，border-box，这样我们计算盒子大小的方式发生了改变。

1.box-sizing：content-box 盒子大小为width+padding+border

2.box-sizing：border-box 盒子大小为width 不会超过盒子

图片模糊处理

css3滤镜filter

```css
filter:函数() 例如 filter：blur() 数值越大图像越模糊
```

calc函数

```
width:calc(100%-80px); 
```



css3过渡

![image-20221014163039746](C:\Users\lanjing\AppData\Roaming\Typora\typora-user-images\image-20221014163039746.png)



















