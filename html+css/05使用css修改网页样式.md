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