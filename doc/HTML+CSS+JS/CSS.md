## CSS

##### 样式表的基本结构

- 放置于head标签之间

- ```css
  <STYLE type="text/css">
  P {color:red; font- size:30px; font-family:隶书;}   //样式标签
  .....
  </STYLE>
  ```

- 而针对某一类下需要共享CSS样式，则可以采用". class_name"的方式来对对应类名下的属性进行引用声明

- ```css
  <STYLE type="text/css">
  .test {color:red; font- size:30px; font-family:隶书;}   //样式标签
  .....
  </STYLE>
  <body>
      <p class="test">我是段落标签</p>
      <ins class="test">我是插入标签</ins>
  </body>
  
  ```

- 常见的文本属性

  - |  文本属性   |         说明         |
    | :---------: | :------------------: |
    |  font-size  |       字体大小       |
    | font-family |       字体类型       |
    | font-style  |       字体样式       |
    |    color    | 设置或检索文本的颜色 |
    | text-align  |       文本对齐       |

    

- 当类属性和标签属性同时覆盖时，相同的属性会覆盖，不同的属性会融合。

- 常见的背景属性

  - | 背景属性          | 说明                                                         |
    | ----------------- | ------------------------------------------------------------ |
    | background-color  | 设置背景颜色                                                 |
    | background-image  | 设置背景图像                                                 |
    | background repeat | 设置一个指定的图像如何被重复，可取值repeat-x、repeat、no- repeat、repeat-y |

- 行内(嵌入)样式表：样式表的申明只针对某一行的记录进行操作的生效。即在开始标签中使用style关键字来进行指定样式。

- 外部样式表文件：通过将样式表写成一个单独的外部文件并进行引用来实现对某一样式的引用操作。

- 外部样式文件的导入方式有两种：

  - 链接（LINK）外部样式表

  - ```html
    <HEAD>
    <LINK href="newsyle.css" rel="stylesheet" type="text/css">
    ///rel属性能够更好地兼容css和html结合后的样子   
    </HEAD>
    ```

  - 导入（@import）外部样式表

  - ```html
    使用@import导入，语法:
    <HEAD>
    <STYLE TYPE="text/css">
    @ import "newstyle.css";
    </STYLE>
    </HEAD>
    ```

    

