# DB_Fundamental_Knowledge

mysqld.exe：数据库服务端的程序，用来管理数据仓库和数据表

mysql.exe：数据库客户端的程序，用于链接数据库



##### 安装数据库过程：

1. 配置一下操作系统环境变量 ,将mysql数据库bin目录配置到环境变量的path变量; .
2. 在cmd命令行执行mysqld --install mysqI56 指令,将mysql数据库服务端注册成操作系统服务程序
3. 启动mysq|数据库服务端程序net start mysql56
4. 通过数据库客户端连上数据库服务端mysq| -h 127.0.0.1 -u root -p

