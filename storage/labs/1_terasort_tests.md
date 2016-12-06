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
* Run the terasort command on this file
* Use the time command to report the job's duration
* Land the result under your user's home directory
```
[robgajudo@ip-172-31-3-11 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/robgajudo/terasort-test /user/robgajudo/terasort-testoutput
16/12/06 00:18:58 INFO terasort.TeraSort: starting
16/12/06 00:18:59 INFO input.FileInputFormat: Total input paths to process : 4
Spent 288ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 295ms
Sampling 10 splits of 300
Making 8 from 100000 sampled records
Computing parititions took 1081ms
Spent 1382ms computing partitions.
16/12/06 00:19:01 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-3-11.ap-southeast-1.compute.internal/172.31.3.11:8032
16/12/06 00:19:01 INFO mapreduce.JobSubmitter: number of splits:300
16/12/06 00:19:01 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1480987579239_0008
16/12/06 00:19:02 INFO impl.YarnClientImpl: Submitted application application_1480987579239_0008
16/12/06 00:19:02 INFO mapreduce.Job: The url to track the job: http://ip-172-31-3-11.ap-southeast-1.compute.internal:8088/proxy/application_1480987579239_0008/
16/12/06 00:19:02 INFO mapreduce.Job: Running job: job_1480987579239_0008
16/12/06 00:19:08 INFO mapreduce.Job: Job job_1480987579239_0008 running in uber mode : false
16/12/06 00:19:08 INFO mapreduce.Job:  map 0% reduce 0%
16/12/06 00:19:20 INFO mapreduce.Job:  map 3% reduce 0%
16/12/06 00:19:23 INFO mapreduce.Job:  map 4% reduce 0%
16/12/06 00:19:30 INFO mapreduce.Job:  map 6% reduce 0%
16/12/06 00:19:31 INFO mapreduce.Job:  map 7% reduce 0%
16/12/06 00:19:37 INFO mapreduce.Job:  map 9% reduce 0%
16/12/06 00:19:40 INFO mapreduce.Job:  map 10% reduce 0%
16/12/06 00:19:41 INFO mapreduce.Job:  map 11% reduce 0%
16/12/06 00:19:42 INFO mapreduce.Job:  map 12% reduce 0%
16/12/06 00:19:50 INFO mapreduce.Job:  map 13% reduce 0%
16/12/06 00:19:51 INFO mapreduce.Job:  map 15% reduce 0%
16/12/06 00:19:53 INFO mapreduce.Job:  map 16% reduce 0%
16/12/06 00:19:59 INFO mapreduce.Job:  map 17% reduce 0%
16/12/06 00:20:01 INFO mapreduce.Job:  map 18% reduce 0%
16/12/06 00:20:04 INFO mapreduce.Job:  map 20% reduce 0%
16/12/06 00:20:09 INFO mapreduce.Job:  map 21% reduce 0%
16/12/06 00:20:11 INFO mapreduce.Job:  map 22% reduce 0%
16/12/06 00:20:16 INFO mapreduce.Job:  map 23% reduce 0%
16/12/06 00:20:18 INFO mapreduce.Job:  map 24% reduce 0%
16/12/06 00:20:19 INFO mapreduce.Job:  map 25% reduce 0%
16/12/06 00:20:22 INFO mapreduce.Job:  map 26% reduce 0%
16/12/06 00:20:23 INFO mapreduce.Job:  map 27% reduce 0%
16/12/06 00:20:27 INFO mapreduce.Job:  map 28% reduce 0%
16/12/06 00:20:31 INFO mapreduce.Job:  map 29% reduce 0%
16/12/06 00:20:32 INFO mapreduce.Job:  map 31% reduce 0%
16/12/06 00:20:37 INFO mapreduce.Job:  map 32% reduce 0%
16/12/06 00:20:40 INFO mapreduce.Job:  map 33% reduce 0%
16/12/06 00:20:43 INFO mapreduce.Job:  map 34% reduce 0%
16/12/06 00:20:44 INFO mapreduce.Job:  map 35% reduce 0%
16/12/06 00:20:46 INFO mapreduce.Job:  map 36% reduce 0%
16/12/06 00:20:47 INFO mapreduce.Job:  map 37% reduce 0%
16/12/06 00:20:52 INFO mapreduce.Job:  map 38% reduce 0%
16/12/06 00:20:56 INFO mapreduce.Job:  map 39% reduce 0%
16/12/06 00:20:57 INFO mapreduce.Job:  map 40% reduce 0%
16/12/06 00:20:58 INFO mapreduce.Job:  map 41% reduce 0%
16/12/06 00:21:01 INFO mapreduce.Job:  map 42% reduce 0%
16/12/06 00:21:03 INFO mapreduce.Job:  map 43% reduce 0%
16/12/06 00:21:07 INFO mapreduce.Job:  map 44% reduce 0%
16/12/06 00:21:10 INFO mapreduce.Job:  map 45% reduce 0%
16/12/06 00:21:11 INFO mapreduce.Job:  map 46% reduce 0%
16/12/06 00:21:13 INFO mapreduce.Job:  map 47% reduce 0%
16/12/06 00:21:16 INFO mapreduce.Job:  map 48% reduce 0%
16/12/06 00:21:17 INFO mapreduce.Job:  map 49% reduce 0%
16/12/06 00:21:23 INFO mapreduce.Job:  map 51% reduce 0%
16/12/06 00:21:25 INFO mapreduce.Job:  map 52% reduce 0%
16/12/06 00:21:27 INFO mapreduce.Job:  map 53% reduce 0%
16/12/06 00:21:32 INFO mapreduce.Job:  map 54% reduce 0%
16/12/06 00:21:34 INFO mapreduce.Job:  map 55% reduce 0%
16/12/06 00:21:36 INFO mapreduce.Job:  map 56% reduce 0%
16/12/06 00:21:37 INFO mapreduce.Job:  map 57% reduce 0%
16/12/06 00:21:40 INFO mapreduce.Job:  map 58% reduce 0%
16/12/06 00:21:43 INFO mapreduce.Job:  map 59% reduce 0%
16/12/06 00:21:46 INFO mapreduce.Job:  map 60% reduce 0%
16/12/06 00:21:48 INFO mapreduce.Job:  map 61% reduce 0%
16/12/06 00:21:50 INFO mapreduce.Job:  map 62% reduce 0%
16/12/06 00:21:53 INFO mapreduce.Job:  map 63% reduce 0%
16/12/06 00:21:55 INFO mapreduce.Job:  map 64% reduce 0%
16/12/06 00:21:57 INFO mapreduce.Job:  map 65% reduce 0%
16/12/06 00:22:02 INFO mapreduce.Job:  map 66% reduce 0%
16/12/06 00:22:03 INFO mapreduce.Job:  map 67% reduce 0%
16/12/06 00:22:04 INFO mapreduce.Job:  map 68% reduce 0%
16/12/06 00:22:07 INFO mapreduce.Job:  map 69% reduce 0%
16/12/06 00:22:12 INFO mapreduce.Job:  map 70% reduce 0%
16/12/06 00:22:13 INFO mapreduce.Job:  map 71% reduce 0%
16/12/06 00:22:15 INFO mapreduce.Job:  map 72% reduce 0%
16/12/06 00:22:16 INFO mapreduce.Job:  map 73% reduce 0%
16/12/06 00:22:19 INFO mapreduce.Job:  map 74% reduce 0%
16/12/06 00:22:23 INFO mapreduce.Job:  map 75% reduce 0%
16/12/06 00:22:25 INFO mapreduce.Job:  map 76% reduce 0%
16/12/06 00:22:28 INFO mapreduce.Job:  map 77% reduce 0%
16/12/06 00:22:29 INFO mapreduce.Job:  map 78% reduce 0%
16/12/06 00:22:31 INFO mapreduce.Job:  map 79% reduce 0%
16/12/06 00:22:34 INFO mapreduce.Job:  map 80% reduce 0%
16/12/06 00:22:38 INFO mapreduce.Job:  map 81% reduce 0%
16/12/06 00:22:41 INFO mapreduce.Job:  map 82% reduce 0%
16/12/06 00:22:42 INFO mapreduce.Job:  map 83% reduce 0%
16/12/06 00:22:43 INFO mapreduce.Job:  map 84% reduce 0%
16/12/06 00:22:51 INFO mapreduce.Job:  map 84% reduce 7%
16/12/06 00:22:53 INFO mapreduce.Job:  map 84% reduce 9%
16/12/06 00:22:54 INFO mapreduce.Job:  map 85% reduce 17%
16/12/06 00:22:56 INFO mapreduce.Job:  map 86% reduce 17%
16/12/06 00:22:57 INFO mapreduce.Job:  map 86% reduce 18%
16/12/06 00:22:59 INFO mapreduce.Job:  map 86% reduce 19%
16/12/06 00:23:00 INFO mapreduce.Job:  map 86% reduce 24%
16/12/06 00:23:03 INFO mapreduce.Job:  map 87% reduce 24%
16/12/06 00:23:05 INFO mapreduce.Job:  map 88% reduce 24%
16/12/06 00:23:06 INFO mapreduce.Job:  map 88% reduce 26%
16/12/06 00:23:12 INFO mapreduce.Job:  map 89% reduce 26%
16/12/06 00:23:14 INFO mapreduce.Job:  map 90% reduce 26%
16/12/06 00:23:20 INFO mapreduce.Job:  map 91% reduce 26%
16/12/06 00:23:21 INFO mapreduce.Job:  map 92% reduce 26%
16/12/06 00:23:22 INFO mapreduce.Job:  map 92% reduce 27%
16/12/06 00:23:28 INFO mapreduce.Job:  map 93% reduce 27%
16/12/06 00:23:29 INFO mapreduce.Job:  map 94% reduce 27%
16/12/06 00:23:35 INFO mapreduce.Job:  map 94% reduce 28%
16/12/06 00:23:36 INFO mapreduce.Job:  map 95% reduce 28%
16/12/06 00:23:37 INFO mapreduce.Job:  map 96% reduce 28%
16/12/06 00:23:44 INFO mapreduce.Job:  map 97% reduce 28%
16/12/06 00:23:46 INFO mapreduce.Job:  map 98% reduce 28%
16/12/06 00:23:49 INFO mapreduce.Job:  map 98% reduce 29%
16/12/06 00:23:50 INFO mapreduce.Job:  map 99% reduce 29%
16/12/06 00:23:52 INFO mapreduce.Job:  map 100% reduce 29%
16/12/06 00:23:55 INFO mapreduce.Job:  map 100% reduce 35%
16/12/06 00:23:56 INFO mapreduce.Job:  map 100% reduce 50%
16/12/06 00:23:58 INFO mapreduce.Job:  map 100% reduce 54%
16/12/06 00:23:59 INFO mapreduce.Job:  map 100% reduce 61%
16/12/06 00:24:00 INFO mapreduce.Job:  map 100% reduce 62%
16/12/06 00:24:01 INFO mapreduce.Job:  map 100% reduce 63%
16/12/06 00:24:02 INFO mapreduce.Job:  map 100% reduce 66%
16/12/06 00:24:03 INFO mapreduce.Job:  map 100% reduce 68%
16/12/06 00:24:04 INFO mapreduce.Job:  map 100% reduce 69%
16/12/06 00:24:05 INFO mapreduce.Job:  map 100% reduce 72%
16/12/06 00:24:07 INFO mapreduce.Job:  map 100% reduce 73%
16/12/06 00:24:08 INFO mapreduce.Job:  map 100% reduce 76%
16/12/06 00:24:09 INFO mapreduce.Job:  map 100% reduce 78%
16/12/06 00:24:10 INFO mapreduce.Job:  map 100% reduce 79%
16/12/06 00:24:11 INFO mapreduce.Job:  map 100% reduce 81%
16/12/06 00:24:12 INFO mapreduce.Job:  map 100% reduce 82%
16/12/06 00:24:13 INFO mapreduce.Job:  map 100% reduce 83%
16/12/06 00:24:14 INFO mapreduce.Job:  map 100% reduce 86%
16/12/06 00:24:15 INFO mapreduce.Job:  map 100% reduce 89%
16/12/06 00:24:16 INFO mapreduce.Job:  map 100% reduce 91%
16/12/06 00:24:17 INFO mapreduce.Job:  map 100% reduce 93%
16/12/06 00:24:19 INFO mapreduce.Job:  map 100% reduce 94%
16/12/06 00:24:21 INFO mapreduce.Job:  map 100% reduce 95%
16/12/06 00:24:23 INFO mapreduce.Job:  map 100% reduce 96%
16/12/06 00:24:25 INFO mapreduce.Job:  map 100% reduce 97%
16/12/06 00:24:27 INFO mapreduce.Job:  map 100% reduce 98%
16/12/06 00:24:30 INFO mapreduce.Job:  map 100% reduce 99%
16/12/06 00:24:33 INFO mapreduce.Job:  map 100% reduce 100%
16/12/06 00:24:34 INFO mapreduce.Job: Job job_1480987579239_0008 completed successfully
16/12/06 00:24:34 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=4472920491
                FILE: Number of bytes written=8886250966
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10000049500
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=924
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=300
                Launched reduce tasks=8
                Data-local map tasks=300
                Total time spent by all maps in occupied slots (ms)=2827028
                Total time spent by all reduces in occupied slots (ms)=724267
                Total time spent by all map tasks (ms)=2827028
                Total time spent by all reduce tasks (ms)=724267
                Total vcore-seconds taken by all map tasks=2827028
                Total vcore-seconds taken by all reduce tasks=724267
                Total megabyte-seconds taken by all map tasks=2894876672
                Total megabyte-seconds taken by all reduce tasks=741649408
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Map output bytes=10200000000
                Map output materialized bytes=4375223545
                Input split bytes=49500
                Combine input records=0
                Combine output records=0
                Reduce input groups=100000000
                Reduce shuffle bytes=4375223545
                Reduce input records=100000000
                Reduce output records=100000000
                Spilled Records=200000000
                Shuffled Maps =2400
                Failed Shuffles=0
                Merged Map outputs=2400
                GC time elapsed (ms)=39141
                CPU time spent (ms)=1517470
                Physical memory (bytes) snapshot=147625361408
                Virtual memory (bytes) snapshot=481983275008
                Total committed heap usage (bytes)=174364557312
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10000000000
        File Output Format Counters
                Bytes Written=10000000000
16/12/06 00:24:34 INFO terasort.TeraSort: done

real    5m37.654s
user    0m9.807s
sys     0m1.036s
```
