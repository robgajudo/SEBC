* Create a precious directory in HDFS; copy the ZIP course file into it.
```
[ec2-user@ip-172-31-3-11 ~]$ sudo -u hdfs hadoop fs -mkdir /precious
```
* Error encountered in putting the file
```
[ec2-user@ip-172-31-3-11 ~]$ sudo -u hdfs hadoop fs -put SEBC-master.zip /precious/
put: `SEBC-master.zip': No such file or directory
```
* Solution
```
[ec2-user@ip-172-31-3-11 tmp]$ sudo chown hdfs:hdfs SEBC-master.zip
[ec2-user@ip-172-31-3-11 tmp]$ sudo su - hdfs
[hdfs@ip-172-31-3-11 tmp]$ hadoop fs -put SEBC-master.zip /precious
[hdfs@ip-172-31-3-11 tmp]$ hadoop fs -ls /
Found 5 items
drwxr-xr-x   - hdfs supergroup          0 2016-12-06 01:02 /precious
drwxr-xr-x   - hdfs supergroup          0 2016-12-05 22:29 /robgajudo
drwxr-xr-x   - hdfs supergroup          0 2016-12-05 22:59 /targetgithub
drwxrwxrwt   - hdfs supergroup          0 2016-12-05 06:18 /tmp
drwxr-xr-x   - hdfs supergroup          0 2016-12-05 23:11 /user
[hdfs@ip-172-31-3-11 tmp]$ hadoop fs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     410040 2016-12-06 01:02 /precious/SEBC-master.zip
```
* Enable snapshots for precious
```
[ec2-user@ip-172-31-3-11 ~]$ sudo -u hdfs hdfs dfsadmin -allowSnapshot /precious
Allowing snaphot on /precious succeeded
```
* Create a snapshot called sebc-hdfs-test
```
[hdfs@ip-172-31-3-11 tmp]$ hdfs dfs -createSnapshot /precious sebc-hdfs-test
Created snapshot /precious/.snapshot/sebc-hdfs-test
```
* Delete the directory
```
[hdfs@ip-172-31-3-11 tmp]$ hadoop fs -rmdir /precious
rmdir: `/precious': Directory is not empty
[hdfs@ip-172-31-3-11 tmp]$ hadoop fs -rm -r /precious
rm: Failed to move to trash: hdfs://ip-172-31-3-11.ap-southeast-1.compute.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
```
* Delete the ZIP file
```
[hdfs@ip-172-31-3-11 tmp]$ hadoop fs -rm -r /precious/SEBC-master.zip
16/12/06 01:25:16 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-3-11.ap-southeast-1.compute.internal:8020/precious/SEBC-master.zip' to trash at: hdfs://ip-172-31-3-11.ap-southeast-1.compute.internal:8020/user/hdfs/.Trash/Current/precious/SEBC-master.zip
```
* Restore the deleted file
```
[hdfs@ip-172-31-3-11 tmp]$ hdfs dfs -cp -ptopax /precious/.snapshot/sebc-hdfs-test /precious
[hdfs@ip-172-31-3-11 tmp]$ hadoop fs -ls /precious
Found 1 items
drwxr-xr-x   - hdfs supergroup          0 2016-12-06 01:17 /precious/sebc-hdfs-test
```
