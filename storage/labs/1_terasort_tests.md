* Create an end-user Linux account named with your GitHub handle
```
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ sudo useradd robgajudo
```
* Create a home HDFS directory for this user as well
```
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ sudo -u hdfs hadoop fs -mkdir /user/robgajudo
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ sudo -u hdfs hadoop fs -ls /user
Found 6 items
drwx------   - hdfs   supergroup          0 2016-12-05 22:59 /user/hdfs
drwxrwxrwx   - mapred hadoop              0 2016-12-05 06:17 /user/history
drwxrwxr-t   - hive   hive                0 2016-12-05 06:18 /user/hive
drwxrwxr-x   - hue    hue                 0 2016-12-05 06:19 /user/hue
drwxrwxr-x   - oozie  oozie               0 2016-12-05 06:19 /user/oozie
drwxr-xr-x   - hdfs   supergroup          0 2016-12-05 23:11 /user/robgajudo
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ sudo -u hdfs hadoop fs -chown robgajudo /user/robgajudo
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ sudo -u hdfs hadoop fs -ls /user
Found 6 items
drwx------   - hdfs      supergroup          0 2016-12-05 22:59 /user/hdfs
drwxrwxrwx   - mapred    hadoop              0 2016-12-05 06:17 /user/history
drwxrwxr-t   - hive      hive                0 2016-12-05 06:18 /user/hive
drwxrwxr-x   - hue       hue                 0 2016-12-05 06:19 /user/hue
drwxrwxr-x   - oozie     oozie               0 2016-12-05 06:19 /user/oozie
drwxr-xr-x   - robgajudo supergroup          0 2016-12-05 23:11 /user/robgajudo
```
Run the following exercises as this user

* Create a 10 GB file using teragen
* Set the number of mappers to four
* Limit the block size to 32 MB
* Land the result under your user's home directory
* Use the time command to report the job's duration
```
[robgajudo@ip-172-31-3-11 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -D mapred.map.tasks=4 -D dfs.blocksize=32m 100000000 /user/robgajudo/terasort-test
16/12/05 23:45:17 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-3-11.ap-southeast-1.compute.internal/172.31.3.11:8032
16/12/05 23:45:18 INFO terasort.TeraSort: Generating 100000000 using 4
16/12/05 23:45:18 INFO mapreduce.JobSubmitter: number of splits:4
16/12/05 23:45:18 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
16/12/05 23:45:18 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1480987579239_0007
16/12/05 23:45:19 INFO impl.YarnClientImpl: Submitted application application_1480987579239_0007
16/12/05 23:45:19 INFO mapreduce.Job: The url to track the job: http://ip-172-31-3-11.ap-southeast-1.compute.internal:8088/proxy/application_1480987579239_0007/
16/12/05 23:45:19 INFO mapreduce.Job: Running job: job_1480987579239_0007
16/12/05 23:45:25 INFO mapreduce.Job: Job job_1480987579239_0007 running in uber mode : false
16/12/05 23:45:25 INFO mapreduce.Job:  map 0% reduce 0%
16/12/05 23:45:36 INFO mapreduce.Job:  map 13% reduce 0%
16/12/05 23:45:39 INFO mapreduce.Job:  map 19% reduce 0%
16/12/05 23:45:42 INFO mapreduce.Job:  map 21% reduce 0%
16/12/05 23:45:45 INFO mapreduce.Job:  map 24% reduce 0%
16/12/05 23:45:48 INFO mapreduce.Job:  map 27% reduce 0%
16/12/05 23:45:51 INFO mapreduce.Job:  map 29% reduce 0%
16/12/05 23:45:54 INFO mapreduce.Job:  map 32% reduce 0%
16/12/05 23:45:57 INFO mapreduce.Job:  map 35% reduce 0%
16/12/05 23:46:00 INFO mapreduce.Job:  map 37% reduce 0%
16/12/05 23:46:03 INFO mapreduce.Job:  map 40% reduce 0%
16/12/05 23:46:06 INFO mapreduce.Job:  map 43% reduce 0%
16/12/05 23:46:09 INFO mapreduce.Job:  map 46% reduce 0%
16/12/05 23:46:12 INFO mapreduce.Job:  map 48% reduce 0%
16/12/05 23:46:15 INFO mapreduce.Job:  map 51% reduce 0%
16/12/05 23:46:18 INFO mapreduce.Job:  map 52% reduce 0%
16/12/05 23:46:19 INFO mapreduce.Job:  map 53% reduce 0%
16/12/05 23:46:21 INFO mapreduce.Job:  map 55% reduce 0%
16/12/05 23:46:22 INFO mapreduce.Job:  map 57% reduce 0%
16/12/05 23:46:24 INFO mapreduce.Job:  map 58% reduce 0%
16/12/05 23:46:25 INFO mapreduce.Job:  map 61% reduce 0%
16/12/05 23:46:28 INFO mapreduce.Job:  map 64% reduce 0%
16/12/05 23:46:31 INFO mapreduce.Job:  map 66% reduce 0%
16/12/05 23:46:33 INFO mapreduce.Job:  map 67% reduce 0%
16/12/05 23:46:34 INFO mapreduce.Job:  map 69% reduce 0%
16/12/05 23:46:36 INFO mapreduce.Job:  map 71% reduce 0%
16/12/05 23:46:38 INFO mapreduce.Job:  map 72% reduce 0%
16/12/05 23:46:40 INFO mapreduce.Job:  map 75% reduce 0%
16/12/05 23:46:43 INFO mapreduce.Job:  map 78% reduce 0%
16/12/05 23:46:46 INFO mapreduce.Job:  map 80% reduce 0%
16/12/05 23:46:49 INFO mapreduce.Job:  map 82% reduce 0%
16/12/05 23:46:52 INFO mapreduce.Job:  map 84% reduce 0%
16/12/05 23:46:55 INFO mapreduce.Job:  map 87% reduce 0%
16/12/05 23:46:58 INFO mapreduce.Job:  map 90% reduce 0%
16/12/05 23:47:01 INFO mapreduce.Job:  map 93% reduce 0%
16/12/05 23:47:04 INFO mapreduce.Job:  map 95% reduce 0%
16/12/05 23:47:07 INFO mapreduce.Job:  map 98% reduce 0%
16/12/05 23:47:09 INFO mapreduce.Job:  map 99% reduce 0%
16/12/05 23:47:10 INFO mapreduce.Job:  map 100% reduce 0%
16/12/05 23:47:10 INFO mapreduce.Job: Job job_1480987579239_0007 completed successfully
16/12/05 23:47:10 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=488716
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=407553
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=407553
                Total vcore-seconds taken by all map tasks=407553
                Total megabyte-seconds taken by all map tasks=417334272
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1835
                CPU time spent (ms)=157390
                Physical memory (bytes) snapshot=875745280
                Virtual memory (bytes) snapshot=6259605504
                Total committed heap usage (bytes)=890765312
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=214760662691937609
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10000000000

real    1m55.447s
user    0m6.050s
sys     0m0.658s
```
Run the terasort command on this file
Use the time command to report the job's duration
Land the result under your user's home directory
Report your work in storage/labs/1_terasort_tests.md, including:
The full teragen and terasort commands you used
The time result of each job
