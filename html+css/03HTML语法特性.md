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

