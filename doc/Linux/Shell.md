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