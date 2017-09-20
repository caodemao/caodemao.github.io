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
`mysqldump -u dbuser -p -d --add-drop-table dbname >d:/dbname_db.sql;`  
17.导出一个表  
`mysqldump -u username -p 数据库名 表名> 导出的文件名;`  
18.导入数据库  
`mysql -u username -p passwrod xxx < xxx.sql`  
19.创建用户  
`create user 'clubmember'@'localhost' identified by 'ClubMember*77';`  
20.给用户权限  
`grant all on clubmembernew.* TO 'clubmember'@'localhost';  `  
21.查看用户权限  
`show grants for 'clubmember'@'localhost';  `  
22.添加表字段  
`alter table 表名 add column 字段名 字段类型 是否允许为null default 默认值 AFTER 在哪个字段后面;`  
eg:`alter table syw_xinhouse add column zuoxin varchar(10) not Null default '';`   
23.修改表字段  
`alter table 表名 change column 字段名 字段类型 是否允许为null default 默认值;`    
24.修改默认值  
`alter table 表名 alter column 字段名 drop default;` (若本身存在默认值，则先删除)  
`alter table 表名 alter column 字段名 set default 默认值;`(若本身不存在则可以直接设定)  
25.查看数据库支持的字符集及校对  
`show character set;`  
26.查看mysql创建表  
`SHOW CREATE table xxx;`  
27.删除表  
`DROP TABLE  tbl_name;`  
28.删除字段  
`alter table 表名 drop column 字段名;`  
29.删除表中所有记录  
`DELETE FROM 表名`  
`TRUNCATE TABLE 表名`  
30.删除表中某些记录  
`delete from 表名 where ...`  
31.查看MYSQL数据库中所有用户   
`SELECT DISTINCT CONCAT('User: ''',user,'''@''',host,''';') AS query FROM mysql.user;`  

#修改root密码
方法1： 用SET PASSWORD命令  
首先登录MySQL。   
`格式：mysql> set password for 用户名@localhost = password('新密码');`      
例子：mysql> set password for root@localhost = password('123');    

方法2：用mysqladmin  
`格式：mysqladmin -u用户名 -p旧密码 password 新密码  `  
例子：mysqladmin -uroot -p123456 password 123  

方法3：用UPDATE直接编辑user表  
首先登录MySQL。  
`mysql> use mysql;  `  
`mysql> update user set password=password('123') where user='root' and host='localhost'; `    
`mysql> flush privileges;  `  

方法4：在忘记root密码的时候，可以这样  
以windows为例：  
1. 关闭正在运行的MySQL服务。  
2. 打开DOS窗口，转到mysql\bin目录。  
3. 输入mysqld --skip-grant-tables 回车。--skip-grant-tables 的意思是启动MySQL服务的时候跳过权限表认证。  
4. 再开一个DOS窗口（因为刚才那个DOS窗口已经不能动了），转到mysql\bin目录。  
5. 输入mysql回车，如果成功，将出现MySQL提示符 >。  
6. 连接权限数据库： use mysql; 。  
6. 改密码：update user set password=password("123") where user="root";（别忘了最后加分号） 。  
7. 刷新权限（必须步骤）：flush privileges;　。  
8. 退出 quit。  
9. 注销系统，再进入，使用用户名root和刚才设置的新密码123登录。  
