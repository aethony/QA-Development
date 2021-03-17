## Linux

- Linux具备现代-切功能完整的UNIX系统所具备的全部特征,其中包括真正的多任务、虚拟内存、共享库、需求装载、共享的写时复制程序执行、优秀的内存管理以及TCP/IP网络支持等。
- Linux的基本思想有两点:
  - 第一：一切都是文件
  - 第二：每个软件都有确定的用途。其中第一条详细来讲就是 系统中的所有都归结为一个文件，包括命令、硬件和软件设备、操作系统、进程等
- 多用户、多任务
  - Linux支持多用户,各个用户对于自己的文件设备有自己特殊的权利,保证了各用户之间互不影响。
  - 多任务则是现在电脑最主要的一个特点, Linux可以使多个程序同时并独立地运行。
- 完全免费
  - Linux是一款免费的操作系统，用户可以通过网络或其他途径免费获得,并可以任意修改其源代码。
- 内核版本----主版本号次版本号修订次数
  - 奇数版本---开发版本 eg：2.5.1
  - 偶数版本---稳定版本 eg：2.6.1



## Linux目录结构

- FHS标准( Filesystem Hierarchy Standard ) :
  - /boot：启动目录，内核存放地
  - /etc：配置文件存放地
  - /tmp：程序产生的临时文件
  - /home：用户的目录，新增用户账号时，用户的家目录都存放在此目录
  - /lib：库文件,程序在执行过程中，需要调用一些额外的参数时需要函数库的协助
  - /bin：可执行文件和常用的Linux命令
  - /sbin：系统管理员的命令和工具
  - /usr：应用程序和文件的安装地
  - /mnt：挂接其他文件系统
  - /root：root帐户的home目录
  - /dev：存放linux系统 下的设备文件



## Linux常见命令

1. vi使用:命令模式、末行模式、编辑模式。

- vi
  - 功能：生成新文件或者编辑、查看文件。
  - 格式：vi file _name。eg：vi test
  - 说明：上面的命令 直接进入vi的命令模式。
  - 使用：从命令模式进入编辑模式，需要按i键或者a键：1) i插入文本；2) a追加文本。使用ESC键可以从编辑模式进入命令模式。
- vi命令模式
- 命令模式
  - :W  保存文件;
  - :wq  保存并退出;
  - :wq!   保存并强制退出;
  - :q  退出;
  - :q!  强制退出;
  - dd  删除行文字;（退出编辑模式后才能进行适用）
  - x 删除一个字符;（退出编辑模式后才能进行适用）
  - :n  光标移至文本第n行;（退出编辑模式后才能进行适用）
  - $  光标移至文本的行尾;（退出编辑模式后才能进行适用）
  -  G  光标移至文本的末尾行的首字母（root用户）/光标移至文本的末尾行最后一个字母（root用户）（退出编辑模式后才能进行适用）
  -  /  查找某个字符串在文档中**[第一次]()**出现的位置。/sdb（退出编辑模式后才能进行适用）



2. Linux管理文件和目录的命令

- pwd
  - 功能描述:打印用户当前所处的路径。(print work directory)
  - 在文本模式下，使用命令:[root@localhost ~]#pwd 
- cd
  - 功能描述:改变用户所在目录。(change directory)
  - 格式: cd <目录名>
  - [root@localhost ~]#cd ..    返回到当前目录的上一级目录
  - [root@localhost ~]#cd       返回当前用户的主目录（如果是root用户登录，则返回root目录）
  - [root@localhost ~]#cd /home    用路径切换到home目录
- Is命令
  - 功能描述:显示指定目录下的内容。( list directory )
  - 格式: Is [参数] [目录或文件] 
  - 选项           含义
  - -a               列举目录中的全部文件，包括隐藏文件
  - -|               列举目录中的细节，包括权限、所有者、组群、大小、创建日期、文件是否是链接等
  - -r               逆向，从后向前地列举目录中内容（先显示目录再显示文件）
  - -R              递归，该选项递归地列举当前目录下所有子目录内的内容![image-20210314103051922](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210314103051922.png)
  - -s               文件大小size (以数据块的形式的做表示）![image-20210314103457237](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210314103457237.png)
  - Is -| 1.txt   列举文件1.txt的所有信息	
- cat命令
  - 功能描述：显示文本内容
  - 语法：cat文本文件名字
  - 例如:在屏幕上显示整个文件的内容: cat 1.txt 
- touch命令
  - 功能描述：创建文本但不能进行编辑(不能插入内容) 
  - 语法: touch 文本文件名字1，文本文件名字2，......
  - 例如: touch 12.txt
- grep命令
  - 功能：是在一堆文件中查找一 个特定的字符串。
  - 语法：grep 查找的字段  查找的文件
  - 注意：以上命令在test.xt中查找money这个字符串，grep查找是区分大小写的。
- cp命令
  - 功能描述:拷贝文件或复制文件。(copy) 
  - 格式: cp [源文件] [目标文件]
  - 选项         含义
  - -i               互动：如果文件将覆盖目标中的文件,他会提示确认
    -r               递归：这个选项会复制整个目录、子目录以及其他
    -v               详细：显示文件的复制进度
  - [root@localhost ~]#ls
  - [root@localhost ~]#cp hello.txt file1.txt 把文件hello拷贝份，命名为file1
- mv命令
  - 功能描述:可以对文件或者目录进行移动.
  - 格式: mv [源对象] [目的对象]
  - 选项     说明
    -i          互动：如果选择的文件会覆盖目标中的文件，他会提示确认
    -f          强制：不提示地移动文件
    -v         详细：显示文件的移动进度
- mkdir
  - 功能描述:创建目录。( make directory )
  - 格式: mkdir [目录名1] [目录名2]
    [root@localhost ~]#mkdir dir2创建一个目录dir2
    [root@localhost ~]#ls借助ls命令 查看dir 2是否创建成功
    [root@localhost ~]#mkdir bb CC dd  一次性创建多个目录
  - mkdir **-p** aa/bb 目录里面只能嵌套一 个目录（实现嵌套目录的方法）
- rmdir
  - 功能描述:删除空目录。( remove directory )
  - 格式: rmdir [参数] [目录名1] [目录名2] ....
  - [root@localhost ~]#rmdir dir2删除一 个空目录
  - [root@localhost ~]#rmdir bb CC dd删除多个空目录
  - 注意事项：1、不能删除非空目录。2、不能删除当前目录
  - -p   删除指定目录，如果这个指定目录被删除后，他所在的父目录为空，也会一并删除
- rm命令
  - 功能描述:删除文件。remove
  - 格式: rm [参数] [文件]
  - 选项          说明
    -i                互动:提示确认删除
    -f                强制:代替互动模式,不提示确认删除
    -v               详细:显示文件的删除进度
    -r                递归:将删除某个目录以及其中所有的文件和子目录



3. 线上查询的命令

- man命令（Ctrl + Z）
  - 功能:用来查询和解释一个命令 的使用方法和这个命令的注意事项.
  - 格式:man命令的名称
  - 要查询ls命令的说明书页,输入命令: man ls 退出按下q
- locate命令
  - 功能:定位文件和目录.
  - 格式:locate文件或者目录名字
  - 想要搜索带有test的这个词的文件,输入命令: locate test
  - ocate命令使用数据库来定位带有test这个词的文件或目录。
- whatis命令
  - 功能:用来查询某个命令的含义。
  - 要查询mv命令的含义,输入命令：whatis mv 

4. 文件备份和压缩命令

- bzip2命令
  - 功能:bzip2来压缩文件（仅压缩文件），压缩后的文件后缀名字为bzip2。
  - 格式:bzip2 filename 
  - 文件即会被压缩,并被保存为filename.bz2。
  - 要解压缩文件,输入命令：bunzip2 filename.bz2
  - filename.bz2会被删除,而以filename代替。
  - bzip2 file1 file2 file3 /home/aa：上面的命令把file1、file2、 file3以及 /home/aa目录中的内容压缩起来。
  
- gzip命令（仅针对文件进行压缩/解压）

  - 要使用gzip来压缩文件，输入命令：gzip filename
  - 文件即会被压缩,并被保存为filename.gz。
  - 要解压缩文件,输入命令：gunzip filename.gz
  - filename.gz会被删除,而以filename代替。
  - 参数      定义
  - -r :         递归处理，将指定目录下的所有文件及子目录一并处理;
  - gzip -r file1  上面的命令把file1目录中的内容压缩起来。

- tar命令

  - 功能描述:将文件或者目录进行打包、或者解压缩。
  - 格式: tar [参数] [打包后的文件名] [需要打包的文件或目录]。
  - 其中参数包含以下几个:
  - -c：创建压缩文件;
  - -x：展开归档文件;
  - -t：显示包括在tar文件中的文件列表（在不进行解压的情况下查看压缩包里包含什么内容）
  - -z：压缩/解压缩文件 (gz格式) ;（加上对于文件夹的压缩）
  - -v：写入或读取时,显示所有的文件;（在压缩或者解压缩的时候会显示你对哪些文件进行了压缩和解压缩）
  - -f：指名要展开的归档文件名;（给要压缩的文件起名字）
  - -j：压缩或解压缩文件 ( bz2格式)。
  - [root@localhost ~]#tar cvf（压缩参数组合） test.tar /home/test将home 下目录test打包成tar包![image-20210316110628335](Linux.assets/image-20210316110628335.png)
  - [root@localhost ~]#tar xvf （解压缩参数组合）test.tar 将test.tar解压缩![image-20210316110809769](Linux.assets/image-20210316110809769.png)

  - ps：经压缩后的文件仍旧存在
  - tar cvf file.tar a b c：将a,b,c三个文件夹一起压缩到file.tar
  - ![image-20210316111324705](Linux.assets/image-20210316111324705.png)
  - 要创建一个tar文件 ,输入命令：tar -cvf filename.tar aa bb
  - 上面的命令将aa、bb放入文件中。
  - 要列出tar文件的内容，输入命令：tar - tvf filename.tar![image-20210316111243689](Linux.assets/image-20210316111243689.png)
  - 要抽取tar文件的命令,输入命令：tar -xvf filename.tar
  - 这个命令不会删除tar文件,但会把解除归档的内容复制到当前工作目录下,并保留归档文件所使用的任何目录结构。
  - 对文件进行压缩的操作
    参数1: cjvf         后缀名:xxx. tbz
    参数2: czvf        后缀名:xxx. tgz
  - 对文件进行解压缩的操作
    参数1: xjvf
    参数2: xzvf
  - 要创建一个使用tar和bzip2来归档压缩的文件,使用j选项：tar -cjvf filename.**tbz** file
  - 要扩展并解除归档bzip tar文件，输入命令：tar -xjvf filename.tbz
  - 要创建一个用tar和gzip归档并压缩的文件，使用-z选项：tar czvf filename.**tgz** file
  - 要扩展并解除归档gzip tar文件，输入命令：tar -xzvf filename.tgz

5. 文件阅读命令

- head命令
  - 功能描述：head命令可以用来查看文件的开头部分。
  - 此命令的格式是：head 文件名
  - 默认设置，它只查看文件的**前10行**。但可以通过指定一个数字
  - 选项来改变要显示的行数，命令如下：head   -20  文件名；这个命令将会查看文件的前20行。
- tail命令
  - 功能：查看文件结尾的10行（默认）。
  - 格式：tail -行数 文件名
  - 这有助于查看日志文件的最后10行来阅读重要的系统信息。
- more命令
  - 功能：按页来查看文件的内容more使用空格键和b键来前后移动。
  - 语法：more [选项] [fileNames]
  - eg：more 1.txt
  - 选项            含义
    -num           一次显示的行数
    -f                  计算行数时,以实际上的行数,而非自动换行过后的行数(有些单行字数太长的会被扩展为两行或两行以上)
    +num           从第num行开始显示![image-20210316124825388](Linux.assets/image-20210316124825388.png)



