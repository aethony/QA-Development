# LAMP实验环境搭建文档

1. ##### 实验背景

   - LAMP指Linux+ Apache + Mysgl/MariaDB+ Perl/PHP/Python是一組常用来**搭建动态网站**或者服务器的开源软件，本身都是各自独立的程序，但是因为常被放在- -起使用，拥有了越来越高的兼容度，**共同组成了-个强大的Web应用程序平台**。目前很多流行的商业应用都是采职这个架构，LAMP具有Web资源丰富轻量快速开发等特点oL AMP具有通用跨平台高性能低价格的优势，因此LAMP无论是性能质量还是价格都是**企业搭建网站的首选平台**。

2. ##### 实验目的

   - 通过文档能够自己搭建LAMP环境，并在环境中部署论坛网站。

3. ##### 实验要求

   - 分别安装搭建lamp服务环境;
   - 采用lamp一键安装包搭建环境;
   - 在lamp环境中初步搭建起-一个网站;

4. ##### 实验环境

   - VMware虛拟机10.0
   - 操作系统采用CentQS 6.5 x64 ;
   - 安装Apache ;
   - MySQL数据库;
   - 安装PHP。

5. ##### 实验分析与设计思路

   LAMP架构原理:客户端发送http request请求，服务器( Apache )接受web请求; Apache[判断客户端请求的资源是否为静态请求。若是静态请求，则Apache直接将客户端请求的静态资源( .html, .htm .shtml 等文件)， 通过Http response的形式传送给客户端;若为phe动态请求，则通过CGI协议将客户端的php请求传输给PHP程序，然后由php程序调用php解析器执行phg请求。PHP在执行phe请求时判断是否会依赖mysg!数据库。若不依赖mysg!数据库，则由phe解析器直接执行php相关脚本，将解析后的脚本再次通过CGI协议返传送给Apache.服务器，再执行“静态请求”的流程;若依赖mysgl数据库，则phe程序通过php-mysg!驱动与mysg!进行关联， 获职相关数据， 然后将其返还给php解释器，再次执行“不依赖mysg!数据库”的流程。

6. ##### 搭建步骤与过程;

   - 安装:
   
   - 1、安装Apache
   
   - 卸载自带httpd: yum remove httpd
   
   - yum install httpd #根据提示， 输入Y安装即可成功安装
   
   - /etc/init. d/httpd start #启动Apache
   
   - 备注: Apache启动之后会提示错误:
   
   - 正在启动httpd:httpd: Could not reliably determine the server's fully gualif domain name, using ::1 for ServerName
   
   - 解决办法:
   
   - vi /etc/httpd/conf/httpd. conf #编辑
   
   - 找到#ServerName www.example .com:80
     修改为ServerName www.Joca lhost.com:80 #这里设置为你自己的域名， 如果没有域名，可以设置为localhost
     
   - :wg! #保存退出
   
   - chkconfig httpd on #设为开机启动
   
   - /etc/init. d/httpd restart #重启Apache
   
   - 2、安装MySQL
   
   - 先卸载自带mysg!: yum remove mysq! mysal-server mysql:libs compat-mysq151
   
   - rm rf /var/lib/mysql
   
   - rm /etc/my.cnf
   
   - 安装:
   
   - yum install mysq! mysql-server #询问是否要安装，输入Y即可自动安装,直到安装完成
   
   - /etc/init. d/mysqld start #启动MySQL
   
   - chkconfig mysgld on #设为开机启动
   
   - cp /usr/s hare/mysql/my-medium.cnf /etc/my.cnf #拷贝配置文件(注意:如果/etc目录下面默认有一个my.cnf，直接覆盖即可) 
   
   - 为root账户设置密码：mysql_ secure_ installation
   
   - 回车，根据提示输入Y(注意:如果没有提示输入Y，回车就行)
   
   - 输入2次密码，回车；根据提示一路输入Y；最后出现: Thanks for using MySQL!
     MySql密码设置完成，重新启动MySQL :
     /etc/init. d/mysgld restart #重启
     
     /etc/init. d/mysqld stop #停止
     /etc/init. d/mysqld start #启动
     
   - 3.安装PHP5
   
   - yum install php
   
   - 根据提示输入Y直到安装完成
   
   - 安装PHP组件，使PHP5支持MySQL
     yum install php-mysq! php-gd libipeg* php-imap php-ldap php-odbc php-pear php-xml php-xmlrpc php-mbstring php-mcrypt php-bcmath php-mhash Jlbmcrypt
     这里选择以上安装包进行安装根据提示输入Y回车
   
   - /etc/init. d/mys qld restarty#重启MySg!
   
   - /etc/init. d/httpd restart #重启Apche
   
   - 测试:
   
   - cd /var/www/htm!
   
   - vi Index.phe #输入下面内容
   
   - <?php
   
   - phpinfo();
   
   - ?>
   
   - :wg! #保存退出
   
   - 在客户端浏览器输入服务器IP地址，可以看到相关的配置信息，具体配置信息如下图所示：![image-20210504104911999](LAMP%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA%E5%AE%9E%E9%AA%8C%E6%96%87%E6%A1%A3.assets/image-20210504104911999.png)
   
   - 
   
   ##### 7.实验结果及分析
   
   - 在lamp环墙中初步搭建起一个网站
   - 解压后，将sys[tem文件夹移到www文件夹中，然后将www目录复制，到/var/www/html中
   - 打开浏览器，输入: http://127.0.0.1:8/wwwinstall.php
   - 然后进入到欢迎页面，点击下一步就行;
   - 继续进入到数据库配置页面