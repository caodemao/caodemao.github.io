# Mysql 命令
1.登录  
`mysql -u xxx -p -h localhost;`  
2.显示所有数据库  
`show databases;`  
3.进入某个数据库  
`use xxx;`  
4.显示数据表  
`show tables;`  
5.查看表结构xxx为表名  
`describe xxx;`  
6.导入外部sql文件  
`source 文件地址`  
7.创建数据库  
`create database <数据库名> character set utf8;`  
8.查看数据库编码  
`show variables like 'character_set_database';`  
9.查看mysql的运行时长  
`show global status like 'uptime';`  
10.mysql连接超时  
`show global variables like '%timeout';`  
11.mysql请求链接进程被主动kill  
`show global status like 'com_kill';`  
13.查看最大允许  
`show global variables like 'max_allowed_packet';`  
14.设置最大允许  
`set global max_allowed_packet=1024*1024*16;`  
15.导出整个数据库  
`dump -u 用户名 -p 数据库名 > 导出的文件名;`  
16.导出一个数据库结构  
`dump -u dbuser -p -d --add-drop-table dbname >d:/dbname_db.sql;`  
17.导出一个表  
`dump -u username -p 数据库名 表名> 导出的文件名;`  
18.导入数据库  
`mysql -u username -p passwrod xxx < xxx.sql`  
19.创建用户  
`create user 'clubmember'@'localhost' identified by 'ClubMember*77';`  
20.给用户权限  
`grant all on clubmembernew.* TO 'clubmember'@'localhost';  `  
21.查看用户权限  
`show grants for 'clubmember'@'localhost';  `