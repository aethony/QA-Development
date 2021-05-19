# JavaScript

##### 简介

- JavaScript是一种具有面向对象能力的、解释型的程序设计语言。

- 它是基于对象和事件驱动并具有相对安全性的客户端脚本语言。因为他不需要在一个语言环境下运行，而只需要支持它的浏览器即可。它的主要目的是，验证发往服务器端的数据、增加Web互动、加强用户体验度等。
- 基于对象：提供好了很多对象，可以直接拿过来使用
- 事件驱动： html做网站静态效果，JavaScript实现动态效果
- 客户端：专门指的是浏览器
- JS的作用：操作HTML和CSS

##### 特点

- 松散型:JavaScript语言核心与C、C++、Java 相似，比如条件判断、循环、运算符等 。但，它却是一种松散类型的语言，也就是说，它的变量不必具有一个明确的类型。
- 解释型:不需要编译。浏览器直接解释执行。
- 基于对象:我们可以直接使用JS已经创建的对象。Math String
- 安全性:不允许访问本地硬盘，不能将数据写入到服务器上。
- 跨平台: js依赖于浏览器本身，与操作系统无关。。

##### 如何在网页中写JS

- 在页面中直接嵌入JS

  - ```javascript
    < script language= "javascript" >
    js程序
    </script>
    ```

  - js代码可以插入在<head> </head>标签中间，也可以放在< body> </body>标签中间。

  - 最常用的是放在<head> </head>

- 在外部当中引用JS

  - 如果脚本比较复杂或者是同一段代码被很多页面所使用，则可以将这些脚本代码放置在一个单独的文件中，该文件的扩展名是.js,然后再需要使用该代码的web页面中链接该JavaScript文件即可。

  - ```javascript
    <script language= "javascript" src=”.js后缀的文件路径" > </script>
    ```

  - 一般写在<head> </head>中间比较好

  - 在js后缀的文件中，不需要使用<script> </script>标签对括起来。

  - <body onload= "函数名()" >表示的是加载页面时调用函数，函数是定义在js后缀的文件中。

  - **当一个script标签一旦引用了外部的JS文件，那么在这个标签中如果还存在js代码，是不会执行的。**

##### 语法

- js的变量区分大小写：username userName这是两个不同的变量

- 每行结尾的分号可有可无，如果语句的结束处没有分号，那么js会自动将这行代码的结尾作为语句的结尾。
  alert(" Hello World");
  alert(" Hello World")

- 标识符：所谓标识符，就是指变量、函数、属性的名字，或者函数的参数。标识符可以是下列格式规则组合起来的一或多个字符:

  - 第一字符必须是一个字母、下划线( )或一个美元符号($)。
  - 其他字符可以是字母、下划线、 美元符号或数字。
  - 不能把关键字、保留字、true、 false和nulI作为标识符。例如: myName、book123等

- 可以使用一个var声明多个变量，比如：

- ```javascript
  var now,year,month,date;
  可以在声明变量的同时对它进行赋值，也就是初始化。
  var now= "2015- 10-10",year= "2015",month="10",date="10";
  如果只是声明了变量，没有赋值，那么该变量的默认值是undefined
  JavaScript是弱类型，声明的时候不需要指定变量的类型，变量的类型将根据变
  量的值来确定。
  ```

- 注释

  - 单行注释：//；单行注释使用双斜线"//"开头，在"//"后面的文字即为注释内容，注释的内容在代码执行过程中不起作用。

  - ```javascript
    var now=new Date();//获取日期对象
    ```

  - 多行注释：多行注释以"/*"开头，以"*/"结尾， 在两者之间的内容为注释内容，在代码执行过程中不起任何作用。

  - ```javascript
    /*
    *功能:获取当前日期
    *作者: tony
    */
    function getClock(){
    //内容
    
    }
    ```

- 定义变量时至使用var运算符。

  - ```javascript
    比如: var username= "tom' ;正确
    var age=30;正确
    int age=30;错误
    ```

- 使用大括号标签代码块：{ //代码}被封装在大括号内的语句按照顺序执行。

##### 数据类型

- 数值型
  - 整型
  - 浮点类型
- 字符类型：字符串型数据是使用单引号或者双引号括起来的一个或者多个字符。
- 布尔类型
- 转义字符
- 空值：null；定义空或者不存在的引用
- 为定义的值：已经声明但是没有赋值的变量
- 第四章开始

##### 流程控制

###### if语句

```javascript
1、if(expression){ 
//expression为true的时候执行里面的内容
}

2、if(expression){
//expression为true的时候执行里面的内容
}else{ 
//expression为false的时候执行里面的内容
}

3、if(expression1){
//expression1为true的时候执行里面的内容
}else if(expression2){
//expression2为true的时候执行里面的内容
}else if(expression3){ 
//expression3为true的时候执行里面的内容
}else{
//这个else可有可无。如果有的话，则上述条件
//都不满足的时候执行else

```

###### Switch语句

```javascript
语法格式:
switch(expression){
        
case judgement 1:statement1:break;
case judgement2:statement2:break;
default:defaultstatement;
        
}

```

