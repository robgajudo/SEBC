```
[root@ip-172-31-3-11 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.compute.internal@SOLVENTO.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.compute.internal@SOLVENTO.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.compute.internal@SOLVENTO.COM: test
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.compute.internal@SOLVENTO.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20161207223030_620280e9-73bc-45e4-a5ff-3538d9540c90): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161207223030_620280e9-73bc-45e4-a5ff-3538d9540c90); Time taken: 0.637 seconds
INFO  : Executing command(queryId=hive_20161207223030_620280e9-73bc-45e4-a5ff-3538d9540c90): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207223030_620280e9-73bc-45e4-a5ff-3538d9540c90); Time taken: 0.081 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (2.173 seconds)
```
