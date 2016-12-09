Hostname
```
[root@ip-172-31-2-18 mysql-connector-java-5.1.40]# hostname
ip-172-31-2-18
```
MySQL Version
```
[root@ip-172-31-2-18 mysql-connector-java-5.1.40]# mysql --version
mysql  Ver 14.14 Distrib 5.5.53, for Linux (x86_64) using readline 5.1
```
Databases
```
[root@ip-172-31-2-18 mysql-connector-java-5.1.40]# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 12
Server version: 5.5.53 MySQL Community Server (GPL)

Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hue                |
| metastore          |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)

mysql>
```
