# MySQL-零基础学习笔记

opensuse下直接Yast搜索就可以啦！
ubuntu下 sudo apt-get install mysql-server

注：“~>"是终端中，”mysql>”是在mysql中.在mysql中命令以";"结尾！！！

# 新建数据库abc
mysql> CREATE DATABASE abc;

# 通过系统服务命令检查MySQL服务器状态
~>service mysql status

# 通过启动命令检查MySQL服务器状态
~>sudo /etc/init.d/mysql status

# 检查MySQL服务器系统进程
~>ps -aux|grep mysql

# 检查MySQL服务器占用端口
~>netstat -nlt|grep 3306

#使用用户名密码登陆
~>mysql -u root -p

# 查看所有的数据库
mysql> show databases;

# 切换到所需要的库
mysql> use 所需要库名称

# 查看当前所在库中所有的表
mysql> show tables;

# 查看数据库的字符集编码
mysql> show variables like '%char%';

# 在数据库abc中，新建一张表a1
mysql> create table a1(id int primary key,name varchar(32) not null);

# 新建book用户，密码为book，允许book可以远程访问abc数据库，授权book对abc进行所有数据库
mysql> GRANT ALL ON abc.* to book@'%' IDENTIFIED BY 'book';

#允许book可以本地访问abc数据库，授权book对abc进行所有数据库
mysql> GRANT ALL ON abc.* to book@localhost IDENTIFIED BY 'book';

# 重启MySQL服务器
~>/etc/init.d/mysql start

# 停止MySQL服务器
~>/etc/init.d/mysql stop

# 挂载硬盘
~>mount -t ext4 /dev/vdb1 /vdb1

# 建立新存储目录
~>mkdir /vdb1/data

# 移动MySQL数据目录到新目录
~>mv /var/lib/mysql /vdb1/data/

# 软连接
~>ln -s /vdb1/data/mysql /var/lib/mysql

#查询版本号，当前时间
mysql>SELECT VERSION(),CURRENT_DATE();

#查询用户列表
mysql>select user();

未完待续。。。。。。
