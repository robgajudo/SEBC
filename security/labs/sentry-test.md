* Verify sentry privleges
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
* Create a Sentry role with full authorization
```
[root@ip-172-31-3-11 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.co                                                                                   mpute.internal@SOLVENTO.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.comput                                                                                   e.internal@SOLVENTO.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.c                                                                                   ompute.internal@SOLVENTO.COM: test
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.c                                                                                   ompute.internal@SOLVENTO.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show roles;
INFO  : Compiling command(queryId=hive_20161207230101_ade09a01-6598-48c3-8a44-b1a84aea1797): show role                                                                                   s
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:role, type:string, comment:from d                                                                                   eserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230101_ade09a01-6598-48c3-8a44-b1a84aea1797);                                                                                    Time taken: 0.795 seconds
INFO  : Executing command(queryId=hive_20161207230101_ade09a01-6598-48c3-8a44-b1a84aea1797): show role                                                                                   s
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230101_ade09a01-6598-48c3-8a44-b1a84aea1797);                                                                                    Time taken: 0.541 seconds
INFO  : OK
+-------+--+
| role  |
+-------+--+
+-------+--+
No rows selected (2.754 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20161207230101_24f64012-bece-42db-84eb-0e8e4ee662d7): CREATE RO                                                                                   LE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230101_24f64012-bece-42db-84eb-0e8e4ee662d7);                                                                                    Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20161207230101_24f64012-bece-42db-84eb-0e8e4ee662d7): CREATE RO                                                                                   LE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230101_24f64012-bece-42db-84eb-0e8e4ee662d7);                                                                                    Time taken: 0.311 seconds
INFO  : OK
No rows affected (0.389 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20161207230202_d1285b65-6950-4161-9e18-4cc0ef71ceff): GRANT ALL                                                                                    ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230202_d1285b65-6950-4161-9e18-4cc0ef71ceff);                                                                                    Time taken: 0.093 seconds
INFO  : Executing command(queryId=hive_20161207230202_d1285b65-6950-4161-9e18-4cc0ef71ceff): GRANT ALL                                                                                    ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230202_d1285b65-6950-4161-9e18-4cc0ef71ceff);                                                                                    Time taken: 0.11 seconds
INFO  : OK
No rows affected (0.211 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP test;
INFO  : Compiling command(queryId=hive_20161207230202_053882b8-c9af-41fe-83f5-2db7740571cb): GRANT ROL                                                                                   E sentry_admin TO GROUP test
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230202_053882b8-c9af-41fe-83f5-2db7740571cb);                                                                                    Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20161207230202_053882b8-c9af-41fe-83f5-2db7740571cb): GRANT ROL                                                                                   E sentry_admin TO GROUP test
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230202_053882b8-c9af-41fe-83f5-2db7740571cb);                                                                                    Time taken: 0.103 seconds
INFO  : OK
No rows affected (0.177 seconds)
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20161207230202_469b193c-3960-47e2-a75f-b5215da43e1f): SHOW TABL                                                                                   ES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:fr                                                                                   om deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230202_469b193c-3960-47e2-a75f-b5215da43e1f);                                                                                    Time taken: 0.103 seconds
INFO  : Executing command(queryId=hive_20161207230202_469b193c-3960-47e2-a75f-b5215da43e1f): SHOW TABL                                                                                   ES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230202_469b193c-3960-47e2-a75f-b5215da43e1f);                                                                                    Time taken: 0.232 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.348 seconds)
```
* Create additional test users
```
[root@ip-172-31-3-11 ~]# sudo groupadd selector
[root@ip-172-31-3-11 ~]# useradd -u 1100 -g selector george
[root@ip-172-31-3-11 ~]# useradd -u 1200 -g inserters ferdinand
useradd: group 'inserters' does not exist
[root@ip-172-31-3-11 ~]# groupadd inserters
[root@ip-172-31-3-11 ~]# useradd -u 1200 -g inserters ferdinand
```
```
[root@ip-172-31-3-11 ~]# kadmin.local
kadmin.local:  add_principal george
WARNING: no policy specified for george@SOLVENTO.COM; defaulting to no policy
Enter password for principal "george@SOLVENTO.COM":
Re-enter password for principal "george@SOLVENTO.COM":
Principal "george@SOLVENTO.COM" created.
kadmin.local:  add_principal ferdinand
WARNING: no policy specified for ferdinand@SOLVENTO.COM; defaulting to no policy
Enter password for principal "ferdinand@SOLVENTO.COM":
Re-enter password for principal "ferdinand@SOLVENTO.COM":
Principal "ferdinand@SOLVENTO.COM" created.
kadmin.local:  exit
```
* Create test roles
```
[root@ip-172-31-3-11 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.co                                                                                   mpute.internal@SOLVENTO.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.comput                                                                                   e.internal@SOLVENTO.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.c                                                                                   ompute.internal@SOLVENTO.COM: test
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.c                                                                                   ompute.internal@SOLVENTO.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> create role reads;
INFO  : Compiling command(queryId=hive_20161207230505_7f2286e3-e5b5-4f30-8944-b851787a270f): create ro                                                                                   le reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230505_7f2286e3-e5b5-4f30-8944-b851787a270f);                                                                                    Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20161207230505_7f2286e3-e5b5-4f30-8944-b851787a270f): create ro                                                                                   le reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230505_7f2286e3-e5b5-4f30-8944-b851787a270f);                                                                                    Time taken: 0.033 seconds
INFO  : OK
No rows affected (0.159 seconds)
0: jdbc:hive2://localhost:10000/default> create role writes;
INFO  : Compiling command(queryId=hive_20161207230505_51a24676-9d41-4400-920d-ae5dc1fd2e83): create ro                                                                                   le writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230505_51a24676-9d41-4400-920d-ae5dc1fd2e83);                                                                                    Time taken: 0.061 seconds
INFO  : Executing command(queryId=hive_20161207230505_51a24676-9d41-4400-920d-ae5dc1fd2e83): create ro                                                                                   le writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230505_51a24676-9d41-4400-920d-ae5dc1fd2e83);                                                                                    Time taken: 0.034 seconds
INFO  : OK
No rows affected (0.107 seconds)
```
* Grant read privilege for all tables to reads
```
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20161207230505_ae0ddba6-efc0-4b12-a708-4b76e0441ee7): GRANT SEL                                                                                   ECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230505_ae0ddba6-efc0-4b12-a708-4b76e0441ee7);                                                                                    Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20161207230505_ae0ddba6-efc0-4b12-a708-4b76e0441ee7): GRANT SEL                                                                                   ECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230505_ae0ddba6-efc0-4b12-a708-4b76e0441ee7);                                                                                    Time taken: 0.057 seconds
INFO  : OK
No rows affected (0.122 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20161207230505_0315deda-74b9-4584-b55a-41912a8dd563): GRANT ROL                                                                                   E reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230505_0315deda-74b9-4584-b55a-41912a8dd563);                                                                                    Time taken: 0.075 seconds
INFO  : Executing command(queryId=hive_20161207230505_0315deda-74b9-4584-b55a-41912a8dd563): GRANT ROL                                                                                   E reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230505_0315deda-74b9-4584-b55a-41912a8dd563);                                                                                    Time taken: 0.041 seconds
INFO  : OK
No rows affected (0.127 seconds)
```
* Grant read privilege for default.sample07 only to 'writes':
```
0: jdbc:hive2://localhost:10000/default> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20161207230505_b60fa3c2-7c0c-4c45-ade2-538e5ddb0c33): REVOKE AL                                                                                   L ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230505_b60fa3c2-7c0c-4c45-ade2-538e5ddb0c33);                                                                                    Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20161207230505_b60fa3c2-7c0c-4c45-ade2-538e5ddb0c33): REVOKE AL                                                                                   L ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230505_b60fa3c2-7c0c-4c45-ade2-538e5ddb0c33);                                                                                    Time taken: 0.116 seconds
INFO  : OK
No rows affected (0.185 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20161207230606_c08e55dd-8c39-4e52-ade7-88d801e039a4): GRANT SEL                                                                                   ECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230606_c08e55dd-8c39-4e52-ade7-88d801e039a4);                                                                                    Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20161207230606_c08e55dd-8c39-4e52-ade7-88d801e039a4): GRANT SEL                                                                                   ECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230606_c08e55dd-8c39-4e52-ade7-88d801e039a4);                                                                                    Time taken: 0.044 seconds
INFO  : OK
No rows affected (0.115 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20161207230606_fa5a9ebf-4f89-4260-89d0-f10a859377b5): GRANT ROL                                                                                   E writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230606_fa5a9ebf-4f89-4260-89d0-f10a859377b5);                                                                                    Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20161207230606_fa5a9ebf-4f89-4260-89d0-f10a859377b5): GRANT ROL                                                                                   E writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230606_fa5a9ebf-4f89-4260-89d0-f10a859377b5);                                                                                    Time taken: 0.047 seconds
INFO  : OK
No rows affected (0.112 seconds)
```
* kinit as george, then login to beeline
```
[root@ip-172-31-3-11 ~]# kinit george@SOLVENTO.COM
Password for george@SOLVENTO.COM:
[root@ip-172-31-3-11 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.co                                                                                   mpute.internal@SOLVENTO.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.comput                                                                                   e.internal@SOLVENTO.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.c                                                                                   ompute.internal@SOLVENTO.COM: george
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.c                                                                                   ompute.internal@SOLVENTO.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20161207230606_efc29f7f-7aad-47ef-9962-ca1cb33fa6cf): show tabl                                                                                   es
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:fr                                                                                   om deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230606_efc29f7f-7aad-47ef-9962-ca1cb33fa6cf);                                                                                    Time taken: 0.077 seconds
INFO  : Executing command(queryId=hive_20161207230606_efc29f7f-7aad-47ef-9962-ca1cb33fa6cf): show tabl                                                                                   es
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230606_efc29f7f-7aad-47ef-9962-ca1cb33fa6cf);                                                                                    Time taken: 0.139 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.396 seconds)
0: jdbc:hive2://localhost:10000/default> exit
. . . . . . . . . . . . . . . . . . . .> [root@ip-172-31-3-11 ~]# kinit ferdinand@SOLVENTO.COM
Password for ferdinand@SOLVENTO.COM:
kinit: Password incorrect while getting initial credentials
[root@ip-172-31-3-11 ~]# kinit ferdinand@SOLVENTO.COM
Password for ferdinand@SOLVENTO.COM:
[root@ip-172-31-3-11 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.co                                                                                   mpute.internal@SOLVENTO.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.comput                                                                                   e.internal@SOLVENTO.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.c                                                                                   ompute.internal@SOLVENTO.COM: ferdinand
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-3-11.ap-southeast-1.c                                                                                   ompute.internal@SOLVENTO.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20161207230707_7c59f747-3210-4606-8f09-8b07a28f3acc): show tabl                                                                                   es
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:fr                                                                                   om deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20161207230707_7c59f747-3210-4606-8f09-8b07a28f3acc);                                                                                    Time taken: 0.073 seconds
INFO  : Executing command(queryId=hive_20161207230707_7c59f747-3210-4606-8f09-8b07a28f3acc): show tabl                                                                                   es
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20161207230707_7c59f747-3210-4606-8f09-8b07a28f3acc);                                                                                    Time taken: 0.14 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.345 seconds)
```
