[toc]
# 前端HTML+CSS学习
# 总体介绍：
### 前端开发(客户端):
#### 1.文字客户端  
#### 2.图形化客户端（C/S架构（client/server））
#### 3.网页（B/S架构(browser/server)）
##### 网页的优点（相比图形化）
跨平台  无需安装  无需更新（客户）
##### 网页使用的语言
HTML CSS JavaScript
### 网页开发概览：
#### 环境：
浏览器：渲染网页
#### 开发标准：
W3C(万维网联盟)---->统一的标准使网页在不同的浏览器有统一的渲染效果
#### 由W3C标准，网页分为结构表现和行为
##### 结构
HTML用于描述网页结构
##### 表现
CSS用于控制页面中元素的样式
##### 行为
JavaScript用于相应用户操作
# 知识点内容
## HTML基础学习
### 1.HTML介绍：
HTML（超文本标记语言——HyperText Markup Language）是构成 Web 世界的一砖一瓦。它定义了网页内容的含义和结构。除 HTML 以外的其它技术则通常用来描述一个网页的表现与展示效果（如 CSS），或功能与行为（如 JavaScript）。

“超文本”（hypertext）是指连接单个网站内或多个网站间的网页的链接。链接是网络的一个基本方面。只要将内容上传到互联网，并将其与他人创建的页面相链接，你就成为了万维网的积极参与者。

HTML 使用“标记”（markup）来注明文本、图片和其他内容，以便于在 Web 浏览器中显示。
HTML 元素通过“标签”（tag）将文本从文档中引出，标签由在“<”和“>”中包裹的元素名组成，HTML 标签里的元素名不区分大小写。也就是说，它们可以用大写，小写或混合形式书写。

HTML文件的后缀为.html

### 2.编写第一个网页程序
#### 标签：
<标签> 开始标签.....中间就是内容..... </标签>结束标签
##### 标题标签：
```  HTML 
<h1>  </h1>
<h2>  </h2>
<h3>  </h3>
```
共有六级标题
##### 段落标签
``` html
<p> 这是一个段落 </p>
<p>这是另一个段落</p>
```
##### 根标签,子标签（层级关系）
``` html
<html>
      <head>
                <title>   <title>
      </head>
      <body>
      </body>
</html>    
      
```
根标签：
``` html
<html>    </html> 
```
子标签（头部）
用户不可见，是给浏览器看的
``` html
<head>   </head>
```
子标签（身体）
用户可见部分
``` html
<body>    </body>
```
#### 第一个网页示例：
``` HTML
<html>
      <head>
                <title> 第一个网页</title>
      </head>
      <body>
	<h1> 将进酒 </h1>
	<h2>  李白</h2>
	<h3>  </h3>
	<p>君不见黄河之水天上来，奔流到海不复回 </p>
	<p>君不见高堂明镜悲白发，朝如青丝暮成雪。</p>
	<p>人生得意须尽欢，莫使金樽空对月。</p>
	<p>天生我材必有用，千金散尽还复来。</p>
      </body>
</html> 
```
### 3.细化一个网页
#### HTML注释
``` html
<!-- 这是一个注释 -->
```
注释不可嵌套
#### 标签的属性
HTML 标签可以设置属性
属性可以在标签中添加附加信息
属性一般描述于开始标签，不用于结束标签
属性总是以名称/值对的形式出现，比如：name="value"。

```html
 <h1>这是我的<font color="red">第二个</font>网页！</h1>
```

font 规定文本的字体、字体尺寸、字体颜色。
```
<font>   </font>
```
这里的color="red"就是属性，让中间字体变为红色。
属性和标签名或其他属性应该用空格隔开。
属性值应该始终被包括在引号内。
双引号是最常用的，不过使用单引号也没有问题。
```HTML
<font color="red">第二个</font>
```
color就是属性名   red就是属性值 ，属性不能随便写，是有相应规定的。
##### 添加了属性的网页代码：
```html
<html>
    <head>
            <title>第二个网页</title>
    </head>
    <body>
        <h1>这是我的<font color="red">第二个</font>网页！</h1>
    </body>
</html>
```
### 4.网页的基本结构
#### 文档声明

##### HTML5的版本声明
文档声明用来告诉浏览器当前网页的版本，写在第一行
```html
<!doctype html>
<!doctype HTML>
```
示例：
```html
<!doctype html>
<htm>
    <head>
            <title></title>
    </head>
    <body>
        <h1>              </h1>
    </body>
</htm>
```
##### 文档字符编码声明
字符编码有很多方式，网页一般使用UTF-8字符集编码。
声明，置于head内部
```html
 <head>
            <meta charset="utf-8">
</head>
```
#### 完整基本结构：
```html
<!doctype html>
<!--网页版本声明-->
<html>
<!--HTML的根标签-->
    <head>
        <!--子元素，头部（帮助浏览器解析网页）-->
        <meta charset="utf-8">
         <!--meat用来设置网页元数据--> 
        <title>标题</title>
         <!--网页的标题，搜索引擎搜索的就是这个-->
    </head>
    <body>
        <!--body是HTML的子元素，所有可见内容都应该写在body里-->
        <h1></h1>
        <!--网页的一级标题-->
    </body>
</html>
```
## HTML语法/特性学习
### 实体
#### 实体的作用：
在网页里编写的多个空格默认被解析为一个空格，不能直接书写一些特殊符号：多个空格，大于，小于号等
在 HTML 中不能使用小于号（<）和大于号（>），这是因为浏览器会误认为它们是标签。

如果希望正确地显示预留字符，我们必须在 HTML 源代码中使用字符实体（character entities）
#### 实体的语法
    &实体的名字
例：
```   html
&nbsp;      <!--不间断空格-->
&lt;        <!--小于号-->
&gt;        <!--大于号-->
&copy;      <!--版权符号-->
```
[详细实体参考：](https://www.runoob.com/html/html-entities.html)

### meat标签
#### meat标签作用
元数据（Metadata）是数据的数据信息。
```html
<meta>
```
标签提供了 HTML 文档的元数据。元数据不会显示在客户端，但是会被浏览器解析。
META元素通常用于指定网页的描述，关键词，文件的最后修改时间，作者及其他元数据。
元数据可以被使用浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 Web 服务调用。
[meat标签文档](https://www.runoob.com/tags/tag-meta.html)
#### meat示例
例：
```html
<meta name="keywords" content="前端，html,css">
```
这里的keywords表示网页的关键字，搜索时会检索这个关键字的内容。
```html
<meta name="description" content="免费在线教程">
```
description用于网页介绍描述，就是搜索引擎搜索显示结果的小字部分。title标签里的是搜索结果的标题。
### 语义化标签
在网页里，HTML负责网页结构使用HTML标签时我们更应该关注其语义，而不是样式。
#### h标题标签
h1-h6一共有六级标题，重要性依次递减，h1在网页中仅次于title标签，一般情况下只有一个。一般情况下标题标签只用到h1-h6.

##### 标题组：
hgroup标签被用来对标题元素进行分组。

当标题有多个层级（副标题）时，hgroup 元素被用来对一系列 h1 - h6 元素进行分组。
```html
<hgroup>
<h1>Welcome to my WWF</h1>
<h2>For a living planet</h2>
</hgroup>
```
独占一行的元素叫块元素
#### P标签(段落)
P标签表示一个段落。
是一个块元素。
#### em标签：强调文本
呈现为被强调的文本。
```html
<em>强调文本</em>
```
同样的还有strong标签:定义重要的文本。
```html
<strong>加粗文本</strong>
```
#### blockquote标签：引用
定义一个摘自另一个源的块引用：浏览器通常会对 blockquote元素进行缩进
例：
```html
<blockquote cite="http://www.worldwildlife.org/who/index.html">
For 50 years, WWF has been protecting the future of nature. The world's leading conservation organization, WWF works in 100 countries and is supported by 1.2 million members in the United States and close to 5 million globally.
</blockquote>
```
还有同样的短引用：q标签
q 标签定义一个短的引用。

浏览器经常会在这种引用的周围插入引号。
例：
```html
<p>WWF's goal is to:
<q>Build a future where people live in harmony with nature.</q>
We hope they succeed.</p>
```
#### br标签：换行
br 标签插入一个简单的换行符。
br 标签是一个空标签，意味着它没有结束标签。

#### header标签（网页的头部）
header标签定义文档或者文档的一部分区域的页眉。
header 元素应该作为介绍内容或者导航链接栏的容器。
在一个文档中，您可以定义多个 header>元素。
注释：header标签不能被放在 footer，address或者另一个 header元素内部。
#### main标签
main> 标签用于指定文档的主体内容。
main 标签中的内容在文档中是唯一的。它不应包含在文档中重复出现的内容，比如侧栏、导航栏、版权信息、站点标志或搜索表单。
#### footer标签
footer 标签定义文档或者文档的一部分区域的页脚。

footer 元素应该包含它所包含的元素的信息。

在典型情况下，该元素会包含文档创作者的姓名、文档的版权信息、使用条款的链接、联系信息等等。

在一个文档中，您可以定义多个 footer元素。
#### nav标签
nav 标签定义导航链接的部分。

并不是所有的 HTML 文档都要使用到 nav元素。nav元素只是作为标注一个导航链接的区域。

在不同设备上（手机或者PC）可以制定导航链接是否显示，以适应不同屏幕的需求。

#### aside标签
aside的内容可用作文章的侧栏。、
#### article标签
article标签定义独立的内容。（文章）
article标签定义的内容本身必须是有意义的且必须是独立于文档的其余部分。
article的潜在来源：

#### section标签
section 标签定义了文档的某个区域。比如章节、头部、底部或者文档的其他区域。

#### div标签（定义区块，用的最多）

div 标签定义 HTML 文档中的一个分隔区块或者一个区域部分。

div标签常用于组合块级元素，以便通过 CSS 来对这些元素进行格式化。
#### span标签
span 用于对文档中的行内元素进行组合。

span 标签没有固定的格式表现。当对它应用样式时，它才会产生视觉上的变化。如果不对 span 应用样式，那么 span 元素中的文本与其他文本不会任何视觉上的差异。

span标签提供了一种将文本的一部分或者文档的一部分独立出来的方式

### 块元素  行内元素
#### 块元素
在网页中一般通过块元素来布局
会在块元素里放行内元素，但不会会在行内元素里放块元素。
P元素里不能放块元素。

#### 行内元素
用于包裹文字

### 列表
HTML 支持有序、无序和定义列表:
列表之间可以互相嵌套
#### 无序列表：（用的最多）
使用ul标签来创建有序列表
使用li来创建列表项
例：
```html
<ul>
<li>Coffee</li>
<li>Milk</li>
</ul>
```
#### 有序列表
有序列表始于 ol标签。每个列表项始于 li 标签。
列表项使用数字来标记。
例：
```html
<ol>
<li>Coffee</li>
<li>Milk</li>
</ol>
```
#### 自定义列表
自定义列表不仅仅是一列项目，而是项目及其注释的组合。
自定义列表以 dl 标签开始。每个自定义列表项以 dt（下定义） 开始。每个自定义列表项的定义以 dd （定义内容）开始。
例：
```html
<dl>
<dt>Coffee</dt>
<dd>- black hot drink</dd>
<dt>Milk</dt>
<dd>- white cold drink</dd>
</dl>
```

### 超链接
HTML 使用超级链接与网络上的另一个文档相连。。点击链接可以从一张页面跳转到另一张页面。或者当前页面的特定位置。
#### 超链接的定义
HTML使用标签 a来设置超文本链接,a标签里可以嵌套除它自身的的所有标签。
例：
```html
<a>  超链接 </a> 
<a href="url">链接文本</a>
```
#### 超链接的属性
##### href跳转到指定目标
值可以是外部网页的地址
也可以是内部页面地址

```html
 <a href="https://www.baidu.com">百度</a>
```
#####  target 属性
使用 target 属性，你可以定义被链接的文档在何处显示。
可选值：
_self默认值，在当前页面打开超链接
_blank在一个新页面打开超链接
```html
<a href="https://www.runoob.com/" target="_blank" rel="noopener noreferrer">访问菜鸟教程!</a>
```
#### ID属性（锚点）
每一个标签都可以添加一个id属性
id属性就是元素的唯一的标识，同一页面不能出现相同的id属性。
```html
<a id="bottle" href="#">回到顶部</a>
```
##### 跳转到当前页面的任意地方
href 写#，就是直接跳转到当前页面的顶部

在开发中，#可以作为一种占位符（没确定跳转页面，先拿#代替）

也可以使用JavaScript：；来作为占位符，点击后什么都不发生。

跳转到页面指定位置，只需要将href属性设置为#目标元素的ID属性值
#### 路径：
##### 相对路径
当我们跳转到一个服务器内部的页面时我们使用相对路径，相对路径一般以.或..开头
```html
./ 
```
 表示当前文件所在的目录
```html
../ 表示当前文件所在的目录的上一级目录
```
### 图片标签
图像由img标签定义。使用img引入外部图片。
```html
<img src="" alt="">
```

img 是空标签，意思是说，它只包含属性，并且没有闭合标签。它属于一种替换元素（介于行内元素和块元素之间）
#### src属性
要在页面上显示图像，你需要使用源属性（src）。src 指 "source"。源属性的值是图像的 URL 地址。（外部图片的路径)
路径规则和超链接一样。
#### alt属性
alt属性用来为图像定义一串预备的可替换的文本。替换文本属性的值是用户定义的。（图片的描述）一般会在图片加载不出来的时候显示。
搜索引擎会根据alt中的内容来搜索图片内容。
#### 图片的高和宽
height（高度） 与 width（宽度）属性用于设置图像的高度与宽度。

属性值默认单位为像素:
```html
<img src="pulpit.jpg" alt="Pulpit rock" width="304" height="228">
```
宽高中修改一个，则另一个会等比缩放。pc端，一般不建议修改图片大小，需要多大就裁多大。

指定图像的高度和宽度是一个很好的习惯。如果图像指定了高度宽度，页面加载时就会保留指定的尺寸。如果没有指定图片的大小，加载页面时有可能会破坏HTML页面的整体布局。

#### 图片的格式

jpeg(jpg)
支持颜色丰富，不支持透明效果，不支持动图
gif
支持颜色少，支持简单透明，支持动图
png
支持颜色丰富，支持复杂透明，不支持动图
webp
谷歌推出的专门用于网页的图片，具备所有优点，本身还小
效果一样，尽量选小的图片，但是兼容性不好
base64
 使用这个编码，可以将图片转化为字符，通过字符来引入图片，一般是需要和网页一起加载的图片才使用base64

### 内联框架(很少使用)
通过使用框架，你可以在同一个浏览器窗口中显示不止一个页面。
使用iframe标签	定义一个内联的框架
``` html
<iframe src="" frameborder="0"></iframe>
```
src指定引入网页的路径
height 和 width 属性用来定义iframe标签的高度与宽度。

属性默认以像素为单位, 但是你可以指定其按比例显示 (如："80%")。

frameborder 属性用于定义iframe表示是否显示边框。

设置属性值为 "0" 移除iframe的边框:

### 引入音视频
#### 音频
audio标签用来向页面引入一个外部的音频文件，默认不允许用户自己控制播放停止。
可以添加controls属性来允许用户自己播放
autoplay属性用来控制音频自动播放（大部分网页不会自动播放，为了好的用户体验）（很少用）
loop属性 :音乐循环播放
```html
<audio src=""  controls autoplay loop ></audio>
```
一般这样写更多一点,兼容性更好。
```html
<audio controls>
    <source src="horse.ogg" type="audio/ogg">
    <source src="horse.mp3" type="audio/mpeg">
    您的浏览器不支持 audio 元素。
</audio>
```
#### 视频
使用video标签来引入视频,与audio相似。
```html
<video controls>
    <source src="horse.mp4" >
</video>
```

### 表格
#### 基础表格
表格在日常生活中使用的非常的多，比如excel就是专门用来创建表格的工具，
表格就是用来表示一些格式化的数据的，比如：课程表、银行对账单
在网页中也可以来创建出不同的表格。
    在HTML中，使用table标签来创建一个表格 
    在table标签中使用tr来表示表格中的一行，有几行就有几个tr
    在tr中需要使用td来创建一个单元格，有几个单元格就有几个td

colspan横向的合并单元格:
``` html
 <td colspan="2">D3</td>
```
rowspan用来设置纵向的合并单元格   
``` html
 <td rowspan="2">B4</td>
```
#### 长表格
有一些情况下表格是非常的长的，
        这时就需要将表格分为三个部分，表头，表格的主体，表格底部
    在HTML中为我们提供了三个标签：
        thead 表头
        tbody 表格主体
        tfoot 表格底部
        
    这三个标签的作用，就来区分表格的不同的部分，他们都是table的子标签，
        都需要直接写到table中，tr需要写在这些标签当中
        
    thead中的内容，永远会显示在表格的头部
    tfoot中的内容，永远都会显示表格的底部
    tbody中的内容，永远都会显示表格的中间
    
    如果表格中没有写tbody，浏览器会自动在表格中添加tbody
    并且将所有的tr都放到tbody中，所以注意tr并不是table的子元素，而是tbody的子元素
    通过table > tr 无法选中行 需要通过tbody > tr

### 表单
表单的作用就是用来将用户信息提交给服务器的
				比如：百度的搜索框 注册 登录这些操作都需要填写表单
创建一个表单
``` html
<form action="target.html">
```
form标签中必须指定一个action属性，该属性指向的是一个服务器的地址
	当我们提交表单时将会提交到action属性对应的地址
使用form创建的仅仅是一个空白的表单，
	我们还需要向form中添加不同的表单项
#### 文本框：
``` html
<input type="text"/>
```
#### 提交按钮：
``` html
<input type="submit"/>
```
使用input来创建一个文本框，它的type属性是text
    如果希望表单项中的数据会提交到服务器中，还必须给表单项指定一个name属性
    name表示提交内容的名字	
    
用户填写的信息会附在url地址的后边以查询字符串的形式发送给服务器
    url地址?查询字符串
格式：
    属性名=属性值&属性名=属性值&属性名=属性值&属性名=属性值
在文本框中也可以指定value属性值，该值将会作为文本框的默认值显示	

在html中还为我们提供了一个标签，专门用来选中表单中的提示文字的
label标签
该标签可以指定一个for属性，该属性的值需要指定一个表单项的id值
#### 密码框
``` html
<input  type="password" name="password" /> 
```
密码框
	- 使用input创建一个密码框，它的type属性值是password

##### 单选按钮
    - 使用input来创建一个单选按钮，它的type属性使用radio
    - 单选按钮通过name属性进行分组，name属性相同是一组按钮
    - 像这种需要用户选择但是不需要用户直接填写内容的表单项，
        还必须指定一个value属性，这样被选中的表单项的value属性值将会最终提交给服务器
        
    如果希望在单选按钮或者是多选框中指定默认选中的选项，
        则可以在希望选中的项中添加checked="checked"属性
多选框
	- 使用input创建一个多选框，它的type属性使用checkbox

##### 下拉列表
    - 使用select来创建一个下拉列表
    下拉列表的name属性需要指定给select，而value属性需要指定给option
    可以通过在option中添加selected="selected"来将选项设置为默认选中
    当为select添加一个multiple="multiple"，则下拉列表变为一个多选的下拉列表
    在select中可以使用optgroup对选项进行分组
    同一个optgroup中的选项是一组
    可以通过label属性来指定分组的名字

提交按钮可以将表单中的信息提交给服务器
        使用input创建一个提交按钮,它的type属性值是submit
        在提交按钮中可以通过value属性来指定按钮上的文字

input type="reset" 可以创建一个重置按钮，
    点击重置按钮以后表单中内容将会恢复为默认值

使用input type=button可以用来创建一个单纯的按钮，
					这个按钮没有任何功能，只能被点击

除了使用input，也可以使用button标签来创建按钮
				这种方式和使用input类似，只不过由于它是成对出现的标签
					使用起来更加的灵活


## CSS基础学习
### CSS介绍
CSS用于控制页面中元素的样式(表现)
（层叠样式表）是一个多层结构，用CSS给每层设计样式，最终看见的是网页上最上面的一层（ps图层的原理）

### 使用css来修改网页中原始的样式
#### 1.style属性（内联样式）
在标签内部通过style属性来设置元素的样式(不推荐使用)
内联样式只能对一个标签生效，影响多个元素要写很多遍，样式变化不方便修改和维护。
！开发时不要使用内联样式
例：
```html
    <p style="color: brown; font-size: 60px;">君不见黄河之水天上来，奔流到海不复回</p>
```
#### 2.(内部样式表)将样式编写到head里
将样式编写到head里的style标签里。只对一个网页起作用。不能跨页面复用
```html
<head>
    <title></title>
    <style>
       统一写到这里
    </style>
</head>
```
通过css选择器选中元素并为其设置格式
```html
<head>
    <style>
    p{


    }    
    </style>
</head>
```
可以为所有p元素设置样式：
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <title></title>
    <style>
    p{
        color: burlywood;
        font-size: 50px;
    }
    </style>
</head>
<body>
    <p style="color: brown; font-size: 60px;">君不见黄河之水天上来，奔流到海不复回</p>
    <p>君不见高堂明镜悲白发，朝如青丝暮成雪。</p>
	<p>人生得意须尽欢，莫使金樽空对月。</p>
	<p>天生我材必有用，千金散尽还复来。</p>
</body>
</html>
```
#### 3.（外部样式表）将样式写在外部css文件里
将样式写在外部css文件里,然后通过link标签引入外部的css文件,外部样式的好处在于样式可以在不同页面复用。将样式编写到css里可以很好使用到浏览器的缓存机制，从而加快网页的加载速度。
这是开发的最佳样式
css程序：
```css
p{
    color: blue ;
    font-size: 20px;
}
```
html引入css样式：
```html
    <head>
   
    <link rel="stylesheet" href="./样式.css">
</head>
```
### css基本语法
在style标签内部，不属于html，与html隔离，需要遵守CSS的语法
```html
<head>
    <style>
         /* style标签内部,就不归html管理了*/
    </style>
</head>
```
#### css的注释
使用/*   */
```css
/*这是个注释*/
p
{
    text-align:center;
    /*这是另一个注释*/
    color:black;
    font-family:arial;
}
```
#### 选择器
通过选择器选择页面中的元素，比如使用P标签就是选中页面所有P元素。

#### 声明块
通过声明块来指定要为元素设定的样式，声明块由一个个声明组成，声明是一个名值对结构一个样式对应一个样式值，名和值之间以：连接，以；结束。

### 选择器
#### 元素选择器
根据标签名来选中指定的元素
语法：标签名｛｝
例子：P{} h1{}
```css
<style>
p{
color :red;

}
</style>

```
#### id选择器
根据元素ID来选中指定的元素
(ID属性不要以数字开头，数字开头的ID在 Mozilla/Firefox 浏览器中不起作用。)
语法：  #id属性值｛｝
例子：#box｛｝   #red｛｝
```html
<head>
<style>
#red{
    color:red;
}
</style>>
</head>
<body>
<p id="red">这是一段文字</p>
</body>
```
#### class选择器（类选择器）
根据class属性来选中指定的元素组
class是一个html的标签属性，和ID相似，但是它可以重复。可以同时为一个元素指定多个class元素。
可以解决拿ID选择器不好给多个元素指定样式的弊端，
可以通过class给元素分组
语法：  .class属性值
```html

<style>
.red{
        color:red;
    }
</style>>
</head>
<body>
<p class="red">这是一段文字</p>
<p class="red">这是一段文字</p>
</body>
```
#### 统配选择器
选中页面里所有元素
语法：*
```css
*{
    color:red;
}
```
#### 复合选择器
交集选择器：
作用：选中复合多个条件的元素
语法：选择器1选择器2选择器3选择器N｛｝
注意点：如果有元素选择器，必须使用元素选择器开头
```html
<head>
<style>
    div.red{
        color:red;
    }
</style>
</head>
<body>
    <div class="red">这里是div</div>
    <P class="red">这里是P标签</P>
</body>
```
#### 并集选择器
同时选中多个选择器对应的元素
语法：选择器1，选择器2，选择器3，选择器N｛｝
例子：#bi,h1,p,div{}
```html
<head>
<style>
    div，p{
        color:red;
    }
</style>
</head>
<body>
    <div class="red">这里是div</div>
    <P class="red">这里是P标签</P>
</body>
```
#### 关系选择器
###### 关系描述
父元素：
        -直接包含子元素的元素叫父元素
子元素：
        —直接被父元素包含的元素叫子元素
祖先元素：
        -直接或间接包含后代元素的元素叫祖先元素
        -一个元素的父元素也是它的祖先元素
后代元素
        -直接或间接被祖先元素包含的元素叫后代元素
        -一个元素的子元素也是它的后代元素
兄弟元素
        -拥有相同父元素的元素是兄弟元素
#####  子元素选择器：
选中指定父元素的子元素
语法：父元素>子元素
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* 
        为div的子元素设置一个字体颜色红色
        子元素选择器：选中指定父元素的子元素
        语法：父元素>子元素
        */
        div.box>span{
            color: crimson;
        }
    </style>
</head>
<body>
   
    <div class="box">
        这里是div
        <P >
            这里是div里的P标签
            <span>这里是p里的span标签</span>
        </P>
        <span>这里是div里的span标签</span>
    </div>
    <div>
        这里是div
        
        <span>这里是第一个div外的span标签</span>
    </div>
    
</body>
</html>
```
##### 后代元素选择器：
选中指定元素的指定后代元素        
语法：祖先 （空格）后代
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /*
         后代元素选择器：
         选中指定元素的指定后代元素        
         语法：祖先 （空格）后代
         */
         div span{
             color: crimson;
         }
    </style>
</head>
<body>
  
    <div class="box">
        这里是div
        <P >
            这里是div里的P标签
            <span>这里是p里的span标签</span>
        </P>
        <span>这里是div里的span标签</span>
    </div>
    <div>
        这里是div
        
        <span>这里是第一个div外的span标签</span>
    </div>
    
</body>
</html>
```
##### 并列标签选择器
###### 选择下一个兄弟
语法：前一个+下一个

###### 选择下方所有的兄弟
语法：兄~弟 
例子：
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
         /*
          选择下一个兄弟
          语法：前一个+下一个
          */
          p+span{
              color: crimson;
          }
          /*
          选择下方所有的兄弟
          语法：兄~弟 
           */
           P~span{color: crimson;}
    </style>
</head>
<body>
    <div class="box">
        这里是div
        <P >
            这里是div里的P标签
            <span>这里是p里的span标签</span>
        </P>
        <span>这里是div里的span标签</span>
    </div>
    <div>
        这里是div
        <span>这里是第一个div外的span标签</span>
    </div>
    
</body>
</html>
```
#### 属性选择器
[属性名]选择含有指定属性的元素
[属性名=属性值]选择含有指定属性值的元素
[属性名^=属性值]选择属性值以指定属性值开头的元素
[属性名$=属性值]选择属性值以指定属性值结尾的元素
[属性名*=属性值]选择属性值含有指定属性值的元素
例子：
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /*
        [属性名]选择含有指定属性的元素
        [属性名=属性值]选择含有指定属性值的元素
        [属性名^=属性值]选择属性值以指定属性值开头的元素
        [属性名$=属性值]选择属性值以指定属性值结尾的元素
        [属性名*=属性值]选择属性值含有指定属性值的元素
         */
        p[title]{
            color: crimson;
        }
        p[title=abc]{
            color: crimson;
        }
        p[title^=abc]{
            color: crimson;
        }
    </style>
</head>
<body>
    <h1 title="abc">将进酒</h1>
    <p title="abcde">君不见黄河之水天上来，奔流到海不复回 </p>
	<p title="deabc">君不见高堂明镜悲白发，朝如青丝暮成雪。</p>
	<p>人生得意须尽欢，莫使金樽空对月。</p>
	<p>天生我材必有用，千金散尽还复来。</p>
</body>
</html>
```
#### 伪类选择器
伪类：不存在的类，特殊的类。用来描述元素的特殊状态。比如：第一个子元素，被点击的元素，鼠标处在上面的元素。
伪类一般以：开头
##### 常用的伪类选择器
第一个子元素 ：first-child
最后一个子元素：last-child 
第n个子元素:nth-child(n) 
n=n是选中除第零个元素之外的所有元素
n=2n或n=even表示偶数元素
n=2n+1或n=odd表示奇数元素  
 以上几个伪类都是根据所有元素的顺序排列的 
:first-of-type
:last-of-type
:nth-of-type()
这几个和上面三个功能相似，但是是根据同类一元素的顺序进行排列的
##### 否定伪类选择器 
:not()去除满足条件的元素
示例：
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* 将ul里第一个li设为红色 */
        /* 第一个子元素 ：first-child*/
        ul>li:first-child{
            color: brown;
        }
        /* 最后一个子元素：last-child */
        ul>li:last-child{
            color: red;
        }
        /* 
        第n个子元素:nth-child(n) 
        n=n是选中除第零个元素之外的所有元素
        n=2n或n=even表示偶数元素
        n=2n+1或n=odd表示奇数元素        */
        ul>li:nth-child(1){
            color: red;
        }
        /* 以上几个伪类都是根据所有元素的顺序排列的 */
        :first-of-type
        :last-of-type
        :nth-of-type()
        /* 这几个和上面三个功能相似，但是是根据同类一元素的顺序进行排列的 */
         /* 否定伪类选择器 */
        ul>li:not(:nth-child(3)){
            color: seagreen;
        }
    </style> 
</head>
<body>
    <ul>
        <span>第一个span</span>
        <li>第一个</li>
        <li>第二个</li>
        <li>第三个</li>
        <li>第四个</li>
        <li>第五个</li>
    </ul>
</body>
</html>
```
##### a元素的伪类（超链接）
超链接可以分为特殊状态：
1.访问过的超链接
2.没有访问过的超链接
：link 表示没有访问过的链接（正常的链接） （a独有）
:visited表示是访问过的链接 （a独有）
由于隐私原因，这个伪类只能修改链接的颜色，不能修改其他字体大小等属性
：hover表示鼠标移入的状态
:active表示鼠标点击
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
       a:link{
           color: seagreen;
       }
       /* :link表示没访问过的链接 */
       a:visited{
           color: sienna;
       }
       /* :visited表示是访问过的链接 
       由于隐私原因，这个伪类只能修改链接的颜色，不能修改其他字体大小等属性*/
       /* ：hover表示鼠标移入的状态 */
       a:hover{
           color: skyblue;
           font-size: 50px;
       }
       /* :active表示鼠标点击 */
       a:active{
           color: springgreen;
       }
    </style>
</head>
<body>
    <a href="http://www.baibu.com">baidu（访问过）</a>
    <br>
    <a href="http://www.baidu123.com">baidu123（没访问过）</a>
</body>
</html>
```
#### 伪元素
伪元素：不真实存在的元素，特殊的位置的元素。
伪元素使用::开头
::first-letter表示第一个字母（字符）
::first-line表示第一行
::selection表示选中的文本

::before表示元素开始的位置
::after表示元素结束的位置
     -->必须配合属性content来使用
     这两个应用很多，是重点内容
例子：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        P{
            font-size: 20px;
        }
        /* ::first-letter表示第一个字母（字符） */
        p::first-letter{
            font-size: 50px;
        }
        /* ::first-line表示第一行 */
        p::first-line{
            font-size: 50px;
        }
        /* p::selection表示选中的文本 */
        p::selection{
            background-color: springgreen;
        }
        div::before{
            content: "123";
            color: tan;
        }
        div::after{
            content: "hh";
            color: blue;
        }
    </style>
</head>
<body>
    <div>hello ,how are you.</div>
    <p>这是一个段落</p>
</body>
</html>
```
### 样式的继承
继承：为一个元素设置的样式会被应用到其后代元素身上
继承是发生在祖先和后代元素之间
继承是为了方便进行开发
并不是所有的样式都会被继承，比如背景，布局等元素。
### 选择器的权重
#### 样式的冲突：
当我们通过不同选择器，选择相同的元素，并且为其设置不同的样式（不同的值），此时发生样式冲突。
发生样式冲突时由选择器权重（优先级）决定。(选择器越具体权重越高)
#### 选择器的权重值：
内联样式          优先级：1000
ID选择器          优先级：0100
类和伪元素选择器   优先级：0010
元素选择器        优先级: 0001 
统配选择器         优先级：0000
继承的样式         没有优先级
比较优先级时要将所有选择器的优先级进行相加计算，最后优先级越高，越优先显示。（分组选择器是单独计算的）
选择器再累加也不会超过其最大数量级
优先级相同，后面的会覆盖前面的。
例子：
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div{
            color: red;

        }
        .red{
            color: white;
        }
/* 这里会优先变为白色 */
    </style>
</head>
<body>
    <div id=box1 class="red">第一个div </div>

</body>
</html>
```
可以在样式后面加一个！important，则此时该样式会获取到最高的优先级，甚至超过内联样式。
例：
```css
<style>
        div{
            color: red !important;

        }
        .red{
            color: white;
        }
</style>
/* 优先变为红色 */
```
### 像素和百分比
显示器是由一个个小方格组成的
不同屏幕的像素的大小是不同的，像素点越小的屏幕越清晰。
所以同样的200px在不同 的设备下显示效果不一样。
#### 像素的单位
##### px表示像素：
200px  300px
##### 百分比
将属性值设置为相对于父元素的百分比
例子：
后面两个.box2的效果是一样的
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            width: 200px;
            height: 200px;
            background-color: turquoise;
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: yellow;
        }
        .box2{
            width: 50%;
            height: 50%;
            background-color: yellow;
        }
/* 后面两个.box2的效果是一样的 */
    </style>
</head>
<body>
    <div class="box1">
        <div class="box2"></div>
    </div>
</body>
</html>
```
#### em和rem
em是相对于自身字体大小大小来计算的
1em=1font-size(默认为16)
rem是相对于根元素（html）字体大小来计算的（移动端用的多）
 例：
 ```css
 .box3{
            font-size: 30px;
            width: 10em;
            /* 相当于300px */
            height: 10em;
            background-color: tomato;
        }
 ```
### 颜色单位
在css里可以直接使用颜色来设置各种颜色(不方便）
##### RGB值
RGB通过三种颜色的不同浓度来调配出不同颜色
R：red
G:green
B:blue
每一种颜色的范围都在0-255之间
语法：RGB（红色，绿色，蓝色）
这里是光的三原色：所以都为0时为黑色，都为255为白色
##### RGBA

A:在RGB基础上多一个不透明效果（1不透明——0完全透明）
##### 十六进制的RGB值
语法：#红色绿色蓝色
颜色浓度：00-ff
 如果符号两位两位相同，可以简写：#aabbcc -->#abc
##### HSL值和HSLA值
H：色相（0~360）
S：饱和度  颜色浓度（0%——100%）
L：亮度    颜色的亮度（0%——100%）
A:不透明度
例子：
```css
<style>
        .box{
            width: 100px;
            height: 100px;
            color: rgb(255, 0, 0);
            color: rgba(red, green, blue, alpha);     
            color: hsl(hue, saturation, lightness); 
            color: hsla(hue, saturation, lightness, alpha);     
        }

    </style>
```
### 布局
#### 文档流（normal flow）
网页是一个多层结构，一层摞着一层
通过css可以分别为每一层来设置样式
作为用户来讲只能看见最上面一层(ps图层的概念)
这些层中最底下一层称为文档流，文档流是网页的基础，我们创建的元素默认都是在文档流中进行排列的
元素有两个状态：在文档流中，和不在文档流中（默认在）
##### 元素在文档流中的特点
###### 块元素
块元素独占一行（自上向下垂直排列  ）
默认宽度是父元素的全部（把父元素盛满）
默认高度是被内容撑开（子元素），比如子元素是一行字，那高度默认就是一行字的高度
###### 行内元素
行内元素不独占一行，只占自身大小。
行内元素在页面中从左往右水平排列，如果一行之中不能全部容纳，就会自动换行继续自左向右排列
行元素的默认宽度和高度都是被内容撑开。

#### 盒模型 框模型（box model）
css将页面中的所有元素设置为了一个矩形的盒子
将元素设置为矩形的盒子后，对页面布局就是将不同的盒子摆放到不同的位置
每一个盒子都由以下几个部分组成：
##### 内容区：（content）
元素中的所有子元素和文本内容都在内容区中排列，内容区的大小由width和height两个属性设置。
width:宽度
height：高度
##### 边框（border）:边框的大小会影响到整个盒子的大小 
设置边框，至少需要设置三个样式、
###### 边框的宽度：border-width
可以不写，默认是三个像素。用来指定四个方向边框的宽度。
可以这么写（四个值）：border-width：10px 20px 30px 40px;
三个值：border-width：10px（上） 20px（左右）  40px（下）;
两个值：border-width：10px（上下） 20px（左右）；
一个值：border-width：10px（上下左右）;
除了border-width还有一组：border-XXX-width，XXX可以是top right bottom left；可以分别指定某一个边的宽度。

###### 边框的颜色：border-color
用于指定四个边框的颜色：可以写四个值，三个值......和上面的border-width相似
也可以不写，默认为color（字体）的颜色
###### 边框的样式：border-style
solid：表示实线
dotted:表示点状虚线
dashed:虚线
double：双实线
同样有四个值，同样可以具体指定一个边的样式同border-width
border-style的默认值为none(没有边框)
###### border的简写
```css
 border-width: 10px;
            border-color: coral;
            border-style: solid;
```
可简写为：
``` css
 border:10px coral solid;
```
这三个值的顺序是可以发生变化的，同样border-XXX也可以这么写三个值。

###### 内边距（padding）
内容和边框的距离，一共有四个方向的内边距
padding-top
padding-right
padding-bottom
padding-left
内边距的设置会影响盒子的大小，背景颜色会延伸到内边距上。
例子：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
      .box1{
          width: 200px;
          height: 200px;
          background-color: coral;
          border: rgb(200, 206, 117) 10px solid;
          padding-top: 20px;
          padding-right: 20px;
          padding-bottom: 20px;
          padding-left: 20px;
        }
      .box2{
            /* 用box2来显示内容真实大小 */
            width: 100%;
            height: 100%;
            background-color: darkcyan;
        }
    </style>
</head>
<body>
    <div class="box1">
        <div class="box2">内容部分的真实大小</div>
    </div>
</body>
</html>
```
**一个盒子的可见框大小**：由内容区 内边距 边框共同决定。计算盒子大小时，需要将这三个区域加到一起计算。
padding可以简写：
padding：20px 30px 40px 50px;(和border的简写相同)

###### 外边距（margin）
外边距不会影响可见框的大小。但是会影响盒子实际占地位置。
一共有四个方向的外边距
margin-top
-上外边距：设置一个正直，元素会向下移动
margin-right
-右外边距（默认情况下设置它不会有任何效果）
margin-bottom
-下外边距，设置一个正值，元素会向右移动。
margin-left
-左外边距：设置一个正值，元素会向右移动

如果是负值则往相反方向走。
元素在页面中是按照自左向右的顺序排列
所以默认情况下设置左和上外边距则会移动元素自身，
margin-top    margin-left
而设置下和右边距会移动其他元素（挤别人）
margin-right    margin-bottom

margin同样可以进行简写，和和border的简写相同
例：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            width: 200px;
            height: 200px;
            background-color: darkturquoise;
            border: gray 20px solid;
            margin-top: 100px;
            margin-left: 100px;
            margin-bottom: 100px;
        }
        .box2{
            width: 200px;
            height: 200px;
            background-color: rgb(90, 194, 137);
            border: rgb(91, 201, 201) 20px solid;

        }
    </style>
</head>
<body>
    <div class="box1">  </div>
    <div class="box2"></div>
    
</body>
</html>
```
##### 盒子的水平布局
元素在其父元素中的水平方向位置由以下几个属性共同决定
margin-left
border-left
padding-left
width
margin-right
border-right
padding-right
**一个元素在其父元素中，水平布局必须要满足以下等式：**
margin-left+border-left+padding-left+width+margin-right+border-right+padding-right=其父元素区的宽度（必须满足）
**如果没满足就称为过渡约束，浏览器会默认进行调整。**

调整规则：如果这七个值里没有为auto的情况，则浏览器会自动调整margin-right（右外边距）到满足等式
这七个值里有三个值可以设置为auto：
width
margin-left
margin-right
如果某个值为auto，则浏览器自动调整auto的值以使等式满足。(width的值如果不写，默认就是auto)
如果将一个一个宽度和一个外边距设置为auto，则宽度自动最大，设置为auto外边距会自动变为0;
如果将三个值都设置为auto，则外边距都是0，宽度最大
如果将两个外边距设置为auto，宽度值固定，则两外边会相等：利用这个特点给元素水平居中
示例：
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .outer{
            width: 800px;
            height: 200px;
            border: lightcoral 10px solid;

        }
        .inner{
            width: 200px;
            height: 200px;
            background-color: rgb(73, 126, 59);
            margin-left: auto; 
            margin-right: auto;
        }
    </style>
</head>
<body>
    <div class="outer">
        <div class="inner"></div>
    </div>
</body>
</html>
```
##### 盒子垂直方向的布局
垂直布局比较简单:默认情况下不指定高度父元素的高度会被内容撑开

子元素是在父元素的内容中排列的
如果子元素的大小超过了父元素，则子元素会从父元素中溢出
使用overflow来设置父元素如何处理溢出的子元素
可选值：
visible默认值  会溢出，在父元素外边显示
hidden 溢出内容不显示，直接裁剪掉
scroll 生成两个滚动条
auto   根据需要生成滚动条
还可以使用overflow-x 或overflow-y来单独设置x和y 方向的溢出问题

##### 盒子模型外边距的折叠
相邻方向垂直外边距会发生重叠现象
**兄弟元素**
兄弟元素间的相邻外边距会取两者之间的一个较大值(两者都是正值)
特殊情况：相邻的外边距一正一负，取两者的和
如果两个外边距都是负值，则取两者中绝对值较大的
兄弟元素外边距的重叠对开发是有利的，所以不需要处理
**父子元素**
父子元素间相邻外边距，子元素的会传递给父元素（上外边距）
父子外边距的折叠会影响到页面的布局，必须要进行处理

##### 行内元素的盒模型
行内元素不支持设置宽度和大小 
可以设置padding，但垂直方向不会影响页面的布局
可以设置border，但垂直方向不会影响页面的布局。
可以设置margin，但垂直方向的margin不影响页面布局

例子：
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .s1{
            background-color: coral;
            width: 100px;
            height: 100px;
            /*行内元素不支持设置宽度和大小 */
            padding: 100px;
            /* 可以设置padding，但垂直方向不会影响页面的布局 */
            
        }
        .box1{
            background-color: cyan;
            width: 200px;
            height: 200px;
        }
    </style>
</head>
<body>
    <span class='s1'>This is a span </span>
    <div class="box1"></div>
</body>
</html>
```

超链接是行内元素，如果要设置它的宽高可以使用display属性（少用）
        block   -->将元素设置为块元素
        inline-block-->将元素设置为行内块元素（既可以设置宽高，有不会独占一行）
        table   -->将元素设置为表格
        none    -->元素不在页面里显示       

visibility属性：可以设置元素的可见状态
可选值：visible默认值，元素在页面里正常显示
       hidden   元素在页面中隐藏不显示，但依然占据位置

##### 浏览器的默认样式
通常情况下，浏览器会为元素设置一些默认样式
默认样式会影响到页面的布局，通常情况下编写网页必须要去除浏览器的默认样式（pc端页面）
可以具体针对元素进行设置：
例如：
``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            width: 100px;
            height: 100px;
            border: solid 1px black;
        }
       
        body{
            margin:0px;
        }
        p{
            margin: 0px;
            /* 去除p标签之间的外边距 */
        }
        ul{
            margin: 0px;
            padding: 0;
            list-style: none;
            /* 去除项目符号 */
        }
        
    </style>
</head>
<body>
    <div class="box1"></div>
    <p>这是一个段落</p>
    <p>这是一个段落</p>
    <p>这是一个段落</p>
    <p>这是一个段落</p>
    <p>这是一个段落</p>
    <ul>
        <li>1</li>
        <li>2</li>
        <li>3</li>
    </ul>
</body>
</html>
```
但简单考虑：一般写为：

```html
*{
    margin:0;
    padding:0;

}
```
这个方法不够完美，可能去除不干净，所以要把所有的标签都看一遍，都重置一遍，这时候可以引入一个完整的重置样式表的外部CSS文件
重置样式表网上很多，现成且可用

##### 盒子的大小                    
 默认情况下，盒子可见框的大小由内容区，内边距和边框共同决定 
box-sizing: content-box; 
box-sizing用于设置盒子尺寸的计算方式（width，height的作用）
可选值：
content-box  默认值，宽度和高度用来设置内容区的大小
border-box  宽度，高度用来设置盒子可见框的大小。
例子：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            width: 100px;
            height: 100px;
            background-color: #bfc;
            padding: 10px;
            border: 10px red solid;
            /* 默认情况下，盒子可见框的大小由内容区，内边距和边框共同决定 */
            box-sizing: content-box;
            /* 
            box-sizing用于设置盒子尺寸的计算方式（width，height的作用）
            可选值：
            content-box  默认值，宽度和高度用来设置内容区的大小
            border-box  宽度，高度用来设置盒子可见框的大小。
             */
        }

    </style>
</head>
<body>
    <div class="box1"></div>
    
</body>
</html>
```
##### 轮廓阴影和圆角
outline用来设置元素的轮廓线，用法和border一样，和边框不同，轮廓不会影响到可见框的大小 
box-shadow用来设置元素的阴影效果，阴影不会影响页面布局
            第一个值：水平偏移量  正值阴影朝右偏移
            第二个值：垂直偏移量  正值阴影朝下偏移
            第三个值：阴影的模糊半径
            第四个值：颜色
border-radius用来设置圆角，值为圆角半径大小
             border-radius可以分别指定四个角的圆角
             四个值：左上 右上 右下 右上
             三个值：左上 右上/左下 右下 
             两个值：左上/右下 右上/左下 
            还有单独写法
            border-top-left-radius: 
            左上角
            border-top-right-radius: 
            右上角
            border-bottom-left-radius: 
            左下角
            border-bottom-right-radius: 
            右下角
            将元素设置为圆形：可以这样写：
            border-radius：50%;
例子：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            width: 100px;
            height: 100px;
            background-color: cadetblue;
            border: 10px red solid;
            outline: solid 10px solid
            /* outline用来设置元素的轮廓线，用法和border一样，和边框不同，轮廓不会影响到可见框的大小 */
        }
        .box1{
            box-shadow: 10px 10px 10px rgb(0, 0, 0,0.4);
            /*box-shadow用来设置元素的阴影效果，阴影不会影响页面布局
              */
        }
        .box2{
            width: 200px;
            height: 200px;
            background-color: silver;
            border-radius: 20px;
        }
    </style>
    
</head>
<body>
    <div class="box1"></div>
    <div class="box2"></div>
</body>
</html>
```
#### 浮动
##### 浮动的介绍
CSS 的 Float（浮动），会使元素向其父元素左或向右移动，其周围的元素也会重新排列。
使用float:属性来设置元素的浮动
可选值：
none：默认值，不浮动。
left：元素向左浮动
right：元素向右浮动
元素设置浮动后，元素水平方向布局的等式便不需要强制成立
元素设置浮动后，会完全从文档流中脱离，不在占用文档流的位置，所以元素下边的还在文档流中的元素会自动向上移动。
浮动特点：
1.元素设置浮动后，会完全从文档流中脱离
2.元素设置浮动后，会使元素向其父元素左或向右移动
3.浮动元素，默认不会从父元素中移出
4.一个浮动元素会尽量向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止，不会盖住其他浮动元素。
5.如果浮动元素的上边是一个没有浮动的块元素，则浮动元素无法上移
6.浮动元素不会超过它前一个浮动的兄弟元素，最多最多就是和他一样高。

浮动的主要作用是让页面中的元素可以水平排列
通过浮动可以制作一些水平方向的布局
##### 浮动的其他特点：
浮动元素不会盖住文字，文字会自动环绕在浮动元素的周围，所以可以利用浮动来设置文字环绕图片的效果
语速设置浮动，从文档流中脱离，元素的一些特点也会发生改变

元素脱离文档流的特点：
块元素
1.块元素不会独占页面的一行
2.脱离文档流，块元素的宽度和高度都会被内容撑开
行内元素
行内文档脱离文档流以后会变为块元素，特点和块元素一样
脱离文档流以后，就不需要区分行内和块元素了

#### 网页的布局
header网页头部
main网页主体
footer网页的底部
布局示例：
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>网页的布局</title>
    <style>
         *{
            margin:0;
            padding:0;
            list-style: none;
        }
        header{
            width: 1000px;
            height: 200px;
            margin: 0px auto;
            background-color: chocolate;
            
        }
        main{
            width: 1000px;
            height: 700px;
            margin: 10px auto;
            background-color: rgb(160, 32, 28);
            
        }
        nav{
            width: 200px;
            height: 100%;
            background-color: cornflowerblue;
            float: left;
        }
        article{
            width: 580px;
            height: 100%;
            background-color: darkgoldenrod;
            float: left;
            margin: 0px 10px;
        }
        aside{
            width: 200px;
            height: 100%;
            background-color: darkkhaki;
            float: left;
        }

        footer{
            width: 1000px;
            height: 200px;
            margin: 0px auto;
            background-color: rgb(112, 89, 72);
        }

    </style>
</head>
<body>
    <header>
        <!-- 网站的头部 -->
    </header>
    <main>
        <!-- 网站的主体 -->
        <nav>
            <!-- 左边导航栏 -->
        </nav>
        <article>
            <!-- 中间内容 -->
        </article>
        <aside>
            <!-- 右边侧栏 -->
        </aside>
    </main>
    <footer>

    </footer>
</body>
</html>
```
#### 高度塌陷问题
在浮动布局里，父元素的高度是默认被子元素撑开的，
当子元素浮动后，会完全脱离文档流，子元素从文档流中脱离
将会无法撑起父元素的高度，导致父元素的高度丢失
父元素的高度塌陷后其下的元素会自动上移，导致页面布局混乱
所以高度塌陷是浮动布局中一个比较常见的问题这个问题必须进行处理

##### BFC（块级格式化环境）
bfc是一个css中的一个隐含的属性，可以为一个元素开启BFC
开启BFC该元素会变成一个独立的布局区域
元素开启BFC后的特点
1.开启BFC的元素不会被浮动元素覆盖
2.开启BFC的元素子元素和父元素的外边距不会重叠
3.开启BFC的元素可以包含浮动的子元素
可以通过一些特殊的方式开启BFC
1.设置元素的浮动（不推荐）
2.将元素设置为行内块元素（不推荐）
3.将元素的overflow设置为非visible的值
    常用方式：为元素设置overflow：hidden  开启BFC

##### clear
如果不希望某个元素因为其他浮动元素的影响改变位置，可以通过clear属性清除浮动元素的当前元素所产生的影响
clear：清除浮动元素对当前元素的影响
可选值：
left：清除左侧浮动元素对当前元素的影响
right：清除右侧浮动元素对当前元素的影响
both:清除两侧影响最大的那侧
原理：设置清除浮动后，浏览器会自动为元素设置一个上外边距，以使其位置不受其他元素的影响

##### 使用after伪类来解决高度塌陷问题
最好用的方法
例子：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            border: chocolate 10px solid;
        }
        .box2{
            width: 200px;
            height: 200px;
            background-color: cornflowerblue;
            float: left;
        }
        .box1::after{
            content: '';
            clear: both;
            display: block;
            /* 转换为块元素 */
        }
    </style>
</head>
<body>
    <div class="box1">
        <div class="box2"></div>
       
    </div>
    
</body>
</html>
```
##### clearfix
最终解决方案：clearfix
例子：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            width: 200px;
            height: 200px;
            background-color: cornflowerblue;
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: darkorange;
            margin-top: 100px;
        }
        /* clearfix这个样式可以同时解决高度塌陷和外边距重叠的问题 */
        .clearfix::before,.clearfix::after{
            content: '';
            display: table;
            clear: both;
        }
    </style>
</head>
<body>
    <div class="box1 clearfix">
        <div class="box2"></div>
    </div>
</body>
</html>
```
#### 定位
##### 定位的介绍
定位是一种更加高级的布局手段
通过定位可以将元素放到页面的任何位置
使用position属性来设置定位
    可选值：static       默认值，元素是静止的没有开启定位
           relative     开启元素的相对定位
           absolute     开启元素的绝对定位
           fixed        开启元素的固定定位
           sticky       开启元素的粘滞定位

##### 相对定位
将position属性设置为relative时则开启相对定位

相对定位特点：
        1.如果元素开启相对定位后，如果不设置偏移量则元素不会发生任何的变化
        2.相对定位是参照于元素在文档流中的位置进行定位的
        3.相对定位会提高元素的层级
        4.相对定位不会脱离文档流

偏移量（offset）
    垂直方向：通常情况下使用一种
        top：定位元素和定位位置上边的距离。
        bottom：定位元素定位位置上边的距离。
    水平方向：
        lift：定位元素和定位位置左边的距离。
        right：定位元素和定位位置右边的距离。
例子：
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div{
            font-size: 60px;
        }
        .box1{
            width: 200px;
            height: 200px;
            background-color: cadetblue;
        }
        .box2{
            width: 200px;
            height: 200px;
            background-color: rgb(95, 160, 106);
            position: relative;
            bottom: 200px;
            left:200px;
        }
        .box3{
            width: 200px;
            height: 200px;
            background-color: rgb(214, 109, 61);
        }
    </style>
</head>
<body>
    <div class="box1">1</div>
    <div class="box2">2</div>
    <div class="box3">3</div>
</body>
</html>
```
##### 绝对定位
将position属性设置为absolute时则开启绝对定位
绝对定位特点：
        1.如果元素开启绝对定位后，如果不设置偏移量则元素位置不会发生变化
        2.绝对定位会脱离文档流
        3.绝对定位会改变元素的性质，行内变成块，块的宽高被元素撑开
        4.绝对定位会使元素提示一个层级
        5.是相对于其包含块进行定位的
        包含块：（containing block）
            正常情况下：
                包含块就是当前元素最近的祖先块元素
            绝对定位的包含块：
            包含块就是离他最近的开启了定位的祖先元素，如果所有祖先元素都没有开启定位，则根元素就是它的包含块。
            html（根元素  ，初始包含块）

偏移量（offset）
    垂直方向：通常情况下使用一种
        top：定位元素和定位位置上边的距离。
        bottom：定位元素定位位置上边的距离。
    水平方向：
        lift：定位元素和定位位置左边的距离。
        right：定位元素和定位位置右边的距离。

例子：
```css
 .box2{
            width: 200px;
            height: 200px;
            background-color: rgb(95, 160, 106);
            position: absolute;
            top: 0px;
            left:0px;
```
##### 固定定位
（网页固定广告，导航栏等）
将position属性设置为fixed时则开启绝对定位
固定定位也是一种绝对定位，所以固定定位的大部分特点都和绝对定位一样
唯一不同是固定定位永远参照浏览器的视口进行定位

##### 粘滞定位
(兼容性不好)
将position属性设置为sticky时则开启粘滞定位
粘滞定位和相对定位的特点基本一致
粘滞定位和相对定位可以在元素到达某个位置时将其固定

##### 绝对定位元素的位置
开启绝对定位以后：
水平方向的布局等式就需要添加left和right两个值
        lift+margin-left+border-left+padding-left+width+margin-right+border-right+padding-right+right=其父元素区的宽度（必须满足）
        和以前一样只是多了两个值
        发生过度约束时，没有auto时，则自动调整right值以使等式满足。
        如果有auto，则自动调整auto的值以使等式满足
        可设置auto的值：
            margin width left right 
            left right 默认为auto，等式不满足优先调整这两个值
这样可以写水平方向的居中：（在包含块里居中）
        left:0;
        right:0;
        margin-right:auto;
        margin-lift:auto;

垂直方向的等式也必须要满足：
        top+margin-top/bottom+padding-top/bottom+border-top/bottom+bottom=父元素高度
        同样auto的值会自动调整
这样可以写垂直方向的居中：（在包含块里居中）
        margin-top:auto;
        margin-bottom:auto;
        top:0;
        bottom:0;
例子：水平垂直居中
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            width: 500px;
            height: 500px;
            background-color: cadetblue;
            position: relative;
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: chocolate;
            position: absolute;
            left: 0;
            right:0;
            margin-right:auto;
            margin-left:auto;
            margin-top:auto;
            margin-bottom:auto;
            top:0;
            bottom:0;
        }

    </style>
</head>
<body>
    <div class="box1">
        <div class="box2"></div>
    </div>
</body>
</html>
```
#### 元素的层级
对于开启了定位的元素，可以通过z-index属性来指定元素的层级
    z-index需要一个整数做参数，数值越大元素的层级越高
        元素的层级越优先显示
    没有参数（参数相同）优先显示结构里最下面的元素。
祖先元素的层级再高，也不会遮盖住后代元素
例子：
``` html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        div{
            font-size: 60px;
        }
        .box1{
            width: 200px;
            height: 200px;
            background-color: cadetblue;
            position: absolute;
            z-index: 1;
        }
        .box2{
            width: 200px;
            height: 200px;
            background-color: rgba(209, 196, 73, 0.5);
            position: absolute;
            top: 50px;
            left: 50px;
            z-index: 2;
        }
        .box3{
            width: 200px;
            height: 200px;
            background-color: rgb(214, 109, 61);
            position: absolute;
            top: 100px;
            left: 100px;
            z-index: 3;
        }
        .box4{
            width: 100px;
            height: 100px;
            background-color: rgb(88, 76, 70);
            position: absolute;
            z-index: 100;
        }
    </style>
</head>
<body>
    <div class="box1">1</div>
    <div class="box2">2</div>
    <div class="box3">3
        <div class="box4">4</div>
    </div>
</body>
</html>
```
#### font
##### 字体相关样式：
color  用来设置字体颜色
font-size  用来设置字体大小
    font-size相关单位：
        em相对于当前元素的一个font-size
        rem相当于根元素的一个font-size
font-family字体族（字体的格式）
        可选值： serif（衬线字体）
                sans-serif（非衬线字体）
                monospace（等宽字体）
                    指定字体的类别，可以指定多种字体，使用，隔开，浏览器会自己按顺序选择其中电脑上有的字体显示
font-face可以将服务器中的字体直接提供给用户去使用 问题：1.加载可能比较慢  2.版权   
例子：
```css
 @font-face {
            font-family:这是字体名字;
            /*   font-family 字体名字 */
            src: url(路径) format（"格式声明"）;
            /* 服务器上字体的路径 */
```
##### 图标字体
    网页里经常使用一些图标，可以通过图片来引入图标
    但是图片大小本身太大，并且非常不灵活
    -所以在使用图标时，我们可以将图标直接设置为字体
    然后通过font-size的形式来引入
    这样我们就可以通过字体的形式来使用图标
    
    Font Awesome：
        免费的字体图标库https://fontawesome.com/
        下载解压后
        将css文件和webfonts移动到项目中（这两必须在同一级目录）
        将CSS文件引入到网页中
        使用图标字体：
            直接通过使用类名来使用图标字体（通常使用i标签来表示字体图标）
    
        其他用法，可以通过伪元素来设置字体图标：
        ``` html
         li::before{
            content: '\f1b0';
            font-family: 'Font Awesome 5 Free';
            font-weight: 900;
        }
        ```
        也可以通过实体来引入符号
        ```html
        <span class="fas"> &#xf0f3; </span>
        ```
##### 行高（line height）
行高是文字占有的实际的高度
可以通过line height设置行高
    行高可以指定大小（px em），也可以为行高设置一个整数,行高会是字体大小的指定倍数（默认行高1.33）

字体框：字体框就是字体存在的格子，设置font-size就是在设置字体框的高度

行高会在字体框里平均分配
    可以将行高设置为与元素高度一样，使得单行文字在元素中垂直居中
    行高还可以用来设置文字的行间距
        行间距=行高-字体的大小

##### 字体的简写属性
font可以设置字体相关的所有属性
    格式：
        font：字体大小/行高  字体族
        行高可以省略。不写则使用默认值

font-weight  字重  字体的加粗
    可选值：normal 默认值
            bold  加粗
            100-900（九个级别，没啥用）
font-style：  字体样式
    可选值：normal 正常的
           italic 斜体
##### 文本的样式
text-align  文本的水平对齐
    可选值: 
            left 左侧对齐
            right 右对齐
            center 居中对齐
            justify两端对齐

vertical-align：元素的垂直对齐            
    可选值：
            baseline(基线对齐)
            top    顶部对齐
            bottom  底部对齐
            center  居中对齐

text-decoration可以用来设置文本的修饰
    可选值：
        none：默认值，不添加任何修饰，正常显示
        underline 为文本添加下划线
        overline 为文本添加上划线
        line-through 为文本添加删除线

white-space:设置网页如何处理空白
    可选值：
        normal  正常
        nowrap  不换行
        pre 保留空白

#### 背景
设置背景样式
##### 设置背景颜色：
background-color: #bfa;
##### 设置背景图片：
使用background-image来设置背景图片
    - 语法：background-image:url(相对路径);     
    - 如果背景图片大于元素，默认会显示图片的左上角
    - 如果背景图片和元素一样大，则会将背景图片全部显示
    - 如果背景图片小于元素大小，则会默认将背景图片平铺以充满元素
background-image:url(img/1.png);
可以同时为一个元素指定背景颜色和背景图片，
这样背景颜色将会作为背景图片的底色
一般情况下设置背景图片时都会同时指定一个背景颜色
##### 设置背景图片的重复方式
background-repeat用于设置背景图片的重复方式
可选值：
    repeat，默认值，背景图片会双方向重复（平铺）
    no-repeat ，背景图片不会重复，有多大就显示多大
    repeat-x， 背景图片沿水平方向重复
    repeat-y， 背景图片沿垂直方向重复
##### 设置背景图片的位置
background-position 用来设置背景图片的位置
设置方式：
        通过top bottom left right center几个方位来设置图片的位置
例子：background-position： bottom left;（至少两个值）

也可以直接指定两个偏移量，
第一个值是水平偏移量
    - 如果指定的是一个正值，则图片会向右移动指定的像素
    - 如果指定的是一个负值，则图片会向左移动指定的像素
第二个是垂直偏移量	
    - 如果指定的是一个正值，则图片会向下移动指定的像素
    - 如果指定的是一个负值，则图片会向上移动指定的像素
例子：background-position: -80px -40px;

##### 设置背景的范围
background-clip用于设置背景的范围
可选值： border-box  默认值，背景会出现在边框的下边
        padding-box 背景不会出现在边框，只出现在内容区和内边距
        content-box 背景只会出现在内容区
background-origin 背景图片的偏移量计算的原点
        padding-box  默认值background-position从内边距开始算
        content-box  background-position从内容区开始算
        border-box   background-position从边框开始算

##### 背景图片的尺寸
background-size来设置背景图片的尺寸
第一个值表示宽度
第二个值表示高度
-如果只写一个，则第二个默认为auto

写cover可以让图片比例不变，将元素铺满
contain图片比例不变，将图片在元素中完整显示

##### 背景图片的滚动
background-attachment用来设置背景图片是否随页面一起滚动（很少用）
 		可选值：
 			scroll，默认值，背景图片随着窗口滚动
  			fixed，背景图片会固定在某一位置，不随页面滚动

 不随窗口滚动的图片，我们一般都是设置给body，而不设置给其他元素

##### 背景属性的简写
  background(还是不简写的好，具体查文档)
  	- 通过该属性可以同时设置所有背景相关的样式
  	- 没有顺序的要求，谁在前睡在后都行
 		也没有数量的要求，不写的样式就使用默认值
例子：
background: #bfa url(img/3.png) center center no-repeat fixed;

##### 雪碧图
为了解决图片闪烁和加载问题
    可以将多个小图片统一保存到一个大图片中，然后通过调整background-position来调整显示位置
    这样图片可以同时加载到网页中，可以有效避免出现闪烁问题
    这个技术在网页运用十分广泛，称为CSS-sprite（现在在减少使用）
    使用：
    1.确定要使用的图标
    2.测量图标大小
    3.根据测量创建元素
    4.将图设置为元素的背景图片
    5.设置偏移量以显示对应图标

    特点：
    一次性加载多个图片，减少服务器请求，加快访问速度

##### 渐变
通过渐变可以设置一些复杂的背景颜色，可以实现一个颜色向其他颜色过渡的效果
    渐变是图片，需要使用background-image来设置
    （用法太多了）
线性渐变
   background-image: linear-gradient(to left ,red,yellow);
   三个值是渐变方向，开头颜色 ，结尾颜色
  （也可以同时指定多个颜色，多个颜色默认情况下平均分配）
径向渐变
    background-image: radial-gradient(red,yellow);
    从中间向西周散射，默认情况下，径向渐变的形状由元素形状决定
    可以手动指定方向：
        circle  正圆
        ellipse 椭圆





















### 练习
#### 01.图片列表
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>图片列表练习</title>
    <style>
        *{
            margin:0;
            padding:0;
            list-style: none;
        }
        body{
            background-color: #352929;
        }
        .box1{
            background-color:#f4f4f4;
            width: 190px;
            height: 626px;
            /* 设置ul的大小 */
            overflow: hidden;
            margin: 50px auto;
            /* 居中 */
        }
        .box li{
            margin-bottom: 10px;
        }
        .box1 img{
            width: 190px;
            /* 设置图片大小 */
        }     
    </style>
</head>
<body>
    <ul  class="box1">
        <li>
            <a href="https://prodev.jd.com/mall/active/24qWmGEbiPnPYxZzEfMj6ktgWxxR/index.html?babelChannel=ttt13&extension_id=eyJhZCI6IiIsImNoIjoiIiwic2hvcCI6IiIsInNrdSI6IiIsInRzIjoiIiwidW5pcWlkIjoie1wiY2xpY2tfaWRcIjpcIjEwMWQ0ZDE5LTRkZjMtNGFmMC1hMTdhLTc1MDVjOWM2ZTI1NFwiLFwibWF0ZXJpYWxfaWRcIjpcIjU1MDczOTM4NjlcIixcInBvc19pZFwiOlwiNDI3M1wiLFwic2lkXCI6XCJiNjZkMjQ2NC0yNDJhLTRiMTYtYjNmNS1hYmU4MmViYmJkMDlcIn0ifQ==&jd_pop=101d4d19-4df3-4af0-a17a-7505c9c6e254&abt=1">
                <img src="./素材/02.jpg" alt=""  width="300" >
            </a>
        </li>
        <li>
            <a href="https://pro.jd.com/mall/active/3uFvKuAQdDK1Npokcjv8tUj8tsmd/index.html?innerAnchor=100014348492&focus=4">
                <img src="./素材/q (1).jpg" alt="" width="300" >
            </a>
        </li>
        <li>
            <a href="https://pro.jd.com/mall/active/N9112CZB4v7aGVL7TKnmRQkevNY/index.html?innerAnchor=100014794825&focus=4">
                <img src="./素材/q (2).jpg" alt="" width="300">
            </a>
        </li>
        <li>
            <a href="https://channel-m.jd.com/pc/psp/100010264815?imup=CgYKABIAGAASHAjvkc7I9AIQoZPw3AMaCGN6eW13bGtqILMJKAEYsBsgACombWl4dGFnX2ksdWEseGdhLGdpYSxjaWUsZl9iYV9mbF9sMTYzMzIyCG1peHRhZ19pSqwBSXxNSVhUQUdfSVIsSV9BX0ZMX1IsSV9BX1JFX0xDLElfQV9QTF9MQyxJX0FfU0xfUixJX0FfQ1NfUixJX1VfRkxfTDE2NjI5LElfU19GTF9SLElfUl9GTF9SLElfUF9GTF9MMTYzNzIsSV9HX1hHX1IsSV9HX1JMX0xDLElfQl9GTF9SLEdJQSxYR0EsVUJ8O0Z8TUlYVEFHX0ZSLEZfQkFfRkxfTDE2MzMyfA&extension_id=eyJhZCI6IjM1MDQiLCJjaCI6IjIiLCJza3UiOiIxMDAwMTAyNjQ4MTUiLCJ0cyI6IjE2NDA2ODg3NDIiLCJ1bmlxaWQiOiJ7XCJjbGlja19pZFwiOlwiNGJjMzU2NWItNTJlNy00YjhkLTllN2MtOWMxNWQzY2FhMTQ2XCIsXCJtYXRlcmlhbF9pZFwiOlwiODA4NzQ1MDcwMzA2NzE5MTQ3OFwiLFwicG9zX2lkXCI6XCIzNTA0XCIsXCJzaWRcIjpcIjZlYWQwZTM0LTk5NjYtNDY1Yy1iOTNlLWEwYzUzODA1MzVjNlwifSJ9&jd_pop=4bc3565b-52e7-4b8d-9e7c-9c15d3caa146&abt=0">
                <img src="./素材/q.jpg" alt="" width="300">
            </a>
        </li>

    </ul>
</body>
</html>
```
#### 02.京东左侧导航条
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>京东导航条</title>
    <style>
        *{
            margin:0;
            padding:0;
            list-style: none;
        }
        body{
            background-color: cadetblue;
        }
        .box1{
            background-color:#f4f4f4;
            width: 190px;
            height: 450px;
            /* 设置ul的大小 */
            overflow: hidden;
            padding: 10px 0px;
            margin: 50px auto;
            /* 居中 */
           
            background-color: cornsilk;
        }
        li{
            height: 25px;
            /* 设置li大小 */
            padding-left: 18px;
            /* 设置右内边距 */
            line-height: 25px;
            /* 文字在一行内垂直居中：想让文字在父元素垂直居中，把父元素的 line-height和height设置为同样的值便可。 */
        }
        /* 鼠标移入背景变色 */
        li:hover{
           background-color: #d9d9d9;
       }
       /* 超链接样式 */
       li a{
           color: #333;
           /* 字体颜色 */
           text-decoration: none;
           /* 去除下划线 */
           font-size: 14px;
           /* 字体大小 */
       }
       a:hover{
           color: #c81623;
       }
       span{
           font-size: 12px;
           padding: 0px 2px;
           /* 为斜杠设置样式 */
       }
    </style>
</head>
<body>
    <ul class="box1">
        <li>
            <a href="https://jiadian.jd.com/">家用电器</a>
        </li>
        <li>
            <a href="https://shouji.jd.com/">手机</a><span>/</span><a href="https://wt.jd.com/">运营商</a><span>/</span><a href="https://shuma.jd.com/">数码</a>
        </li>
        <li>
             <a href="https://diannao.jd.com/">电脑</a><span>/</span><a href="https://bg.jd.com/">办公</a>
        </li>
        <li>
             <a href="https://list.jd.com/list.html?cat=1620">家居</a><span>/</span><a href="https://channel.jd.com/furniture.html">家具</a><span>/</span> <a href="https://list.jd.com/list.html?cat=9855">家装</a>/ <a href="https://channel.jd.com/kitchenware.html">厨具</a>
        </li>
        <li>
             <a href="">男装</a><span>/</span><a href="">女装</a><span>/</span><a href="">童装</a><span>/</span><a href="">内衣</a>
        </li>
        <li>
             <a href="">美妆</a><span>/</span><a href="">个护清洁</a><span>/</span><a href="">宠物</a>
        </li>
        <li>
             <a href="">女鞋</a><span>/</span><a href="">箱包</a><span>/</span><a href="">钟表</a><span>/</span><a href="">珠宝</a>
        </li>
        <li>
            <a href="">男鞋</a><span>/</span><a href="">运动</a><span>/</span><a href="">户外</a>
        </li>
        <li>
             <a href="">房产</a><span>/</span><a href="">汽车</a><span>/</span><a href="">汽车用品</a>
        </li>
        <li>
             <a href="">母婴</a><span>/</span><a href="">玩具乐器</a>
        </li>     
        <li>
             <a href="">食品</a><span>/</span><a href="">酒类</a><span>/</span><a href="">生鲜</a><span>/</span><a href="">特产</a>
        </li>
        <li>
            <a href="">艺术</a><span>/</span><a href="">礼品礼花</a><span>/</span><a href="">农贸绿植</a>
        </li>
        <li>
            <a href="">医药保健</a><span>/</span><a href="">计生情趣</a>
        </li>
        <li>
            <a href="">图书</a><span>/</span><a href="">文娱</a><span>/</span><a href="">电纸书</a>
        </li>
        <li>
            <a href="">机票</a><span>/</span><a href="">酒店</a><span>/</span><a href="">旅游</a><span>/</span><a href="">生活</a>
        </li>
        <li>
            <a href="">男鞋</a><span>/</span><a href="">运动</a><span>/</span><a href="">户外</a>
        </li>
        <li>
            <a href="">房产</a><span>/</span><a href="">汽车</a><span>/</span><a href="">汽车用品</a>
        </li>
        <li>
            <a href="">母婴</a><span>/</span><a href="">玩具乐器</a>
       </li>   
    </ul>
</body>
</html>
```
#### 网易新闻列表
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>网易新闻列表</title> 
    <style>
        *{
            margin:0;
            padding:0;
            list-style: none;
        }
        a{
            text-decoration: none;
        }
        .news-wrapper{
            width: 300px;
            height: 357px;
            /* 设置大小 */
            margin: 50px auto;
            /* 设置居中 */
            border-top: 1px solid #ddd;
            /* 设置上边框 */
        }
        .news-title1{
            height: 40px;
            line-height: 40px;
            display: inline-block;
            border-top: 1px solid rgb(255, 0, 0);
            /* 设置上边框 */
            margin-top: -1px;
        }
        .news-title1 a{
            color: #404068;
        }
        .news-img{
            height: 157px;
        }
        .news-img .img-title2{
            color: rgb(255, 255, 255);
            margin-top: -30px;
            padding-left: 20px;
        }
        .news-list{
            margin-top: 20px;
        }
        .news-list li{
            margin-bottom:17px;
        }
        .news-list li a{
            font-size: 14px;
            color: #666;
        }
        .news-list li::before{
            content: '●';
            color: rgb(131, 122, 122);
            font-size: 12px;
            margin-right: 10px;
        }
        .news-list li a:hover{
           color: #c81623;
       }
       .news-title1 a:hover{
        color: #c81623;
       }

    </style>
</head>
<body>
    <div class="news-wrapper">
        <h3 class=" news-title1">
            <a href="https://sports.163.com/">体育</a>
        </h3>
        <div class="news-img">
            <a href="https://www.163.com/sports/article/GSB383Q500058782.html">
                <img src="./素材/下载.jpg" alt="">
                <h4 class="img-title2">俄副总理硬核批NHL退出北京冬奥</h4>
            </a>
        </div>
        <ul class="news-list">
            <li>
                <a href="https://www.163.com/sports/article/GSCDH9BN0005877U.html">疑点重重！460万美元的球星卡是假货？</a>
            </li>
            <li>
                <a href="https://www.163.com/sports/article/GSCE1CJF00058780.html">他起步不如李铁 深耕15年成国内第1人</a>
            </li>
            <li>
                <a href="https://www.163.com/sports/article/GSA9TQVH0005877U.html">超神奇剧本！莫兰特1打4超强滞空绝杀太阳</a>
            </li>
            <li>
                <a href="https://www.163.com/sports/article/GS79EGFD00059A7T.html">4078天！汪峰唱了一首歌给中超之王</a>
            </li>
        </ul>

    </div>

</body>
</html>
```
#### 导航条练习
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>导航条练习</title>
    <style>
        *{
            margin:0;
            padding:0;
        }
        .box1{
            /* 导航条大小颜色 */
            width: 1197px;
            height: 48px;             
            margin: 100px auto;   
            background-color: #E8E7E3;    
        }
        .box1 div{
            
            height: 48px;
            line-height: 48px;
            /* 垂直居中 */
            float: left;
            /* 浮动 */
            text-align: center;
        }
        a{
            display: inline-block;
            color: #777;
            font-size: 18px;
            text-decoration: none;
            padding: 0 39px;
        }
        .box1 div a:hover{
            color: rgb(245, 245, 241);
            background-color: rgb(110, 110, 105);
        }
    </style>
</head>
<body>
    <div class="box1">
        <div class="a1">
            <a href="https://www.w3school.com.cn/h.asp">HTML/CSS</a>
        </div>
        <div class="a2">
            <a>Browser Side</a>
        </div>
        <div class="a3">
            <a>Serve Side</a>
        </div>
        <div class="a4">
            <a>Programming</a>
        </div>
        <div class="a5">
            <a>XML</a>
        </div>
        <div class="a6">
            <a>Wed Building</a>
        </div>
        <div class="a7">
            <a>Reference</a>
        </div>
    </div>
</body>
</html>
```
#### 京东轮播图（静态）
```HTML
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>京东轮播图</title>
    <style>
        *{
            margin:0;
            padding:0;
            list-style: none;
        }
        .img-list{
            width: 590px;
            height: 470px;
            margin: 100px auto;
            position: relative;
        }
        .img-list li{
            position: absolute;
        }
        /* 通过修改元素层级来显示指定的图片 */
        .img-list li:nth-child(3){
            z-index: 3;
        }
        /* 设置导航点的样式 */
        .pointer{
            position: absolute;
            z-index: 9999;
            bottom: 20px;
            left: 40px;
        }
        .pointer a{
             width: 10px;
             height: 10px;
             background-color: rgba(255, 255, 255,.6);
             float: left;
             border-radius: 50%;
             margin:0 4px;
             /* 设置圆形 */
             background-clip: content-box;
             border: rgb(160, 141, 141,0) 2px solid;
         }
         .pointer a.active{
             background-color: #fff;
             border: darkgray 2px solid;
         }
        .pointer a:hover{
            background-color: darkgray;
        }

    </style>
</head>
<body>
    <ul class="img-list">
        <li><a href="javascript:"><img src="./素材/img/05/轮播图1.jpg" alt=""></a></li>
        <li><a href="javascript:"><img src="./素材/img/05/轮播图2.jpg" alt=""></a></li>
        <li><a href="javascript:"><img src="./素材/img/05/轮播图3.jpg" alt=""></a></li>
        <li><a href="javascript:"><img src="./素材/img/05/轮播图4.jpg" alt=""></a></li>
        <li><a href="javascript:"><img src="./素材/img/05/轮播图5.jpg" alt=""></a></li>
        <li><a href="javascript:"><img src="./素材/img/05/轮播图6.jpg" alt=""></a></li>
        <li><a href="javascript:"><img src="./素材/img/05/轮播图7.jpg" alt=""></a></li>
        <div class="pointer">
            <a class="active" href="javascript:"></a>
            <a href="javascript:"></a>
            <a href="javascript:"></a>
            <a href="javascript:"></a>
            <a href="javascript:"></a>
            <a href="javascript:"></a>
            <a href="javascript:"></a>
        </div>
    </ul>
</body>
</html>
```