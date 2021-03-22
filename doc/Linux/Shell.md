## Shell

##### 概述

- Shell 是一个用C语言编写的程序它是用户使用Linux的桥梁。
2. Shell 既是种命令语言,又是一种程序设计语言。
- Shell 是指一种应用程序，这个应用程序提供了一个界面,用户通过这个界面访问操作系统内核的服务 

##### Shell环境

- Shell编程只要有一个能编写代码的文本编辑器vi和一个能解释执行的脚本解释器就可以了。
- 也即/bin/bash。 

##### Shell的版本类型

- Bourne Shell ( /usr/bin/sh或/bin/sh ) 
- **Bourne Again Shell ( /bin/bash )**（主流使用）
- C Shell ( /usr/bin/csh )
- K Shell ( /usr/bin/ksh )
- Shell for Root ( /sbin/sh )

##### shell脚本

- 将多个Linux市令写在一个脚本文件中，用户只需要执行这个脚本文件一次，就会把脚本中所包含的所
  有命令全部执行

##### shell构成

- bash环境文件
  - .bash_ profile
    - 设置环境变量
    - **帐户一建立，该文件就存在（随着用户的产生而产生）**
  - .bashrc
    - 存放针对bash的命令
    - 每次启动就执行它
    - 在.bash_ profile之后执行
  - .bash_ logout 
    - 仅在退出注册时运行
  - .bash history
    - 历史纪录

##### shell脚本格式

- 格式：vi shell_script.sh
- 脚本第一行格式：#!/bin/bash
- 符号#!用来指定该脚本文件的解析程序，这里使用的是bin目录下的bash解析器。当编辑好脚本后，如果要执行该脚本,还必须使其具有可执行属性。

![image-20210322101409385](Shell.assets/image-20210322101409385.png)

- 变量调用：$para_name
- 只读变量：使用readonly命令可以将变量定义为只读变量,只读变量的值不能被改变。![image-20210322111708029](Shell.assets/image-20210322111708029.png)
- 删除变量：使用unset命令可以删除变量，变量被删除后不能再次进行使用，且unset命令不能删除只读变量。语法为：unset variable_name
- 求解字符串的长度：$(#para_name)能够获取一个字符串的长度
- 截取字符串：用“:”来进行提取即可，语法为”para_name:start_index:length of cut out“
- 解析方式一：chmod +x脚本文件的名字   eg：./脚本文件的名字
- 解析方式二：/bin/bash  脚本文件的名字

##### 

##### shell数组

- 定义格式：array_name = (value0 value1 ... valuen)