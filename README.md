# mysql
一些mysql常用的操作

#创建用户

#登录
mysql -uroot -p

#输入密码
***

#在root用户下操作
create user'name'@'localhost'identified by'密码';
flush privileges;

#创建数据库
create database name;
flush privileges;

#修改用户权限（在创建的数据库中的权限）‘%’通配符可以设置所有的数据库
grant all privileges on databasename.*to user@localhost identified by '密码';
flush privileges;

#在这个数据库下拥有所有权限（可以单独设置权限）
grant select,insert,update,delete on databasename.* to user@localhost identified by “密码″;
flush privileges;

#修改密码 ,在root用户下，可以修改root密码
update mysql.user set password=password(’密码′) where User=’username′ and Host=’localhost’;
flush privileges;

#删除用户
delete from user where user=’username′ and host=’localhost’;
flush privileges;

#删除数据库
drop database name
flush privileges；

#删除用户及权限
drop user 用户名@'%'
drop user 用户名@‘localhost’



查看MYSQL数据库中所有用户及拥有权限

查看MYSQL数据库中所有用户
 SELECT DISTINCT CONCAT('User: ''',user,'''@''',host,''';') AS query FROM mysql.user;
查看数据库中具体某个用户的权限
mysql> show grants for 'cactiuser'@'%';   






