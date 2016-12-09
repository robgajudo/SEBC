```
[root@ip-172-31-15-248 yum.repos.d]# ls /etc/yum.repos.d/
cloudera-manager.repo  mysql-community.repo  redhat-rhui-client-config.repo  redhat-rhui.repo  rhel-source.repo  rhui-load-balancers.conf
```
* Configure Cloudera Manager
```
[root@ip-172-31-15-248 ~]# sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql -h 172.31.2.18 --scm-host ip-172-31-15-248 scm scm welcome1
JAVA_HOME=/usr/lib/jvm/jre-openjdk
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/lib/jvm/jre-openjdk/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
log4j:ERROR Could not find value for key log4j.appender.A
log4j:ERROR Could not instantiate appender named "A".
[2016-12-08 21:53:43,570] INFO     0[main] - com.cloudera.enterprise.dbutil.DbCommandExecutor.testDbConnection(DbCommandExecutor.java) - Successfully connected to database.
All done, your SCM database is configured correctly!
```
