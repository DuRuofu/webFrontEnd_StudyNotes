# JavaScript

[toc]
## 介绍

### 组成
由ECMAScript，DOM,BOM三部分组成
### 特点
##### 1.解释型语言
不用编译
##### 2.类似于c和java的语法结构

##### 3.动态语言
##### 4.基于原型和面对对象

### hello world

js是从上到下一行一行的执行的
例子：

``` js
<script>
        // 控制浏览器弹出一个警告框
        alert("这是我的第一行js代码")
        // 让计算机在页面中输出一个内容
        //  document.write 可以向body中输出一个内容
        document.write("这是我的第一行js代码")
        // 向控制台输入一个内容
        console.log("这是我的第一行js代码")
</script>
```
#### 输出语句
- alert("要输出的内容");
- 该语句会在浏览器窗口中弹出一个警告框

- document.write("要输出的内容");
- 该内容将会被写到body标签中，并在页面中显示

- console.log("要输出的内容");
- 该内容会被写到开发者工具的控制台中

### 编写位置

和CSS类似
可以将js代码编写到外部js文件中，然后通过script标签引入
写到外部文件中可以在不同的页面中同时引用，也可以利用到浏览器的缓存机制
推荐使用的方式

``` js
<script type="text/javascript" src="js/script.js"></script>
```
script标签一旦用于引入外部文件了，就不能在编写代码了，即使编写了浏览器也会忽略
如果需要则可以在创建一个新的script标签用于编写内部代码

可以将js代码编写到script标签
``` js
<script type="text/javascript">
			alert("我是内部的JS代码");
		</script>
```
可以将js代码编写到标签的onclick属性中
当我们点击按钮时，js代码才会执行

``` js
<button onclick="alert('你点我干嘛~~');">点我一下</button>
```
可以将js代码写在超链接的href属性中，这样当点击超链接时，会执行js代码
``` js
<a href="javascript:alert('让你点你就点！！');">你也点我一下</a>
<a href="javascript:;">你也点我一下</a>
```
虽然可以写在标签的属性中，但是他们属于结构与行为耦合，不方便维护，不推荐使用

## 基础语法

### 注释

多行注释：
/*  
这是一个多行注释 
 */
单行注释：
//  这是一个单行注释

### 格式要求
- JS严格区分大小写	
- JS中每条语句以分号(;)结尾（不添加可以运行，但浏览器会自己加，会影响加载速度，还有可能加错分号导致错误）
- JS中会自动忽略多个空格和换行，所以我们可以利用空格和换行对代码进行格式化。

### 字面量和变量

字面量
- 字面量实际上就是一些固定的值，比如 1 2 3 4 true false null NaN "hello"
        字面量都是不可以改变的。
- 由于字面量不是很方便使用，所以在JS中很少直接使用字面量

变量
- 变量可以用来保存字面量，并且可以保存任意的字面量
- 一般都是通过变量来使用字面量，而不直接使用字面量，而且也可以通过变量来对字面量进行一个描述
- 声明变量
        - 使用var关键字来声明一个变量
            var a;
            var b;
            var c;
    
- 为变量赋值
        a = 1;
        b = 2;
        c = 3;
    
- 声明和赋值同时进行
        var d = 456;
        var e = 789;

### 标识符
 在JS中所有的可以自主命名的内容，都可以认为是一个标识符，
 是标识符就应该遵守标识符的规范。
 比如：变量名、函数名、属性名
 规范：
        1.标识符中可以含有字母、数字、_、$
        2.标识符不能以数字开头
        3.标识符不能是JS中的关键字和保留字
        4.标识符一般采用驼峰命名法
                xxxYyyZzz
 JS底层保存标识符时实际上是采用的Unicode编码，
        所以理论上讲，所有的utf-8中含有的内容都可以作为标识符    
        所以可以用中文进行命名，但不建议使用

### 基本数据类型

JS中一共分成六种数据类型
  - String 字符串
  - Number 数值
  - Boolean 布尔值
  - Null 空值
  - Undefined 未定义
  - Object 对象
其中String Number Boolean Null Undefined属于基本数据类型，而Object属于引用数据类型

#### 字符串

JS中的字符串需要使用引号引起来双引号或单引号都行
  - 在JS中字符串需要使用引号引起来
  - 使用双引号或单引号都可以，但是不要混着用
  - 引号不能嵌套，双引号里不能放双引号，单引号不能放单引号

在字符串中使用\作为转义字符
        \'  ==> '
        \"  ==> "
        \n  ==> 换行
        \t  ==> 制表符
        \\  ==> \	

用typeof运算符检查字符串时，会返回"string"	
##### 字符串拓展
在底层字符串是以字符数组的形式保存的：["H","e","l"]这样
一些方法和数组类似：
###### length属性
 可以用来获取字符串的长度
```js
console.log(str.length);
```
###### charAt()
```js
			/*
			 * charAt()
			 * 	- 可以返回字符串中指定位置的字符
			 * 	- 根据索引获取指定的字符	
			 */
			str = "中Hello Atguigu";
			
			var result = str.charAt(6);
```
###### charCodeAt()
```js
			/*
			 * charCodeAt()
			 * 	- 获取指定位置字符的字符编码（Unicode编码）
			 */
			result = str.charCodeAt(0);
```
###### fromCharCode(0x2692)
```js
			/*
			 * String.formCharCode()
			 * 	- 可以根据字符编码去获取字符,这是一个构造函数的方法
			 */
			result = String.fromCharCode(0x2692);
			
```
###### concat()			
```js
			/*
			 * concat()
			 * 	- 可以用来连接两个或多个字符串
			 * 	- 作用和+一样
			 */
			result = str.concat("你好","再见");
```
###### indexof()
```js
			/*
			 * indexof()
			 * 	- 该方法可以检索一个字符串中是否含有指定内容
			 * 	- 如果字符串中含有该内容，则会返回其第一次出现的索引
			 * 		如果没有找到指定的内容，则返回-1
			 * 	- 可以指定一个第二个参数，指定开始查找的位置
			 * 
			 * lastIndexOf();
			 * 	- 该方法的用法和indexOf()一样，
			 * 		不同的是indexOf是从前往后找，
			 * 		而lastIndexOf是从后往前找
			 * 	- 也可以指定开始查找的位置
			 */
			
			str = "hello hatguigu";
			
			result = str.indexOf("h",1);
			
			result = str.lastIndexOf("h",5);
			
```
###### slice()
```js
			/*
			 * slice()
			 * 	- 可以从字符串中截取指定的内容
			 * 	- 不会影响原字符串，而是将截取到内容返回
			 * 	- 参数：
			 * 		第一个，开始位置的索引（包括开始位置）
			 * 		第二个，结束位置的索引（不包括结束位置）
			 * 			- 如果省略第二个参数，则会截取到后边所有的
			 * 		- 也可以传递一个负数作为参数，负数的话将会从后边计算
			 */
			str = "abcdefghijk";
			
			result = str.slice(1,4);
			result = str.slice(1,-1);
```
###### substring()
```js
			/*
			 * substring()
			 * 	- 可以用来截取一个字符串，可以slice()类似
			 * 	- 参数：
			 * 		- 第一个：开始截取位置的索引（包括开始位置）
			 * 		- 第二个：结束位置的索引（不包括结束位置）
			 * 		- 不同的是这个方法不能接受负值作为参数，
			 * 			如果传递了一个负值，则默认使用0
			 * 		- 而且他还自动调整参数的位置，如果第二个参数小于第一个，则自动交换
			 */
			
			result = str.substring(0,1);
			
```
###### substr()
```js
			/*
			 * substr()
			 * 	- 用来截取字符串
			 * 	- 参数：
			 * 		1.截取开始位置的索引
			 * 		2.截取的长度
			 */
			
			str = "abcdefg";
			
			result = str.substr(3,2);
```
###### split()
```js
			/*
			 * split()
			 * 	- 可以将一个字符串拆分为一个数组
			 * 	- 参数：
			 * 		-需要一个字符串作为参数，将会根据该字符串去拆分数组
			 */
			str = "abcbcdefghij";
			
			result = str.split("d");
			/*
			 * 如果传递一个空串作为参数，则会将每个字符都拆分为数组中的一个元素
			 */
			result = str.split("");
			
			//console.log(Array.isArray(result));
			//console.log(result[0]);
			console.log(result);
			
			
			str = "abcdefg";
```
###### toUpperCase()
```js
			/*
			 * toUpperCase()
			 * 	- 将一个字符串转换为大写并返回
			 */
			result = str.toUpperCase();
			
			str = "ABCDEFG";
```
###### toLowerCase()
```js
			/*
			 * toLowerCase()
			 * 	-将一个字符串转换为小写并返回
			 */
			result = str.toLowerCase();
```

####  Number 数值

- JS中所有的整数和浮点数都是Number类型
- JS中可以表示的数字的最大(小)值
Number.MAX_VALUE
        1.7976931348623157e+308
Number.MIN_VALUE 大于0的最小值
        5e-324
如果使用Number表示的数字超过了最大值，则会返回一个无穷值
- 特殊的数字
Infinity 正无穷（字面量）
-Infinity 负无穷
使用typeof检查Infinity也会返回number
NaN 非法数字（Not A Number）

- 精度
在JS中整数的运算基本可以保证精确
如果使用JS进行浮点运算，可能得到一个不精确的结果（浮点数不能精确储存）
所以千万不要使用JS进行对精确度要求比较高的运算	

- 其他进制的数字的表示：
0b 开头表示二进制，但是不是所有的浏览器都支持
0 开头表示八进制
0x 开头表示十六进制

在进制转换时
像"070"这种字符串，有些浏览器会当成8进制解析，有些会当成10进制解析
可以在parseInt()中传递一个第二个参数，来指定数字的进制

``` js
        //可以在parseInt()中传递一个第二个参数，来指定数字的进制
        a = parseInt(a,10);
```
- 使用typeof检查一个Number类型的数据时，会返回"number"
（包括NaN 和 Infinity）

#### Boolean 布尔值

布尔值只有两个，主要用来做逻辑判断
        true
        - 表示真
        false
        - 表示假

使用typeof检查一个布尔值时，会返回boolean

#### Null
 Null（空值）类型的值只有一个，就是null
        null这个值专门用来表示一个为空的对象
        使用typeof检查一个null值时，会返回object

####  Undefined
 Undefined（未定义）类型的值只有一个，就undefined
  	当声明一个变量，但是并不给变量赋值时，它的值就是undefined
  	使用typeof检查一个undefined时也会返回undefined

### 强制类型转换
- 指将一个数据类型强制转换为其他的数据类型
- 类型转换主要指，将其他的数据类型，转换为
String Number Boolean

#### 将其他的数据类型转换为String

方式一：
        - 调用被转换数据类型的toString()方法

``` js
        //调用a的toString()方法
        //调用xxx的yyy()方法，就是xxx.yyy()
        a = a.toString();
```

  - 该方法不会影响到原变量，它会将转换的结果返回
  - 但是注意：null和undefined这两个值没有toString()方法，
          如果调用他们的方法，会报错

方式二：
  - 调用String()函数，并将被转换的数据作为参数传递给函数
``` js
        //调用String()函数，来将a转换为字符串
        a = String(a);
```
  - 使用String()函数做强制类型转换时，
          对于Number和Boolean实际上就是调用的toString()方法
          但是对于null和undefined，就不会调用toString()方法
                  它会将 null 直接转换为 "null"
                  将 undefined 直接转换为 "undefined"

#### 将其他的数据类型转换为Number

转换方式一：
  使用Number()函数

``` js
        //调用Number()函数来将a转换为Number类型
        a = Number(a);
```
        - 字符串 --> 数字
                1.如果是纯数字的字符串，则直接将其转换为数字
                2.如果字符串中有非数字的内容，则转换为NaN
                3.如果字符串是一个空串或者是一个全是空格的字符串，则转换为0
        - 布尔 --> 数字
                true 转成 1
                false 转成 0
    
        - null --> 数字     0
    
        - undefined --> 数字 NaN

  转换方式二：
        - 这种方式专门用来对付字符串
                - 如果对非String使用parseInt()或parseFloat()
	      它会先将其转换为String然后再操作

  ``` js
        a = "123567a567px";
        //调用parseInt()函数将a转换为Number
  ```
        - parseInt() 把一个字符串转换为一个整数
                parseInt()可以将一个字符串中的有效的整数内容去出来，
                然后转换为Number
        - parseFloat() 把一个字符串转换为一个浮点数
          parseFloat()作用和parseInt()类似，不同的是它可以获得有效的小数

#### 将其他的数据类型转换为Boolean

 使用Boolean()函数
 ``` js
        //调用Boolean()函数来将a转换为布尔值
        a = Boolean(a);
 ```
- 数字 ---> 布尔
	- 除了0和NaN，其余的都是true

- 字符串 ---> 布尔
	- 除了空串，其余的都是true

- null和undefined都会转换为false

- 对象也会转换为true

### 运算符

运算符也叫操作符
通过运算符可以对一个或多个值进行运算,并获取运算结果
比如：typeof就是运算符，可以来获得一个值的类型
        它会将该值的类型以字符串的形式返回
        number string boolean undefined object

#### 算数运算符
当对非Number类型的值进行运算时，会将这些值转换为Number然后在运算
        任何值和NaN做运算都得NaN

##### +
可以对两个值进行加法运算，并将结果返回
如果对两个字符串进行加法运算，则会做拼串，会将两个字符串拼接为一个字符串，并返回
任何的值和字符串做加法运算，都会先转换为字符串，然后再和字符串做拼串的操作
> 我们可以利用这一特点，来将一个任意的数据类型转换为String
> 我们只需要为任意的数据类型 + 一个 "" 即可将其转换为String
> 这是一种隐式的类型转换，由浏览器自动完成，实际上它也是调用String()函数

##### -
可以对两个值进行减法运算，并将结果返回
> 任何值做- * /运算时都会自动转换为Number
>	我们可以利用这一特点做隐式的类型转换
>	可以通过为一个值 -0 *1 /1来将其转换为Number
>	原理和Number()函数一样，使用起来更加简单
##### *
可以对两个值进行乘法运算
##### /
可以对两个值进行除法运算
##### %
取模运算（取余数）

#### 一元运算符
一元运算符，只需要一个操作数
##### + 正号
	- 正号不会对数字产生任何影响
##### - 负号
	- 负号可以对数字进行负号的取反

#####  对于非Number类型的值，
	它会将先转换为Number，然后在运算
		可以对一个其他的数据类型使用+,来将其转换为number
	它的原理和Number()函数一样

#### 自增自减运算符

##### 自增 ++
 - 通过自增可以使变量在自身的基础上增加1
 - 对于一个变量自增以后，原变量的值会立即自增1
	 - 自增分成两种：后++(a++) 和 前++(++a)	
		无论是a++ 还是 ++a，都会立即使原变量的值自增1
			不同的是a++ 和 ++a的值不同
		a++的值等于原变量的值（自增前的值）
		++a的值等于新值 （自增后的值）

##### 自减 --

- 通过自减可以使变量在自身的基础上减1
- 自减分成两种：后--(a--) 和 前--(--a)
        无论是a-- 还是 --a 都会立即使原变量的值自减1
                不同的是a-- 和 --a的值不同
                        a-- 是变量的原值 （自减前的值）
                        --a 是变量的新值 （自减以后的值）                                  

#### 逻辑运算符

JS中为我们提供了三种逻辑运算符

##### 非

```
                ! 非
                - !可以用来对一个值进行非运算
                - 所谓非运算就是值对一个布尔值进行取反操作，
                    true变false，false变true
                - 如果对一个值进行两次取反，它不会变化
                - 如果对非布尔值进行元素，则会将其转换为布尔值，然后再取反
                    所以我们可以利用该特点，来将一个其他的数据类型转换为布尔值
                    可以为一个任意数据类型取两次反，来将其转换为布尔值，
                    原理和Boolean()函数一样
```

##### 与

```
				&& 与
			  	- &&可以对符号两侧的值进行与运算并返回结果
			  	- 运算规则
			  		- 两个值中只要有一个值为false就返回false，
			  			只有两个值都为true时，才会返回true
			  		- JS中的“与”属于短路的与，
			 			如果第一个值为false，则不会看第二个值
```

##### 或

```
			 	 || 或
			 	- ||可以对符号两侧的值进行或运算并返回结果
			  	- 运算规则：
			  		- 两个值中只要有一个true，就返回true
			  			如果两个值都为false，才返回false
			 		- JS中的“或”属于短路的或
			  			如果第一个值为true，则不会检查第二个值
```

##### 非布尔值逻辑运算符

&& || 非布尔值的情况

\- 对于非布尔值进行与或运算时，会先将其转换为布尔值，然后再运算，并且返回原值

```
			  	- 与运算：
			  		- 如果第一个值为true，则必然返回第二个值
			  		- 如果第一个值为false，则直接返回第一个值
			  
			  	- 或运算
			  		- 如果第一个值为true，则直接返回第一个值
			  		- 如果第一个值为false，则返回第二个值
```

#### 赋值运算符

 = 可以将符号右侧的值赋值给符号左侧的变量

#### 关系运算符

通过关系运算符可以比较两个值之间的大小关系， 如果关系成立它会返回true，如果关系不成立则返回false

```
        > 大于号
			  	- 判断符号左侧的值是否大于右侧的值
			  	- 如果关系成立，返回true，如果关系不成立则返回false
			  
        >= 大于等于
			  	- 判断符号左侧的值是否大于或等于右侧的值
			  
		< 小于号
	    <= 小于等于
			  	同理
```

非数值的情况

```js
		  	- 对于非数值进行比较时，会将其转换为数字然后在比较
			  	- 如果符号两侧的值都是字符串时，不会将其转换为数字进行比较
			  		而会分别比较字符串中字符的Unicode编码
			    -比较两个字符串时，比较的是字符串的字符编码
			    -比较字符编码时是一位一位进行比较
			    -如果两位一样，则比较下一位，所以借用它来对英文进行排序
			    -比较中文时没有意义
			    console.log("戒" > "我"); //true
			    -如果比较的两个字符串型的数字，可能会得到不可预期的结果
		    -注意：在比较两个字符串型的数字时，一定一定一定要转型
				console.log("11123123123123123123" < +"5"); //true
```

#### Unicode编码

在js里使用：在字符串中使用转义字符输入Unicode编码
格式：\u四位编码

```js
console.log("\u2620");
```

在网页里（html）使用

格式：&#编码; 这里的编码需要的是10进制`

```js
<h1 style="font-size: 200px;">&#9760;</h1>
<h1 style="font-size: 200px;">&#9856;</h1>
```

#### 相等运算符

相等运算符用来比较两个值是否相等，如果相等会返回true，否则返回false

```
* 使用 == 来做相等运算
* 	- 当使用==来比较两个值时，如果值的类型不同，
* 		则会自动进行类型转换，将其转换为相同的类型
* 		然后在比较
* 不相等
* 	 不相等用来判断两个值是否不相等，如果不相等返回true，否则返回false
* 	- 使用 != 来做不相等运算
* 	- 不相等也会对变量进行自动的类型转换，如果转换后相等它也会返回false
* 
* 		
*  ===
* 		全等
* 		- 用来判断两个值是否全等，它和相等类似，不同的是它不会做自动的类型转换
* 			如果两个值的类型不同，直接返回false
* 	!==
* 		不全等
* 		- 用来判断两个值是否不全等，和不等类似，不同的是它不会做自动的类型转换
* 			如果两个值的类型不同，直接返回true
```

```js
//undefined 衍生自 null
//	所以这两个值做相等判断时，会返回true
console.log(undefined == null);
```

```js
// NaN不和任何值相等，包括他本身
console.log(NaN == NaN); //false
```

```js
var b = NaN;
//判断b的值是否是NaN
console.log(b == NaN);
/*
 可以通过isNaN()函数来判断一个值是否是NaN
 如果该值是NaN则返回true，否则返回false
*/
console.log(isNaN(b));
```

#### 条件运算符

条件运算符也叫三元运算符

```js
语法：
	条件表达式?语句1:语句2;
- 执行的流程：
    条件运算符在执行时，首先对条件表达式进行求值，
    如果该值为true，则执行语句1，并返回执行结果
    如果该值为false，则执行语句2，并返回执行结果
    如果条件的表达式的求值结果是一个非布尔值，
    会将其转换为布尔值然后在运算
```

举例：求三数最大值

```js
    var a = 300;
    var b = 143;
    var c = 50;
    //获取a和b中的最大值
    var max = a > b ? a : b;
    //获取a b c 中的大值
    max = max > c ? max : c;
    //这种写法不推荐使用，不方便阅读
    var max = a > b ? (a > c ? a :c) : (b > c ? b : c);
    console.log("max = "+max);
```

### 运算符的优先级

```
就和数学中一样，在JS中运算符也有优先级，
 	比如：先乘除 后加减
 在JS中有一个运算符优先级的表，
 	在表中越靠上优先级越高，优先级越高越优先计算，
 	如果优先级一样，则从左往右计算。
 但是这个表我们并不需要记忆，如果遇到优先级不清楚
 可以使用()来改变优先级
```

<img src="https://image-1308319148.cos.ap-chengdu.myqcloud.com/main/1652691618198.png"  />

### 代码块

```
 我们的程序是由一条一条语句构成的
 	语句是按照自上向下的顺序一条一条执行的
 	在JS中可以使用{}来为语句进行分组,
 		同一个{}中的语句我们称为是一组语句，
 		它们要么都执行，要么都不执行，
 		一个{}中的语句我们也称为叫一个代码块
 		在代码块的后边就不用再编写;了
 
 	JS中的代码块，只具有分组的的作用，没有其他的用途
 		代码块内容的内容，在外部是完全可见的
 		
```

```js
{
    var a = 10;	
    alert("hello");
    console.log("你好");
    document.write("语句");
}
```

### 流程控制语句

JS中的程序是从上到下一行一行执行的

通过流程控制语句可以控制程序执行流程，使程序可以根据一定的条件来选择执行

*  语句的分类：

   1. 条件判断语句

   2. 条件分支语句

   3. 循环语句

 条件判断语句：
  - 使用条件判断语句可以在执行某个语句之前进行判断，
       果条件成立才会执行语句，条件不成立则语句不执行。

#### if语句

```
 语法一：
 		if(条件表达式){
 			语句...
 		}
 			
 		if语句在执行时，会先对条件表达式进行求值判断，
 		如果条件表达式的值为true，则执行if后的语句，
 		如果条件表达式的值为false，则不会执行if后的语句。
 			if语句只能控制紧随其后的那个语句,
 				如果希望if语句可以控制多条语句，
 				可以将这些语句统一放到代码块中
 			if语句后的代码块不是必须的，但是在开发中尽量写上代码块，即使if后只有一条语句
```

```
语法二:
 		if(条件表达式){
 			语句...
 		}else{
 			语句...
 		}
 
 	if...else...语句
 		当该语句执行时，会先对if后的条件表达式进行求值判断，
 			如果该值为true，则执行if后的语句
 			如果该值为false，则执行else后的语句	
```

```
  	语法三：
  		if(条件表达式){
  			语句...
  		}else if(条件表达式){
  			语句...
  		}else if(条件表达式){
  			语句...
  		}else{
  			语句...
  		}
  
  		if...else if...else
  			当该语句执行时，会从上到下依次对条件表达式进行求值判断
  			如果值为true，则执行当前语句。
  			如果值为false，则继续向下判断。
  			如果所有的条件都不满足，则执行最后一个else后的语句
  			该语句中，只会有一个代码块被执行，一旦代码块执行了，则直接结束语句
```

#### if练习

##### 练习1

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>if练习1</title>
		<script type="text/javascript">
			/*
			 * 	从键盘输入小明的期末成绩:
			 *	当成绩为100时，'奖励一辆BMW'
			 *	当成绩为[80-99]时，'奖励一台iphone15s'
			 *	当成绩为[60-80]时，'奖励一本参考书'
			 *	其他时，什么奖励也没有
			 */
			
			/*
			 * prompt()可以弹出一个提示框，该提示框中会带有一个文本框，
			 * 	用户可以在文本框中输入一段内容，该函数需要一个字符串作为参数，
			 * 	该字符串将会作为提示框的提示文字
			 * 
			 * 用户输入的内容将会作为函数的返回值返回，可以定义一个变量来接收该内容
			 */
			//score就是小明的期末成绩
			var score = prompt("请输入小明的期末成绩(0-100):");
			
			
			//判断值是否合法
			if(score > 100 || score < 0 || isNaN(score)){
				alert("拉出去毙了~~~");
			}else{
				//根据score的值来决定给小明什么奖励
				if(score == 100){
					//奖励一台宝马
					alert("宝马，拿去~~~");
				}else if(score >= 80){
					//奖励一个手机
					alert("手机，拿去玩~~~");
				}else if(score >= 60){
					//奖励一本参考书
					alert("参考书，拿去看~~~");
				}else{
					alert("棍子一根~~");
				}
			}
	
		</script>
	</head>
	<body>
		
	</body>
</html>

```

##### 练习2

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>if练习2</title>
		<script type="text/javascript">
			/*
			 * 	大家都知道，男大当婚，女大当嫁。那么女方家长要嫁女儿，当然要提出一定的条件： 
			 *	高：180cm以上; 富:1000万以上; 帅:500以上;
			 *	如果这三个条件同时满足，则:'我一定要嫁给他'
			 *	如果三个条件有为真的情况，则:'嫁吧，比上不足，比下有余。' 
			 *	如果三个条件都不满足，则:'不嫁！' 
			 */
			
			var height = prompt("请输入你的身高(CM):");
			var money = prompt("请输入你的财富(万):");
			var face = prompt("请输入你的颜值(PX):");
			
			//如果这三个条件同时满足，则:'我一定要嫁给他'
			if(height > 180 && money > 1000 && face > 500){
				alert("我一定要嫁给他~~");
			}else if(height > 180 || money > 1000 || face > 500){
				//如果三个条件有为真的情况，则:'嫁吧，比上不足，比下有余。' 
				alert("嫁吧，比上不足，比下有余。");
			}else{
				//如果三个条件都不满足，则:'不嫁！' 
				alert("不嫁。");
			}

		</script>
	</head>
	<body>
		
	</body>
</html>

```

##### 练习3：三个整数排序

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>if练习3</title>
		<script type="text/javascript">
			/*
			 * 	编写程序，由键盘输入三个整数分别存入变量num1、num2、num3，
			 * 	对他们进行排序，并且从小到大输出。
			 */
			
			//获取用户输入的三个数
			/*
			 * prompt()函数的返回值是String类型的
			 */
			var num1 = +prompt("请输入第一个数:");
			var num2 = +prompt("请输入第二个数:");
			var num3 = +prompt("请输入第三个数:");
			
			
			//找到三个数中最小的数
			if(num1 < num2 && num1 < num3){
				//num1最小，比较num2和num3
				if(num2 < num3){
					//num1 num2 num3
					alert(num1 +","+num2 + ","+num3);
				}else{
					//num1 num3 num2
					alert(num1 +","+num3 + ","+num2);
				}
				
			}else if(num2 < num1 && num2 < num3){
				//num2最小，比较num1和num3
				if(num1 < num3){
					//num2 num1 num3
					alert(num2 +","+num1 + ","+num3);
				}else{
					//num2 num3 num1
					alert(num2 +","+num3 + ","+num1);
				}
				
			}else{
				//num3最小,比较num1和num2
				if(num1 < num2){
					// num3 num1 num2
					alert(num3 +","+num1 + ","+num2);
				}else{
					//num3 num2 num1
					alert(num3 +","+num2 + ","+num1);
				}
				
			}
			
			
		</script>
	</head>
	<body>
		
	</body>
</html>

```

### 条件分支语句

#### switch语句

条件分支语句也叫switch语句

```
			  	语法：
			  		switch(条件表达式){
			 			case 表达式:
			  				语句...
			  				break;
			   		case 表达式:
			  				语句...
			  				break;
			  			default:
			  				语句...
			  				break;
			  		}			  		
```

 	执行流程：

```
 		switch...case..语句
 		在执行时会依次将case后的表达式的值和switch后的条件表达式的值进行全等比较，
 			如果比较结果为true，则从当前case处开始执行代码。
 				当前case后的所有的代码都会执行，我们可以在case的后边跟着一个break关键字，
 				这样可以确保只会执行当前case后的语句，而不会执行其他的case
 			如果比较结果为false，则继续向下比较
 			如果所有的比较结果都为false，则只执行default后的语句
 
 	switch语句和if语句的功能实际上有重复的，使用switch可以实现if的功能，
 		同样使用if也可以实现switch的功能，所以我们使用时，可以根据自己的习惯选择。
```

例子：

```js
			var num = 3;
//用if写：
			/*if(num == 1){
				console.log("壹");
			}else if(num == 2){
				console.log("贰");
			}else if(num == 3){
				console.log("叁");
			}*/
			
			num = "hello";
//用switch语句写
			switch(num){
				case 1:
					console.log("壹");
					//使用break可以来退出switch语句
					break;
				case 2:
					console.log("贰");
					break;
				case 3:
					console.log("叁");
					break;
				default:
					console.log("非法数字~~");
					break;
			}
```

#### swich练习:

对于成绩大于60分的，输出'合格'。低于60分的，输出'不合格'

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>switch练习1</title>
		<script type="text/javascript">
			/*
			 * 对于成绩大于60分的，输出'合格'。低于60分的，输出'不合格'
			 * 
			 * 6x  /  10 = 6
			 * 7x  /  10 = 7
			 * 8x  /  10 = 8
			 * 9x  /  10 = 9
			 * 100 /  10 = 10
			 * 
			 */
			var score = 75;
			
			/*switch(parseInt(score/10)){
				case 10:
				case 9:
				case 8:
				case 7:
				case 6:
					console.log("合格");
					break;
				default:
					console.log("不合格");
					break;
			}*/
			
			switch(true){
				case score >= 60:
					console.log("合格");
					break;
				default:
					console.log("不合格");
					break;
			}
		
		</script>
	<body>
	</body>
</html>

```

### 循环语句

#### while语句

通过循环语句可以反复的执行一段代码多次

```
 while循环:
			  	- 语法：
			  		while(条件表达式){
			  			语句...
			  		}
			  
			  	- while语句在执行时，
			  		先对条件表达式进行求值判断，
			  			如果值为true，则执行循环体，
			  				循环体执行完毕以后，继续对表达式进行判断
			  				如果为true，则继续执行循环体，以此类推
			  			如果值为false，则终止循环
```

```
 do...while循环
			  	- 语法：
			  		do{
			  			语句...
			  		}while(条件表达式)
			  
			  	- 执行流程：
			  		do...while语句在执行时，会先执行循环体，
			  			循环体执行完毕以后，在对while后的条件表达式进行判断，
			  			如果结果为true，则继续执行循环体，执行完毕继续判断以此类推
			  			如果结果为false，则终止循环
			  
			  		实际上这两个语句功能类似，不同的是while是先判断后执行，
			  			而do...while会先执行后判断，
			  		do...while可以保证循环体至少执行一次，
			  			而while不能
```

```js
//向这种将条件表达式写死为true的循环，叫做死循环
//该循环不会停止，除非浏览器关闭，死循环在开发中慎用
//可以使用break，来终止循环
                while(true){
                    alert(n++);

                    //判断n是否是10
                    if(n == 10){
                        //退出循环
                        break;
                    }
                }
//创建一个循环，往往需要三个步骤			
//1.创初始化一个变量						
//2.在循环中设置一个条件表达式		
//3.定义一个更新表达式，每次更新初始化变量
```

##### while练习1

假如投资的年利率为5%，试求从1000块增长到5000块，需要花费多少年

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">
			
			/*
			 * 假如投资的年利率为5%，试求从1000块增长到5000块，需要花费多少年
			 * 
			 * 1000 1000*1.05
			 * 1050 1050*1.05
			 */		
			//定义一个变量，表示当前的钱数
			var money = 1000;		
			//定义一个计数器
			var count = 0;			
			//定义一个while循环来计算每年的钱数
			while(money < 5000){
				money *= 1.05;				
				//使count自增
				count++;
			}			
			//console.log(money);
			console.log("一共需要"+count+"年");
		</script>
	</head>
	<body>
	</body>
</html>

```

##### while练习2

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>if练习1</title>
		<script type="text/javascript">
			/*
			 * 	从键盘输入小明的期末成绩:
			 *	当成绩为100时，'奖励一辆BMW'
			 *	当成绩为[80-99]时，'奖励一台iphone15s'
			 *	当成绩为[60-80]时，'奖励一本参考书'
			 *	其他时，什么奖励也没有
			 */
			
			/*
			 * prompt()可以弹出一个提示框，该提示框中会带有一个文本框，
			 * 	用户可以在文本框中输入一段内容，该函数需要一个字符串作为参数，
			 * 	该字符串将会作为提示框的提示文字
			 * 
			 * 用户输入的内容将会作为函数的返回值返回，可以定义一个变量来接收该内容
			 */
			//将prompt放入到一个循环中,以实现输错之后可以继续输入
			while(true){
				//score就是小明的期末成绩
				var score = prompt("请输入小明的期末成绩(0-100):");
				//判断用户输入的值是否合法
				if(score >= 0 && score <= 100){
					//满足该条件则证明用户的输入合法，退出循环
					break;
				}
				
				alert("请输入有效的分数！！！");
			}
		
			//判断值是否合法
			if(score > 100 || score < 0 || isNaN(score)){
				alert("拉出去毙了~~~");
			}else{
				//根据score的值来决定给小明什么奖励
				if(score == 100){
					//奖励一台宝马
					alert("宝马，拿去~~~");
				}else if(score >= 80){
					//奖励一个手机
					alert("手机，拿去玩~~~");
				}else if(score >= 60){
					//奖励一本参考书
					alert("参考书，拿去看~~~");
				}else{
					alert("棍子一根~~");
				}
			}
	
		</script>
	</head>
	<body>
		
	</body>
</html>

```

#### for循环

for语句，也是一个循环语句，也称为for循环、

```
在for循环中，为我们提供了专门的位置用来放三个表达式：
        1.初始化表达式
        2.条件表达式
        3.更新表达式
```

```js
for循环的语法：
                for(①初始化表达式;②条件表达式;④更新表达式){
                    ③语句...
                }
 for循环的执行流程：
                 ①执行初始化表达式，初始化变量（初始化表达式只会执行一次）
                 ②执行条件表达式，判断是否执行循环。
                 如果为true，则执行循环③d
                 如果为false，终止循环
                 ④执行更新表达式，更新表达式执行完毕继续重复②
                 
 for循环中的三个部分都可以省略，也可以写在外部
 如果在for循环中不写任何的表达式，只写两个;
 此时循环是一个死循环会一直执行下去，慎用
                 for(;;){
                     alert("hello");
                 }
```

##### for循环的嵌套:

以99乘法表为例

```js
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">
			
			/*
			 * 1.打印99乘法表
			 * 	 1*1=1
			 * 	 1*2=2 2*2=4
			 * 	 1*3=3 2*3=6 3*3=9
			 * 	 1*4=4 2*4=8 3*4=12 4*4=16	
			 * 						....9*9=81
			 * 
			 * 2.打印出1-100之间所有的质数
			 */		
			//创建外层循环，用来控制乘法表的高度
			for(var i=1 ; i<=9 ; i++ ){
				//创建一个内层循环来控制图形的宽度
				for(var j=1 ; j<=i ; j++){
					document.write("<span>"+j+"*"+i+"="+i*j+"</span>");
				}
				
				//输出一个换行
				document.write("<br />");			
			}	
		</script>
		<style type="text/css">
		
			body{
				width: 2000px;
			}
			
			span{
				display: inline-block;//使式子对齐（通过设置span的宽度）
				width: 80px;
			}			
		</style>
	</head>
	<body>
	</body>
</html>

```

##### break和continue关键字

###### break

break关键字可以用来退出switch或循环语句
不能在if语句中使用break和continue

```js
			for(var i=0 ; i<5 ; i++){
				console.log(i);
				if(i == 2){
					break;//这里的break是用于外面的for的
				}
				
			}
```

break关键字，会立即终止离他最近的那个循环语句

```js
* 可以为循环语句创建一个label，来标识当前的循环（给循环指定名字）
* label:循环语句
* 使用break语句时，可以在break后跟着一个label，
* 	这样break将会结束指定的循环，而不是最近的
            outer:
            for(var i=0 ; i<5 ; i++){
                console.log("@外层循环"+i)
                for(var j=0 ; j<5; j++){
                    break outer;//这里就直接终止了外层循环
                    console.log("内层循环:"+j);
                }
            }
```

###### continue

 continue关键字可以用来跳过当次循环
同样continue也是默认只会对离他最近的循环循环起作用

##### for循环练习1：100以内奇数和

```js
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">
			
			/*
			 * 打印1-100之间所有奇数之和
			 */
			
			//创建一个变量，用来保存奇数之和
			//var sum = 0;
			
			//打印1-100之间的数
			for(var i=1 , sum=0 ; i<=100 ; i++){
				
				//判断i是否是奇数
				//不能被2整除的数就是奇数
				if(i%2 != 0){
					//如果i除以2有余数则证明i是奇数
					//console.log(i);
					sum = sum+i;
				}
			}
			
			console.log("奇数之和为 : "+sum);
			
		</script>
	</head>
	<body>
	</body>
</html>
```

##### for循环练习2：打印1-100之间所有7的倍数的个数及总和

```js
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">			
			/*
			 * 打印1-100之间所有7的倍数的个数及总和
			 */
			//定义一个变量，来保存总和
			var sum = 0;
			//定义一个计数器，来记录数量
			var count = 0;
			
			//打印1-100之间所有的数
			for(var i=1 ; i<=100 ; i++){
				
				//判断i是否是7的倍数
				if(i % 7 == 0){
					//console.log(i);
					sum += i;
					//使计数器自增1
					count++;				
				}			
			}			
			//输出总和
			console.log("总和为:"+sum);
			//输出总数
			console.log("总数量为:"+count);	
		</script>
	</head>
	<body>
	</body>
</html>
```

##### for循环练习3：水仙花数

```js
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">
			
			/*
			 * 水仙花数是指一个3位数，它的每个位上的数字的3 次幂之和等于它本身。
				（例如：1^3 + 5^3 + 3^3 = 153）,请打印所有的水仙花数。
			 */	
			//打印所有的三位数
			for(var i=100 ; i<1000 ; i++){
				
				//获取i的百位 十位 个位的数字
				//获取百位数字
				var bai = parseInt(i/100);		
				//获取十位的数字
				var shi = parseInt((i-bai*100)/10);			
				//获取个位数字
				var ge = i % 10;	
				//判断i是否是水仙花数
				if(bai*bai*bai + shi*shi*shi + ge*ge*ge == i){
					console.log(i);
				}	
			}
		</script>
	</head>
	<body>
	</body>
</html>
```

##### for循环练习4：判断质数

```js
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">
			/*
			 * 在页面中接收一个用户输入的数字，并判断该数是否是质数。
				质数：只能被1和它自身整除的数，1不是质数也不是合数，质数必须是大于1的自然数。	
			 */
			
			var num = prompt("请输入一个大于1的整数:");
		
			//判断这个值是否合法
			if(num <= 1){
				alert("该值不合法！");
			}else{
				
				//创建一个变量来保存当前的数的状态
				//默认当前num是质数
				var flag = true;
				
				//判断num是否是质数
				//获取2-num之间的数
				for(var i=2 ; i<num ; i++){
					//console.log(i);
					//判断num是否能被i整除
					if(num % i == 0){
						//如果num能被i整除，则说明num一定不是质数
						//设置flag为false
						flag = false;
					}
				}			
				//如果num是质数则输出
				if(flag){
					alert(num + "是质数！！！");
				}else{
					alert("这个不是质数")
				}		
			}
		</script>
	</head>
	<body>
	</body>
</html>

```

### 对象

#### **介绍，基本内容：**

```js
<script type="text/javascript">
			/*
			 * JS中数据类型
			 * 	- String 字符串
			 *  - Number 数值
			 * 	- Boolean 布尔值
			 * 	- Null 空值
			 * 	- Undefined 未定义
			 * 		- 以上这五种类型属于基本数据类型，以后我们看到的值
			 * 			只要不是上边的5种，全都是对象
			 * 	- Object 对象
			 * 
			 * 
			 * 基本数据类型都是单一的值"hello" 123 true,
			 * 	值和值之间没有任何的联系。
			 * 
			 * 在JS中来表示一个人的信息（name gender age）：
			 * 	var name = "孙悟空";
			 * 	var gender = "男";
			 * 	var age = 18;
			 * 如果使用基本数据类型的数据，我们所创建的变量都是独立，不能成为一个整体。
			 * 
			 * 对象属于一种复合的数据类型，在对象中可以保存多个不同数据类型的属性。
			 * 
			 * 对象的分类：
			 * 	1.内建对象
			 * 		- 由ES标准中定义的对象，在任何的ES的实现中都可以使用
			 * 		- 比如：Math String Number Boolean Function Object....
			 * 
			 * 	2.宿主对象
			 * 		- 由JS的运行环境提供的对象，目前来讲主要指由浏览器提供的对象
			 * 		- 比如 BOM DOM
			 * 
			 * 	3.自定义对象
			 * 		- 由开发人员自己创建的对象
			 * 
			 */
			
			//创建对象
			/*
			 * 使用new关键字调用的函数，是构造函数constructor
			 * 	构造函数是专门用来创建对象的函数
			 * 使用typeof检查一个对象时，会返回object
			 */
			var obj = new Object();
			
			
			/*
			 * 在对象中保存的值称为属性
			 * 向对象添加属性
			 * 	语法：对象.属性名 = 属性值;
			 */
			
			//向obj中添加一个name属性
			obj.name = "孙悟空";
			//向obj中添加一个gender属性
			obj.gender = "男";
			//向obj中添加一个age属性
			obj.age = 18;
			
			/*
			 * 读取对象中的属性
			 * 	语法：对象.属性名
			 * 
			 * 如果读取对象中没有的属性，不会报错而是会返回undefined
			 */
			
			//console.log(obj.gender);
			//console.log(obj.hello);
			
			/*
			 * 修改对象的属性值
			 * 	语法：对象.属性名 = 新值
			 */
			obj.name = "tom";
			
			/*
			 * 删除对象的属性
			 * 	语法：delete 对象.属性名
			 */
			delete obj.name;		
			console.log(obj.age);
		</script>
```

#### 属性名和属性值

```js
		<script type="text/javascript">
			
			var obj = new Object();

			/*
			 * 向对象中添加属性
			 * 属性名：
			 * 	- 对象的属性名不强制要求遵守标识符的规范
			 * 		什么乱七八糟的名字都可以使用
			 * 	- 但是我们使用是还是尽量按照标识符的规范去做
			 * 
			 */
			obj.name = "孙悟空";
			
			//obj.var = "hello";
			
			/*
			 * 如果要使用特殊的属性名，不能采用.的方式来操作
			 * 	需要使用另一种方式：
			 * 		语法：对象["属性名"] = 属性值
			 * 	读取时也需要采用这种方式
			 * 
			 * 使用[]这种形式去操作属性，更加的灵活，
			 * 	在[]中可以直接传递一个变量，这样变量值是多少就会读取那个属性
			 * 
			 */
			obj["123"] = 789;
			obj["nihao"] = "你好";
			var n = "nihao";
			//console.log(obj["123"]);
			
			/*
			 * 属性值
			 * 	JS对象的属性值，可以是任意的数据类型
			 * 		甚至也可以是一个对象
			 */
			
			obj.test = true;
			obj.test = null;
			obj.test = undefined;
			
			//创建一个对象
			var obj2 = new Object();
			obj2.name = "猪八戒";
			
			//将obj2设置为obj的属性
			obj.test = obj2;
			
			//console.log(obj.test.name);
			
			/*
			 * in 运算符
			 * 	- 通过该运算符可以检查一个对象中是否含有指定的属性
			 * 		如果有则返回true，没有则返回false
			 *  - 语法：
			 * 		"属性名" in 对象
			 */
			//console.log(obj.test2);
			
			//检查obj中是否含有test2属性
			//console.log("test2" in obj);
			//console.log("test" in obj);
			console.log("name" in obj);
			
		</script>
```

#### 基本数据类型和引用数据类型 

#####  基本数据类型
   String Number Boolean Null Undefined

##### 引用数据类型

	Object
	  
	  JS中的变量都是保存到栈内存中的，
	 		基本数据类型的值直接在栈内存中存储，
	 		值与值之间是独立存在，修改一个变量不会影响其他的变量
	  
	  		对象是保存到堆内存中的，每创建一个新的对象，就会在堆内存中开辟出一个新的空间，
	 		而变量保存的是对象的内存地址（对象的引用），如果两个变量保存的是同一个对象引用，
	  		当一个通过一个变量修改属性时，另一个也会受到影响
	当比较两个基本数据类型的值时，就是比较值。
			而比较两个引用数据类型时，它是比较的对象的内存地址，
					如果两个对象是一摸一样的，但是地址不同，它也会返回false

#### 对象字面量

创建一个对象：
```js
var obj = new Object();
```

使用对象字面量来创建一个对象:
```js
var obj = {};
```

使用对象字面量，可以在创建对象时，直接指定对象中的属性

 语法：{属性名:属性值,属性名:属性值....}
		对象字面量的属性名可以加引号也可以不加，建议不加,
		如果要使用一些特殊的名字，则必须加引号
		 
 属性名和属性值是一组一组的名值对结构，
		名和值之间使用:连接，多个名值对之间使用,隔开
		如果一个属性之后没有其他的属性了，就不要写,
		
举例：

```js
			var obj2 = {
				
				name:"猪八戒",
				age:13,
				gender:"男",
				test:{name:"沙僧"}				
			};
```

### 函数

#### function介绍
函数 function
	- 函数也是一个对象
	- 函数中可以封装一些功能（代码），在需要时可以执行这些功能（代码）
	- 函数中可以保存一些代码在需要的时候调用
	- 使用typeof检查一个函数对象时，会返回function

我们在实际开发中很少使用构造函数来创建一个函数对象
使用构造函数创建一个函数对象
可以将要封装的代码以字符串的形式传递给构造函数

```js
var fun = new Function("console.log('Hello 这是我的第一个函数');");
```

封装到函数中的代码不会立即执行
函数中的代码会在函数调用的时候执行
调用函数 语法：函数对象()
当调用函数时，函数中封装的代码会按照顺序执行

使用 函数声明 来创建一个函数,语法：

```js
		function 函数名([形参1,形参2...形参N]){
			语句...
		}
		//例子:
		function fun2(){
			console.log("这是我的第二个函数~~~");
			alert("哈哈哈哈哈");
			document.write("~~~~(>_<)~~~~");
		}
```

使用 函数表达式 来创建一个函数,语法：
```js
	  var 函数名  = function([形参1,形参2...形参N]){
		 语句....
	   }
	//例子 创建匿名函数：
	function(){
		console.log("我是匿名函数中封装的代码");
	};
	//调用匿名函数
	var fun3 = function(){
		console.log("我是匿名函数中封装的代码");
	};
```

#### 函数的参数

例子：
```js
	 // 	定义一个用来求两个数和的函数
	 // 	可以在函数的()中来指定一个或多个形参（形式参数）
	 // 	多个形参之间使用,隔开，声明形参就相当于在函数内部声明了对应的变量
	 // 	但是并不赋值
	function sum(a,b){
		console.log("a = "+a);
		console.log("b = "+b);
		console.log(a+b);
	}
	//在调用函数时，可以在()中指定实参（实际参数）
	// 	实参将会赋值给函数中对应的形参
	sum(1,2);
	sum(123,456);
```

调用函数时解析器不会检查实参的类型,
所以要注意，是否有可能会接收到非法的参数，如果有可能则需要对参数进行类型的检查
函数的实参可以是任意的数据类型
```js
	sum(123,"hello");
	sum(true , false);
```

调用函数时，解析器也不会检查实参的数量
		多余实参不会被赋值
		如果实参的数量少于形参的数量，则没有对应实参的形参将是undefined
```js
sum(123,456,"hello",true,null);
sum(123);
```

#### 函数的返回值

可以使用 return 来设置函数的返回值
```
语法：
	return 值
```
return后的值将会会作为函数的执行结果返回，可以定义一个变量，来接收该结果
在函数中return后的语句都不会执行
如果return语句后不跟任何值就相当于返回一个undefined，如果函数中不写return，则也会返回undefined
return后可以跟任意类型的值
```js
	function sum(a , b , c){
		//alert(a + b +c);		
		var d = a + b + c;	
		return d;		
	}
```

调用函数
变量result的值就是函数的执行结果
函数返回什么result的值就是什么
```js
			var result = sum(4,7,8);			
			console.log("result = "+result);
```
返回值可以是任意的数据类型,也可以是一个对象，也可以是一个函数
```js
			function fun2(){
				
				//返回一个对象
				return {name:"沙和尚"};
			}
```
```js
			function fun3(){
				//在函数内部再声明一个函数
				function fun4(){
					alert("我是fun4");
				}
				//将fun4函数对象作为返回值返回
				return fun4;
			}
```
#### 函数练习

```js		
 //定义一个函数，判断一个数字是否是偶数，如果是返回true，否则返回false		
			function isOu(num){		
				return num % 2 == 0;
			}		
			var result = isOu(15);
```

```js
// 定义一个函数，可以根据半径计算一个圆的面积，并返回计算结果
			function mianji(r){		
				return 3.14*r*r;		
			}
			result = mianji(5);
```

```js
/*
 * 创建一个函数，可以在控制台中输出一个人的信息(传递对象)
 * 	可以输出人的 name age gender address
 * 实参可以是任意的数据类型，也可以是一个对象
 * 	当我们的参数过多时，可以将参数封装到一个对象中，然后通过对象传递
 */
			function sayHello(o){
				
				//console.log("o = "+o);
				console.log("我是"+o.name+",今年我"+o.age+"岁了,"+"我是一个"+o.gender+"人"+",我住在"+o.address);
			}
			//创建一个对象
			var obj = {
				name:"孙悟空",
				age:18,
				address:"花果山",
				gender:"男"
				
			};
```
所以：
```js
//实参可以是一个对象，也可以是一个函数		
			function fun(a){
				console.log("a = "+a);
				a(obj);
			}
			fun(sayHello);
//将匿名函数作为实参
			fun(function(){alert("hello")});
```

```js
		fun(mianji(10));
		fun(mianji);
//两者的区别：
		mianji()
			  	- 调用函数
			  	- 相当于使用的函数的返回值			  
		 mianji
			  	- 函数对象
			 	- 相当于直接使用函数对象
```

#### break continue return的区别

使用break可以退出当前的循环
continue用于跳过当次循环
使用return可以结束整个函数
```js
function fun(){
				alert("函数要执行了~~~~");				
				for(var i=0 ; i<5 ; i++){								
					if(i == 2){
						//使用break可以退出当前的循环
						//break;						
						//continue用于跳过当次循环
						//continue;						
						//使用return可以结束整个函数
						//return;
					}					
					console.log(i);
				}				
				alert("函数执行完了~~~~");
			}
```
#### 立即执行函数

立即执行函数:
	函数定义完，立即被调用，这种函数叫做立即执行函数
	立即执行函数往往只会执行一次
```js
	//用括号标识匿名函数
	(function(){
				alert("我是一个匿名函数~~~");
			})();		
	(function(a,b){
		console.log("a = "+a);
		console.log("b = "+b);
	})(123,456);
```
#### 将函数作为对象的属性(方法)
对象的属性值可以是任何的数据类型，也可以是个函数
```js
			var obj = new Object();
			obj.name = "孙悟空";
			obj.age = 18;
	//对象的属性值可以是任何的数据类型，也可以是个函数
			obj.sayName = function(){
				console.log(obj.name);
			};
```

可以通过调用属性的方法调用该函数
```js
			obj.sayName();//调方法
```
函数也可以称为对象的属性，如果一个函数作为一个对象的属性保存，那么我们称这个函数时这个对象的方法
调用这个函数就说调用对象的方法（method）
但是它只是名称上的区别没有其他的区别
也可以通过字面量的方式来写
```js
			var obj = {
				
				name:"猪八戒",
				age:18,
				sayName:function(){
					console.log(obj.name);
				}
				
			};
			
			.say.Name();
```

#### 枚举对象中的属性(遍历)
```js
<script type="text/javascript">
			
			var obj = {
						name:"孙悟空",
						age:18,
						gender:"男",
						address:"花果山"
					 };		 
			//枚举对象中的属性
			//使用for ... in 语句
			/*
			  语法：
			  	for(var 变量 in 对象){
			  	
			   }
			  
			  for...in语句 对象中有几个属性，循环体就会执行几次
			  	每次执行时，会将对象中的一个属性的名字赋值给变量
			 */
			
			for(var n in obj){
				console.log("属性名:"+n);
				
				console.log("属性值:"+obj[n]);
			}
		</script>
```

#### 全局作用域
```
- 作用域指一个变量的作用的范围
- 在JS中一共有两种作用域：

	1.全局作用域
		- 直接编写在script标签中的JS代码，都在全局作用域
		- 全局作用域在页面打开时创建，在页面关闭时销毁
		- 在全局作用域中有一个全局对象window
			它代表的是一个浏览器的窗口，它由浏览器创建我们可以直接使用
		- 在全局作用域中：
			创建的变量都会作为window对象的属性保存
			创建的函数都会作为window对象的方法保存
		- 全局作用域中的变量都是全局变量
			在页面的任意的部分都可以访问的到

	2.函数作用域
	
```
#### 函数作用域
```JS
函数作用域	
		- 调用函数时创建函数作用域，函数执行完毕以后，函数作用域销毁
		- 每调用一次函数就会创建一个新的函数作用域，他们之间是互相独立的
		- 在函数作用域中可以访问到全局作用域的变量
			在全局作用域中无法访问到函数作用域的变量
		- 当在函数作用域操作一个变量时，它会先在自身作用域中寻找，如果有就直接使用
			如果没有则向上一级作用域中寻找，直到找到全局作用域，
			如果全局作用域中依然没有找到，则会报错ReferenceError
		- 在函数中要访问全局变量可以使用window对象
		
		- 在函数作用域也有声明提前的特性，
			使用var关键字声明的变量，会在函数中所有的代码执行之前被声明
			函数声明也会在函数中所有的代码执行之前执行
			
		-在函数中，不适用var声明的变量都会成为全局变量	
		-在函数中，定义形参就相当于在函数作用域中声明了变量
```

#### 变量的声明提前

使用var关键字声明的变量，会在所有的代码执行之前被声明（但是不会赋值），
但是如果声明变量时不适用var关键字，则变量不会被声明提前


#### 函数的声明提前

使用函数声明形式创建的函数 function 函数(){}
它会在所有的代码执行之前就被创建，所以我们可以在函数声明前来调用函数
使用函数表达式创建的函数，不会被声明提前，所以不能在声明前调用	
```JS
			//函数声明，会被提前创建
			function fun(){
				console.log("我是一个fun函数");
			}
			
			//函数表达式，不会被提前创建
			var fun2 = function(){
				console.log("我是fun2函数");
			};
```

#### this(当前对象)（类似于python的self）
解析器在调用函数每次都会向函数内部传递进一个隐含的参数,
这个隐含的参数就是this，this指向的是一个对象，
这个对象我们称为函数执行的 上下文对象，
根据函数的调用方式的不同，this会指向不同的对象
		1.以函数的形式调用时，this永远都是window
		2.以方法的形式调用时，this就是调用方法的那个对象
```js
			function fun(){
				//console.log("a = "+a+", b = "+b);
				console.log(this.name);
			}
			var obj = {
				name:"孙悟空",
				sayName:fun
			};
			//以方法的形式调用，this是调用方法的对象
			obj.sayName();//this就是obj
```

例子：
```js
		<script type="text/javascript">
			
			//创建一个name变量
			var name = "全局";
			
			//创建一个fun()函数
			function fun(){
				console.log(this.name);
			}
			
			//创建两个对象
			var obj = {
					name:"孙悟空",
					sayName:fun
			};
			
			var obj2 = {
					name:"沙和尚",
					sayName:fun
			};			
			//我们希望调用obj.sayName()时可以输出obj的名字
			//obj.sayName();			
			obj.sayName();	
		</script>
```
补充进阶：
```js
		<script type="text/javascript">
			/*
			 * 在调用函数时，浏览器每次都会传递进两个隐含的参数：
			 * 	1.函数的上下文对象 this
			 * 	2.封装实参的对象 arguments
			 * 		- arguments是一个类数组对象,它也可以通过索引来操作数据，也可以获取长度
			 * 		- 在调用函数时，我们所传递的实参都会在arguments中保存
			 * 		- arguments.length可以用来获取实参的长度
			 * 		- 我们即使不定义形参，也可以通过arguments来使用实参，
			 * 			只不过比较麻烦
			 * 			arguments[0] 表示第一个实参
			 * 			arguments[1] 表示第二个实参 。。。
			 *		- 它里边有一个属性叫做callee，
			 * 			这个属性对应一个函数对象，就是当前正在指向的函数的对象
			 * 		
			 */
			
			function fun(a,b){
				//console.log(arguments.length);
				console.log(arguments.callee == fun);
			}
			
			fun("hello",true);
			
		</script>
```
#### date对象
##### Date对象创建
- 在JS中使用Date对象来表示一个时间
创建一个Date对象,保存当前时间
```js
			//创建一个Date对象
			//如果直接使用构造函数创建一个Date对象，则会封装为当前代码执行的时间
			var d = new Date();
			
			//创建一个指定的时间对象
			//需要在构造函数中传递一个表示时间的字符串作为参数
			//日期的格式  月份/日/年 时:分:秒
			var d2 = new Date("2/18/2011 11:10:30");
```
创建一个指定的时间对象
```js
			//创建一个指定的时间对象
			//需要在构造函数中传递一个表示时间的字符串作为参数
			//日期的格式  月份/日/年 时:分:秒
			var d2 = new Date("2/18/2011 11:10:30");
```
##### 方法
###### getDate()
```js
			/*
			 * getDate()
			 * 	- 获取当前日期对象是几日
			 */
			var date = d2.getDate();
```
###### getDay()
```js
			/*
			 * getDay()
			 * 	- 获取当前日期对象时周几
			 * 	- 会返回一个0-6的值
			 * 		0 表示周日
			 * 		1表示周一
			 * 		。。。
			 */
			var day = d2.getDay();
```
###### getMonth()
```js
			/*
			 * getMonth()
			 * d2 = new Date("12/18/2011 11:10:30");
			 * - 获取当前时间对象的月份
			 * 	- 会返回一个0-11的值
			 * 		0 表示1月
			 * 		1 表示2月
			 * 		11 表示12月
			 */
			var month = d2.getMonth();
```
###### getFullYear()
```
			/*
			 * getFullYear()
			 * 	- 获取当前日期对象的年份
			 */
			var year = d2.getFullYear();
```
###### getTime()
```
			/*
			 * getTime()
			 * 	- 获取当前日期对象的时间戳
			 * 	- 时间戳，指的是从格林威治标准时间的1970年1月1日，0时0分0秒
			 * 		到当前日期所花费的毫秒数（1秒 = 1000毫秒）
			 * 	- 计算机底层在保存时间时使用都是时间戳
			 */
			
			var time = d2.getTime();
```
可以利用时间戳来测试代码的执行的性能
```
			//利用时间戳来测试代码的执行的性能
			//获取当前的时间戳
			var start = Date.now();
			
			for(var i=0 ; i<100 ; i++){
				console.log(i);
			}
			
			var end = Date.now();
			
			
			console.log("执行了："+(end - start)+"毫秒");
```
#### math对象
Math和其他的对象不同，它不是一个构造函数，它属于一个工具类不用创建对象，它里边封装了数学运算相关的属性和方法
比如：Math.PI 表示的圆周率
方法：
```js
			 *	abs()
			    -可以用来计算一个数的绝对值
			 * Math.ceil()
			 * 	- 可以对一个数进行向上取整，小数位只有有值就自动进1
			 * Math.floor()
			 * 	- 可以对一个数进行向下取整，小数部分会被舍掉
			 * Math.round()
			 * 	- 可以对一个数进行四舍五入取整
			 			 * Math.random()
			 * 	- 可以用来生成一个0-1之间的随机数
			 *  - 生成一个0-10的随机数
			 * 	- 生成一个0-x之间的随机数
			 * 		Math.round(Math.random()*x)
			 * 
			 * 	- 生成一个1-10
			 * 	- 生成一个x-y之间的随机数
			 * 		Math.round(Math.random()*(y-x)+x)
			 * max() 可以获取多个数中的最大值
			 * min() 可以获取多个数中的最小值
			 * Math.pow(x,y)
			 * 	返回x的y次幂
			 * 	Math.sqrt()
			 *  用于对一个数进行开方运算
```

#### 包装类
```
			 * 基本数据类型
			 * 	String Number Boolean Null Undefined
			 * 引用数据类型
			 * 	Object
			 * 
			 * 在JS中为我们提供了三个包装类，通过这三个包装类可以将基本数据类型的数据转换为对象
			 * 	String()
			 * 		- 可以将基本数据类型字符串转换为String对象
			 * 	Number()
			 * 		- 可以将基本数据类型的数字转换为Number对象
			 *  Boolean()
			 * 		- 可以将基本数据类型的布尔值转换为Boolean对象
			 * 	但是注意：我们在实际应用中不会使用基本数据类型的对象，
			 * 		如果使用基本数据类型的对象，在做一些比较时可能会带来一些不可预期的结果
```
	方法和属性之能添加给对象，不能添加给基本数据类型
	当我们对一些基本数据类型的值去调用属性和方法时，
	浏览器会临时使用包装类将其转换为对象，然后在调用对象的属性和方法
	调用完以后，在将其转换为基本数据类型

#### 批量创建对象（使用工厂方法创建对象）

创建一个对象
```js
			var obj = {
					name:"孙悟空",
					age:18,
					gender:"男",
					sayName:function(){
						alert(this.name);
					}
			};
```

使用工厂方法创建对象,通过该方法可以大批量的创建对象

```js
			function createPerson(name , age ,gender){
				//创建一个新的对象 
				var obj = new Object();
				//向对象中添加属性
				obj.name = name;
				obj.age = age;
				obj.gender = gender;
				obj.sayName = function(){
					alert(this.name);
				};
				//将新的对象返回
				return obj;
			}
```

然后通过这样的函数就可以批量创建同类对象

```js
			var obj2 = createPerson("猪八戒",28,"男");
			var obj3 = createPerson("白骨精",16,"女");
			var obj4 = createPerson("蜘蛛精",18,"女");
```

使用工厂方法创建的对象，使用的构造函数都是Object
所以创建的对象都是Object这个类型，
就导致我们无法区分出多种不同类型的对象
```js
		//创建一个狗的对象
		function createDog(name , age){
			var obj = new Object();
			obj.name = name;
			obj.age = age;
			obj.sayHello = function(){
				alert("汪汪~~");
			};
			
			return obj;
		}
		//和创建人的一样，检查类型都是Object
```

#### 构造函数
```
构造函数就是一个普通的函数，创建方式和普通函数没有区别,
不同的是构造函数习惯上首字母大写

构造函数和普通函数的区别就是调用方式的不同
普通函数是直接调用，而构造函数需要使用new关键字来调用

 构造函数的执行流程：
 1.立刻创建一个新的对象
 2.将新建的对象设置为函数中this,在构造函数中可以使用this来引用新建的对象
 3.逐行执行函数中的代码
 4.将新建的对象作为返回值返回
 
使用同一个构造函数创建的对象，我们称为一类对象，也将一个构造函数称为一个类。
我们将通过一个构造函数创建的对象，称为是该类的实例

this的情况：
  	1.当以函数的形式调用时，this是window
  	2.当以方法的形式调用时，谁调用方法this就是谁
  	3.当以构造函数的形式调用时，this就是新创建的那个对象

```
创建一个构造函数，专门用来创建Person对象的
```JS
			function Person(name , age , gender){
				this.name = name;
				this.age = age;
				this.gender = gender;
				this.sayName = function(){
					alert(this.name);
				};
			}
```
 使用instanceof可以检查一个对象是否是一个类的实例
 如果是，则返回true，否则返回false
 ```
 语法：
	对象 instanceof 构造函数
 
 ```
 所有的对象都是Object的后代，	所以任何对象和Object左instanceof检查时都会返回true

 ```
	创建一个Person构造函数
	- 在Person构造函数中，为每一个对象都添加了一个sayName方法，
		目前我们的方法是在构造函数内部创建的，
			也就是构造函数每执行一次就会创建一个新的sayName方法
		也是所有实例的sayName都是唯一的。
		这样就导致了构造函数执行一次就会创建一个新的方法，
			执行10000次就会创建10000个新的方法，而10000个方法都是一摸一样的
			这是完全没有必要，完全可以使所有的对象共享同一个方法
			function Person(name , age , gender){
				this.name = name;
				this.age = age;
				this.gender = gender;
				向对象中添加一个方法
				this.sayName = fun;
			}			
 ```

也可以 将sayName方法在全局作用域中定义
```js
			function fun(){
				alert("Hello大家好，我是:"+this.name);
			};
```
将函数定义在全局作用域，污染了全局作用域的命名空间,而且定义在全局作用域中也很不安全
对应此问题，我们提出原型的概念
#### 原型
原型 prototype
```
我们所创建的每一个函数，解析器都会向函数中添加一个属性prototype
这个属性对应着一个对象，这个对象就是我们所谓的原型对象

如果函数作为普通函数调用prototype没有任何作用
当函数以构造函数的形式调用时，它所创建的对象中都会有一个隐含的属性，
指向该构造函数的原型对象，我们可以通过__proto__来访问该属性

原型对象就相当于一个公共的区域，所有同一个类的实例都可以访问到这个原型对象，
我们可以将对象中共有的内容，统一设置到原型对象中。

当我们访问对象的一个属性或方法时，它会先在对象自身中寻找，如果有则直接使用，
如果没有则会去原型对象中寻找，如果找到则直接使用

以后我们创建构造函数时，可以将这些对象共有的属性和方法，统一添加到构造函数的原型对象中，
这样不用分别为每一个对象添加，也不会影响到全局作用域，就可以使每个对象都具有这些属性和方法了
```
图示：

<img src="https://image-1308319148.cos.ap-chengdu.myqcloud.com/main/1654685732665.png" style="zoom:67%;" />

例子：

```js
			function MyClass(){
				
			}
			
			//向MyClass的原型中添加属性a
			MyClass.prototype.a = 123;
			
			//向MyClass的原型中添加一个方法
			MyClass.prototype.sayHello = function(){
				alert("hello");
			};
```
```js
			function Person(name , age , gender){
				this.name = name;
				this.age = age;
				this.gender = gender;
				//向对象中添加一个方法
				//this.sayName = fun;
			}
			//向原型中添加sayName方法
			Person.prototype.sayName = function(){
				alert("Hello大家好，我是:"+this.name);
			};
```

```js
			/*
			 * 创建一个构造函数
			 */
			function MyClass(){
				
			}
			
			//向MyClass的原型中添加一个name属性
			MyClass.prototype.name = "我是原型中的名字";
			
			var mc = new MyClass();
			mc.age = 18;
			
			//console.log(mc.name);
			
			//使用in检查对象中是否含有某个属性时，如果对象中没有但是原型中有，也会返回true
			//console.log("name" in mc);
			
			//可以使用对象的hasOwnProperty()来检查对象自身中是否含有该属性
			//使用该方法只有当对象自身中含有属性时，才会返回true
			//console.log(mc.hasOwnProperty("age"));
			/*
			 * 原型对象也是对象，所以它也有原型，
			 * 	当我们使用一个对象的属性或方法时，会现在自身中寻找，
			 * 		自身中如果有，则直接使用，
			 * 		如果没有则去原型对象中寻找，如果原型对象中有，则使用，
			 * 		如果没有则去原型的原型中寻找,直到找到Object对象的原型，
			 * 		Object对象的原型没有原型，如果在Object原型中依然没有找到，则返回undefined
			 */
```

#### toString方法
当我们直接在页面中打印一个对象时，事件上是输出的对象的toString()方法的返回值（会显示[object Object]，对象的构造函数类）
如果我们希望在输出对象时不输出[object Object]，可以为对象添加一个toString()方法
```js
			function Person(name , age , gender){
				this.name = name;
				this.age = age;
				this.gender = gender;
			}
			
			//修改Person原型的toString(重写toString方法，现在浏览器版本用不到)
			Person.prototype.toString = function(){
				return "Person[name="+this.name+",age="+this.age+",gender="+this.gender+"]";
			};
			//创建一个Person实例
			var per = new Person("孙悟空",18,"男");
			var per2 = new Person("猪八戒",28,"男");
```
#### 函数对象的方法（call()和apply()）
```js
			function fun(a,b) {
				console.log("a = "+a);
				console.log("b = "+b);
				//alert(this);
			}
			
			var obj = {
				name: "obj",
				sayName:function(){
					alert(this.name);
				}
			};
```
```
			/*
			 * call()和apply()
			 * 	- 这两个方法都是函数对象的方法，需要通过函数对象来调用
			 * 	- 当对函数调用call()和apply()都会调用函数执行
			 * 	- 在调用call()和apply()可以将一个对象指定为第一个参数
			 * 		此时这个对象将会成为函数执行时的this
			 * 	- call()方法可以将实参在对象之后依次传递
			 * 	- apply()方法需要将实参封装到一个数组中统一传递
			 * 
			 * 	- this的情况：
			 * 		1.以函数形式调用时，this永远都是window
			 * 		2.以方法的形式调用时，this是调用方法的对象
			 * 		3.以构造函数的形式调用时，this是新创建的那个对象
			 * 		4.使用call和apply调用时，this是指定的那个对象
			 */
```
##### call()
call()方法可以将实参在对象之后依次传递

##### apply()
apply()方法需要将实参封装到一个数组中统一传递

####  垃圾回收（GC）
```JS
- 就像人生活的时间长了会产生垃圾一样，程序运行过程中也会产生垃圾
	这些垃圾积攒过多以后，会导致程序运行的速度过慢，
	所以我们需要一个垃圾回收的机制，来处理程序运行过程中产生垃圾
- 当一个对象没有任何的变量或属性对它进行引用，此时我们将永远无法操作该对象，
	此时这种对象就是一个垃圾，这种对象过多会占用大量的内存空间，导致程序运行变慢，
	所以这种垃圾必须进行清理。
- 在JS中拥有自动的垃圾回收机制，会自动将这些垃圾对象从内存中销毁，
	我们不需要也不能进行垃圾回收的操作
- 我们需要做的只是要将不再使用的对象设置null即可
	var obj = new Object();
	obj = null;
```
### 数组

#### 数组介绍
对象可以分为内建对象，宿主对象，自定义对象。数组属于内建对象。
```
数组（Array）
		- 数组也是一个对象
		- 它和我们普通对象功能类似，也是用来存储一些值的
		- 不同的是普通对象是使用字符串作为属性名的，
			而数组时使用数字来作为索引操作元素
		- 索引：
			从0开始的整数就是索引
		- 数组的存储性能比普通对象要好，在开发中我们经常使用数组来存储一些数据
```
如何创建数组：
```js
			//创建数组对象
			var arr = new Array();//Array()就是数组的构造函数
```
向数组中添加元素
```js
			// 向数组中添加元素
			// 语法：数组[索引] = 值			 
			arr[0] = 10;
			arr[1] = 33;
			arr[2] = 22;
			arr[3] = 44;
```
读取数组中的元素
```js
			/*
			 * 读取数组中的元素
			 * 语法：数组[索引]
			 * 	如果读取不存在的索引，他不会报错而是返回undefined
			 */			
			console.log(arr[3]);
```
获取数组的长度
```js
			/*
			 * 获取数组的长度
			 * 可以使用length属性来获取数组的长度(元素的个数)
			 * 	语法：数组.length
			 * 
			 * 对于连续的数组，使用length可以获取到数组的长度（元素的个数）
			 * 对于非连续的数组，使用length会获取到数组的最大的索引+1
			 * 		尽量不要创建非连续的数组
			 */
			console.log(arr.length);
			
			/*
			 *  还可以修改length
			 * 	如果修改的length大于原长度，则多出部分会空出来
			 *  如果修改的length小于原长度，则多出的元素会被删除
			 */
			//小技巧
			//向数组的最后一个位置添加元素
			//语法：数组[数组.length] = 值;
			arr[arr.length] = 70;
			arr[arr.length] = 80;
			arr[arr.length] = 90;
```

#### 数组的字面量
使用字面量来创建数组
```js
			//使用字面量来创建数组
			//语法:[]
			var arr = [];
			
			//使用字面量创建数组时，可以在创建时就指定数组中的元素
			var arr = [1,2,3,4,5,10];
			
			//使用构造函数创建数组时，也可以同时添加元素，将要添加的元素作文构造函数的参数传递
			//元素之间使用,隔开
			var arr2 = new Array(10,20,30);
			
			//创建一个数组数组中只有一个元素10
			arr = [10];
			
			//创建一个长度为10的数组
			arr2 = new Array(10);
			
			//数组中的元素可以是任意的数据类型
			arr = ["hello",1,true,null,undefined];
			
			//也可以是对象
			var obj = {name:"孙悟空"};
			arr[arr.length] = obj;
			arr = [{name:"孙悟空"},{name:"沙和尚"},{name:"猪八戒"}];
			
			//也可以是一个函数
			arr = [function(){alert(1)},function(){alert(2)}];
			//数组中也可以放数组，如下这种数组我们称为二维数组
			arr = [[1,2,3],[3,4,5],[5,6,7]];
```

#### 数组的方法
```js
			//创建一个数组
			var arr = ["孙悟空","猪八戒","沙和尚"];
```

##### push()
```js
			/*
			 * push()
			 * 	- 该方法可以向数组的末尾添加一个或多个元素，并返回数组的新的长度
			 * 	- 可以将要添加的元素作为方法的参数传递，
			 * 		这样这些元素将会自动添加到数组的末尾
			 * 	- 该方法会将数组新的长度作为返回值返回
			 */
			
			var result = arr.push("唐僧","蜘蛛精","白骨精","玉兔精");
```

##### pop()
```js
			/*
			 * pop()
			 * 	- 该方法可以删除数组的最后一个元素,并将被删除的元素作为返回值返回
			 */
			result = arr.pop();
```

##### unshift()
```js
			/*
			 * unshift()
			 * 	- 向数组开头添加一个或多个元素，并返回新的数组长度
			 * 	- 向前边插入元素以后，其他的元素索引会依次调整
			 */		
			arr.unshift("牛魔王","二郎神");
```

##### shift()
```js
			/*
			 * shift()
			 * 	- 可以删除数组的第一个元素，并将被删除的元素作为返回值返回
			 */
			result = arr.shift();
```
##### slice()
```js
			/*
			 * slice()
			 * 	- 可以用来从数组提取指定元素,相当与python里数组的切片
			 * 	- 该方法不会改变元素数组，而是将截取到的元素封装到一个新数组中返回
			 * 	- 参数：
			 * 		1.截取开始的位置的索引,包含开始索引
			 * 		2.截取结束的位置的索引,不包含结束索引
			 * 			- 第二个参数可以省略不写,此时会截取从开始索引往后的所有元素
			 * 		- 索引可以传递一个负值，如果传递一个负值，则从后往前计算
			 * 			-1 倒数第一个
			 * 			-2 倒数第二个
			 */
			
			var result = arr.slice(1,4);
```

##### splice()
```js
			/*
			 * splice()
			 * 	- 可以用于删除数组中的指定元素
			 * 	- 使用splice()会影响到原数组，会将指定元素从原数组中删除
			 * 		并将被删除的元素作为返回值返回
			 * 	- 参数：
			 * 		第一个，表示开始位置的索引
			 * 		第二个，表示删除的数量
			 * 		第三个及以后。。
			 * 			可以传递一些新的元素，这些元素将会自动插入到开始位置索引前边
			 * 	
			 */
			
			arr = ["孙悟空","猪八戒","沙和尚","唐僧","白骨精"];
			var result = arr.splice(3,0,"牛魔王","铁扇公主","红孩儿");
```
#####  concat()
```js
			var arr = ["孙悟空","猪八戒","沙和尚"];
			var arr2 = ["白骨精","玉兔精","蜘蛛精"];
			var arr3 = ["二郎神","太上老君","玉皇大帝"];
			
			/*
			 * concat()可以连接两个或多个数组，并将新的数组返回
			 * 	- 该方法不会对原数组产生影响
			 */
			var result = arr.concat(arr2,arr3,"牛魔王","铁扇公主");
	
```
##### join()
 ```js
 /*
  * join()
  * 	- 该方法可以将数组转换为一个字符串
  * 	- 该方法不会对原数组产生影响，而是将转换后的字符串作为结果返回
  * 	- 在join()中可以指定一个字符串作为参数，这个字符串将会成为数组中元素的连接符
  * 		如果不指定连接符，则默认使用,作为连接符
  */
 arr = ["孙悟空","猪八戒","沙和尚","唐僧"];
 result = arr.join("-");
 ```

 ##### sort()
```js
			arr = ["b","d","e","a","c"];
			/*
			 * sort()
			 * 	- 可以用来对数组中的元素进行排序
			 * 	- 也会影响原数组，默认会按照Unicode编码进行排序
			 */
			arr.sort();
```
注意：
```
			/*
			 * 即使对于纯数字的数组，使用sort()排序时，也会按照Unicode编码来排序，
			 * 	所以对数字进排序时，可能会得到错误的结果。
			 * 
			 * 我们可以自己来指定排序的规则
			 * 	我们可以在sort()添加一个回调函数，来指定排序规则，
			 * 		回调函数中需要定义两个形参,
			 * 		浏览器将会分别使用数组中的元素作为实参去调用回调函数
			 * 		使用哪个元素调用不确定，但是肯定的是在数组中a一定在b前边
			 * 	- 浏览器会根据回调函数的返回值来决定元素的顺序，
			 * 		如果返回一个大于0的值，则元素会交换位置
			 * 		如果返回一个小于0的值，则元素位置不变
			 * 		如果返回一个0，则认为两个元素相等，也不交换位置
			 * 
			 * 	- 如果需要升序排列，则返回 a-b
			 * 		如果需要降序排列，则返回b-a
			 */
```
所以有：
```js
			arr = [5,4,2,1,3,6,8,7];
			
			arr.sort(function(a,b){
				
				//前边的大(这样写太过于麻烦)
				/*if(a > b){
					return -1;
				}else if(a < b){
					return 1;
				}else{
					return 0;
				}*/
				
				//升序排列
				//return a - b;
				
				//降序排列
				return b - a;
			});
```


 ######  reverse()
```js
			/*
			 * reverse()
			 * 	- 该方法用来反转数组（前边的去后边，后边的去前边）
			 * 	- 该方法会直接修改原数组
			 */
			
			arr.reverse();
```
#### 数组的遍历
##### 利用for循环遍历

```js
			//创建一个数组
			var arr = ["孙悟空","猪八戒","沙和尚","唐僧","白骨精"];
			
			//所谓的遍历数组，就是将数组中所有的元素都取出来
			for(var i=0 ; i<arr.length ; i++){
				console.log(arr[i]);
			}
```
##### forEach()遍历
一般我们都是使用for循环去遍历数组，JS中还为我们提供了一个方法，用来遍历数组
```js
			 /*forEach()
			 * 		- 这个方法只支持IE8以上的浏览器
			 * 			IE8及以下的浏览器均不支持该方法，所以如果需要兼容IE8，则不要使用forEach
			 * 			还是使用for循环来遍历
			 */
			//创建一个数组
			var arr = ["孙悟空","猪八戒","沙和尚","唐僧","白骨精"];
			
			/*
			 * forEach()方法需要一个函数作为参数
			 * 	- 像这种函数，由我们创建但是不由我们调用的，我们称为回调函数
			 * 	- 数组中有几个元素函数就会执行几次，每次执行时，浏览器会将遍历到的元素
			 * 		以实参的形式传递进来，我们可以来定义形参，来读取这些内容
			 * 	- 浏览器会在回调函数中传递三个参数：
			 * 		第一个参数，就是当前正在遍历的元素
			 * 		第二个参数，就是当前正在遍历的元素的索引
			 * 		第三个参数，就是正在遍历的数组
			 * 		
			 */
			arr.forEach(function(value , index , obj){
				console.log(value);
			});			
```

#### 练习
##### 练习1
条件：
```js
			function Person(name , age , gender){
				this.name = name;
				this.age = age;
			}
			//创建一个Person对象
			var per = new Person("孙悟空",18);
			var per2 = new Person("猪八戒",28);
			var per3 = new Person("红孩儿",8);
			var per4 = new Person("蜘蛛精",16);
			var per5 = new Person("二郎神",38);
			/*
			 * 将这些person对象放入到一个数组中
			 */
			var perArr = [per,per2,per3,per4,per5];
```
要求：创建一个函数，可以将perArr中的满18岁的Person提取出来，然后封装到一个新的数组中并返回
arr:形参，要提取信息的数组
```js
			function getAdult(arr){
				//创建一个新的数组
				var newArr = [];
				
				//遍历arr，获取arr中Person对象
				for(var i=0 ; i<arr.length ; i++){
					var p = arr[i];
					//判断Person对象的age是否大于等于18
					if(p.age >= 18){
						//如果大于等于18，则将这个对象添加到newArr中
						//将对象放入到新数组中
						newArr.push(p);
					}
				}
				//将新的数组返回
				return newArr;
				
			}
			
			var result = getAdult(perArr);
```

##### 练习2
```js
			//创建一个数组
			var arr = [1,2,3,2,2,1,3,4,2,5];
			
			//去除数组中重复的数字
```
利用嵌套循环去重
```js
			//去除数组中重复的数字
			//获取数组中的每一个元素
			for(var i=0 ; i<arr.length ; i++){
				//console.log(arr[i]);
				/*获取当前元素后的所有元素*/
				for(var j=i+1 ; j<arr.length ; j++){
					//console.log("---->"+arr[j]);
					//判断两个元素的值是否相等
					if(arr[i] == arr[j]){
						//如果相等则证明出现了重复的元素，则删除j对应的元素
						arr.splice(j,1);
						//当删除了当前j所在的元素以后，后边的元素会自动补位
						//此时将不会在比较这个元素吧，我需要在比较一次j所在位置的元素
						//使j自减
						j--;
					}
				}
			}
```

### 正则表达式

#### 正则表达式介绍
通常情况下用户输入邮件格式：
```
			 * 	- admin@atguigu.com
			 *  - admin@.com   adminatguigu.com
			 *  - 邮件的规则：
			 * 		1.前边可以是xxxx乱七八糟
			 * 		2.跟着一个@
			 * 		3.后边可以是xxxx乱七八糟
			 * 		4..com获取其他的乱七八糟
```
正则表达式用于定义一些字符串的规则，计算机可以根据正则表达式，来检查一个字符串是否符合规则，
获取将字符串中符合规则的内容提取出来（给计算机看的一种规则，它也是一个对象）

#### 创建正则表达式的对象
```js
			/*
			 * 语法：
			 * 	var 变量 = new RegExp("正则表达式","匹配模式");
			 *  使用typeof检查正则对象，会返回object
			 * 	var reg = new RegExp("a"); 这个正则表达式可以来检查一个字符串中是否含有a
			 * 在构造函数中可以传递一个匹配模式作为第二个参数，
			 * 		可以是 
			 * 			i 忽略大小写 
			 * 			g 全局匹配模式
			 */
```
 正则表达式的方法：test()
 ```js
 /*
  * 正则表达式的方法：
  * 	test()
  * 	 - 使用这个方法可以用来检查一个字符串是否符合正则表达式的规则，
  * 		如果符合则返回true，否则返回false
  */
 var result = reg.test(str);
 //console.log(result);
 console.log(reg.test("Ac"));
 ```
#### 正则表达式语法
##### 使用字面量来创建正则表达式：
```js
			/*
			 * 使用字面量来创建正则表达式
			 * 	语法：var 变量 = /正则表达式/匹配模式
			 * 使用字面量的方式创建更加简单
			 * 	使用构造函数创建更加灵活
			 * 
			 */
			var reg = new RegExp("a","i");
			//改写：
			var reg = /a/i;
```
##### 逻辑判断
```js
			//创建一个正则表达式，检查一个字符串中是否有a或b
			/*
			 * 使用 | 表示或者的意思
			 */
			reg = /a|b|c/;
			
			/*
			 * 创建一个正则表达式检查一个字符串中是否有字母
			 */
			reg = /a|b|c|d|e|f|g/;
			
			/*
			 * []里的内容也是或的关系
			 * [ab] == a|b
			 * [a-z] 任意小写字母
			 * [A-Z] 任意大写字母
			 * [A-z] 任意字母
			 * [0-9] 任意数字
			 */
			reg = /[A-z]/;
			
			//检查一个字符串中是否含有 abc 或 adc 或 aec
			reg = /a[bde]c/;
			
			/*
			 * [^ ] 除了
			 */
			reg = /[^ab]/;
			
```
##### 量词
```
			 * 量词
			 * 	- 通过量词可以设置一个内容出现的次数
			 * 	- 量词只对它前边的一个内容起作用
			 * 	- {n} 正好出现n次
			 * 	- {m,n} 出现m-n次
			 * 	- {m,} m次以上
			 * 	- + 至少一个，相当于{1,}
			 * 	- * 0个或多个，相当于{0,}
			 * 	- ? 0个或1个，相当于{0,1}
```
##### 开头结尾
```js
			/*
			 * 检查一个字符串中是否以a开头
			 * 	^ 表示开头
			 * 	$ 表示结尾
			 */
			reg = /^a/; //匹配开头的a
			
			reg = /a$/; //匹配结尾的a
			/*
			 * 如果在正则表达式中同时使用^ $则要求字符串必须完全符合正则表达式
			 */
			reg = /^a$/;
```
练习： 创建一个正则表达式，用来检查一个字符串是否是一个合法手机号
```js
			 * 手机号的规则：
			 * 	1 3 567890123 （11位）
			 * 	
			 * 	1. 以1开头
			 *  2. 第二位3-9任意数字
			 * 	3. 三位以后任意数字9个
			 * 	
			 * 	^1   [3-9]  [0-9]{9}$\
			 
			 var phoneStr = "13067890123";
			 var phoneReg = /^1[3-9][0-9]{9}$/;
```
##### 元字符
如何检查一个字符串中是否含有 .
. 表示任意字符
在正则表达式中使用\作为转义字符
\. 来表示.
```js
			var reg = /\./;
````
\\  表示\
注意：使用构造函数时，由于它的参数是一个字符串，而\是字符串中转义字符，
	如果要使用\则需要使用\\来代替
```js
			reg = new RegExp("\\.");
			reg = new RegExp("\\\\");
```

			 * \w
			 * 	- 任意字母、数字、_  [A-z0-9_]
			 * \W
			 * 	- 除了字母、数字、_  [^A-z0-9_]
			 * \d
			 * 	- 任意的数字 [0-9]
			 * \D
			 * 	- 除了数字 [^0-9]
			 * \s
			 * 	- 空格
			 * \S
			 * 	- 除了空格
			 * \b
			 * 	- 单词边界
			 * \B
			 * 	- 除了单词边界
```js
			/*
			 * 创建一个正则表达式检查一个字符串中是否含有单词child
			 */
			
			reg = /\bchild\b/;
```
例子：去除字符串中的空格
```js
			//接收一个用户的输入
			//var str = prompt("请输入你的用户名:");
			
			var str = "              he      llo                ";
			
			//去除掉字符串中的前后的空格
			//去除空格就是使用""来替换空格
			console.log(str);
			
			//str = str.replace(/\s/g , "");
			
			//去除开头的空格
			str = str.replace(/^\s*/, "");
			//去除结尾的空格
			str = str.replace(/\s*$/, "");
			// /^\s*|\s*$/g 匹配开头和结尾的空格
			str = str.replace(/^\s*|\s*$/g,"");
			
			
			console.log(str);
```
#### 正则表达式的方法
##### 字符串和正则相关的方法
######  split()
	 split()
		- 可以将一个字符串拆分为一个数组
		- 方法中可以传递一个正则表达式作为参数，这样方法将会根据正则表达式去拆分字符串
		- 这个方法即使不指定全局匹配，也会全都插分
```js
			var str = "1a2b3c4d5e6f7";
			/*
			 * 根据任意字母来将字符串拆分
			 */
			var result = str.split(/[A-z]/);
```

######  search()
		 * 	- 可以搜索字符串中是否含有指定内容
		 * 	- 如果搜索到指定内容，则会返回第一次出现的索引，如果没有搜索到返回-1
		 * 	- 它可以接受一个正则表达式作为参数，然后会根据正则表达式去检索字符串
		 * 	- serach()只会查找第一个，即使设置全局匹配也没用
```js
			str = "hello abc hello aec afc";
			/*
			 * 搜索字符串中是否含有abc 或 aec 或 afc
			 */
			result = str.search(/a[bef]c/);
```
######  match()
			 * 	- 可以根据正则表达式，从一个字符串中将符合条件的内容提取出来
			 * 	- 默认情况下我们的match只会找到第一个符合要求的内容，找到以后就停止检索
			 * 		我们可以设置正则表达式为全局匹配模式，这样就会匹配到所有的内容
			 * 		可以为一个正则表达式设置多个匹配模式，且顺序无所谓
			 * 	- match()会将匹配到的内容封装到一个数组中返回，即使只查询到一个结果
```js
			str = "1a2a3a4a5e6f7A8B9C";
			
			result = str.match(/[a-z]/ig);
```
######  replace()
			 * 	- 可以将字符串中指定内容替换为新的内容
			 *  - 参数：
			 * 		1.被替换的内容，可以接受一个正则表达式作为参数
			 * 		2.新的内容
			 *  - 默认只会替换第一个
```js
			result = str.replace(/[a-z]/gi , "@_@");
			result = str.replace(/[a-z]/gi , "");
```
#### 练习
##### 邮件的正则表达式
电子邮件:	hello  .nihao          @     abc  .com.cn
任意字母数字下划线    .任意字母数字下划线  @   任意字母数字     .任意字母（2-5位）   .任意字母（2-5位）
\w{3,}  (\.\w+)*  @  [A-z0-9]+  (\.[A-z]{2,5}){1,2}
```js
			var emailReg = /^\w{3,}(\.\w+)*@[A-z0-9]+(\.[A-z]{2,5}){1,2}$/;
			
			var email = "abc.hello@163.com";
			
			console.log(emailReg.test(email));
```

### JSON
```JS
			/*
			 * JSON
			 * 	- JS中的对象只有JS自己认识，其他的语言都不认识
			 * 	- JSON就是一个特殊格式的字符串，这个字符串可以被任意的语言所识别，
			 * 		并且可以转换为任意语言中的对象，JSON在开发中主要用来数据的交互
			 * 	- JSON
			 * 		- JavaScript Object Notation JS对象表示法
			 * 		- JSON和JS对象的格式一样，只不过JSON字符串中的属性名必须加双引号
			 * 			其他的和JS语法一致
			 * 		JSON分类：
			 * 			1.对象 {}
			 * 			2.数组 []
			 * 
			 * 		JSON中允许的值：
			 * 			1.字符串
			 * 			2.数值
			 * 			3.布尔值
			 * 			4.null
			 * 			5.对象
			 * 			6.数组
			 */
```
创建一个对象：
```js
			var arr = '[1,2,3,"hello",true]';
			
			var obj2 = '{"arr":[1,2,3]}';
			
			var arr2 ='[{"name":"孙悟空","age":18,"gender":"男"},{"name":"孙悟空","age":18,"gender":"男"}]';
	
```

 将JSON字符串转换为JS中的对象
 在JS中，为我们提供了一个工具类，就叫JSON
 这个对象可以帮助我们将一个JSON转换为JS对象，也可以将一个JS对象转换为JSON
 ```js
 			var json = '{"name":"孙悟空","age":18,"gender":"男"}';
 ```

 json --> js对象:JSON.parse()
 - 可以将以JSON字符串转换为js对象
 - 它需要一个JSON字符串作为参数，会将该字符串转换为JS对象并返回
 ```js
 var o = JSON.parse(json);
 var o2 = JSON.parse(arr);
 ```

JS对象 ---> JSON:JSON.stringify()
- 可以将一个JS对象转换为JSON字符串
- 需要一个js对象作为参数，会返回一个JSON字符串
```js
			var obj3 = {name:"猪八戒" , age:28 , gender:"男"}; 
			var str = JSON.stringify(obj3);
			//console.log(str);
```