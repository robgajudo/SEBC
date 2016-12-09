```
[root@ip-172-31-15-248 ~]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/raffles/tgen512m/teragen-out /user/raffles/terasort-testoutput
16/12/08 23:47:55 INFO terasort.TeraSort: starting
16/12/08 23:47:57 INFO hdfs.DFSClient: Created token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@ROBGAJUDO.SG, renewer=yarn, realUser=, issueDate=1481258877445, maxDate=1481863677445, sequenceNumber=2, masterKeyId=4 on 172.31.15.248:8020
16/12/08 23:47:57 INFO security.TokenCache: Got dt for hdfs://ip-172-31-15-248.ap-southeast-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.15.248:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@ROBGAJUDO.SG, renewer=yarn, realUser=, issueDate=1481258877445, maxDate=1481863677445, sequenceNumber=2, masterKeyId=4)
16/12/08 23:47:57 INFO input.FileInputFormat: Total input paths to process : 2
Spent 366ms computing base-splits.
Spent 3ms computing TeraScheduler splits.
Computing input splits took 371ms
Sampling 10 splits of 78
Making 8 from 100000 sampled records
Computing parititions took 915ms
Spent 1290ms computing partitions.
16/12/08 23:47:58 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-15-248.ap-southeast-1.compute.internal/172.31.15.248:8032
16/12/08 23:47:59 INFO mapreduce.JobSubmitter: number of splits:78
16/12/08 23:47:59 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1481257731610_0001
16/12/08 23:47:59 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.15.248:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@ROBGAJUDO.SG, renewer=yarn, realUser=, issueDate=1481258877445, maxDate=1481863677445, sequenceNumber=2, masterKeyId=4)
16/12/08 23:48:00 INFO impl.YarnClientImpl: Submitted application application_1481257731610_0001
16/12/08 23:48:00 INFO mapreduce.Job: The url to track the job: http://ip-172-31-15-248.ap-southeast-1.compute.internal:8088/proxy/application_1481257731610_0001/
16/12/08 23:48:00 INFO mapreduce.Job: Running job: job_1481257731610_0001
16/12/08 23:48:10 INFO mapreduce.Job: Job job_1481257731610_0001 running in uber mode : false
16/12/08 23:48:10 INFO mapreduce.Job:  map 0% reduce 0%
16/12/08 23:48:24 INFO mapreduce.Job:  map 4% reduce 0%
16/12/08 23:48:34 INFO mapreduce.Job:  map 14% reduce 0%
16/12/08 23:48:35 INFO mapreduce.Job:  map 15% reduce 0%
16/12/08 23:48:36 INFO mapreduce.Job:  map 17% reduce 0%
16/12/08 23:48:37 INFO mapreduce.Job:  map 18% reduce 0%
16/12/08 23:48:47 INFO mapreduce.Job:  map 19% reduce 0%
16/12/08 23:48:48 INFO mapreduce.Job:  map 22% reduce 0%
16/12/08 23:48:49 INFO mapreduce.Job:  map 25% reduce 0%
16/12/08 23:48:50 INFO mapreduce.Job:  map 32% reduce 0%
16/12/08 23:48:59 INFO mapreduce.Job:  map 33% reduce 0%
16/12/08 23:49:00 INFO mapreduce.Job:  map 36% reduce 0%
16/12/08 23:49:05 INFO mapreduce.Job:  map 46% reduce 0%
16/12/08 23:49:12 INFO mapreduce.Job:  map 47% reduce 0%
16/12/08 23:49:13 INFO mapreduce.Job:  map 50% reduce 0%
16/12/08 23:49:21 INFO mapreduce.Job:  map 58% reduce 0%
16/12/08 23:49:22 INFO mapreduce.Job:  map 60% reduce 0%
16/12/08 23:49:23 INFO mapreduce.Job:  map 62% reduce 0%
16/12/08 23:49:24 INFO mapreduce.Job:  map 64% reduce 0%
16/12/08 23:49:35 INFO mapreduce.Job:  map 65% reduce 0%
16/12/08 23:49:36 INFO mapreduce.Job:  map 76% reduce 0%
16/12/08 23:49:37 INFO mapreduce.Job:  map 78% reduce 0%
16/12/08 23:49:48 INFO mapreduce.Job:  map 82% reduce 0%
16/12/08 23:49:50 INFO mapreduce.Job:  map 83% reduce 0%
16/12/08 23:49:51 INFO mapreduce.Job:  map 91% reduce 0%
16/12/08 23:49:52 INFO mapreduce.Job:  map 92% reduce 0%
16/12/08 23:50:00 INFO mapreduce.Job:  map 96% reduce 0%
16/12/08 23:50:05 INFO mapreduce.Job:  map 99% reduce 0%
16/12/08 23:50:06 INFO mapreduce.Job:  map 100% reduce 13%
16/12/08 23:50:07 INFO mapreduce.Job:  map 100% reduce 17%
16/12/08 23:50:09 INFO mapreduce.Job:  map 100% reduce 22%
16/12/08 23:50:10 INFO mapreduce.Job:  map 100% reduce 24%
16/12/08 23:50:12 INFO mapreduce.Job:  map 100% reduce 38%
16/12/08 23:50:13 INFO mapreduce.Job:  map 100% reduce 45%
16/12/08 23:50:14 INFO mapreduce.Job:  map 100% reduce 51%
16/12/08 23:50:15 INFO mapreduce.Job:  map 100% reduce 54%
16/12/08 23:50:17 INFO mapreduce.Job:  map 100% reduce 63%
16/12/08 23:50:18 INFO mapreduce.Job:  map 100% reduce 67%
16/12/08 23:50:20 INFO mapreduce.Job:  map 100% reduce 74%
16/12/08 23:50:21 INFO mapreduce.Job:  map 100% reduce 78%
16/12/08 23:50:23 INFO mapreduce.Job:  map 100% reduce 81%
16/12/08 23:50:24 INFO mapreduce.Job:  map 100% reduce 84%
16/12/08 23:50:26 INFO mapreduce.Job:  map 100% reduce 86%
16/12/08 23:50:27 INFO mapreduce.Job:  map 100% reduce 89%
16/12/08 23:50:29 INFO mapreduce.Job:  map 100% reduce 93%
16/12/08 23:50:30 INFO mapreduce.Job:  map 100% reduce 94%
16/12/08 23:50:32 INFO mapreduce.Job:  map 100% reduce 96%
16/12/08 23:50:33 INFO mapreduce.Job:  map 100% reduce 97%
16/12/08 23:50:35 INFO mapreduce.Job:  map 100% reduce 99%
16/12/08 23:50:36 INFO mapreduce.Job:  map 100% reduce 100%
16/12/08 23:50:39 INFO mapreduce.Job: Job job_1481257731610_0001 completed successfully
16/12/08 23:50:39 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=2285956530
                FILE: Number of bytes written=4541227003
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=5120013416
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=258
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=78
                Launched reduce tasks=8
                Data-local map tasks=78
                Total time spent by all maps in occupied slots (ms)=1080067
                Total time spent by all reduces in occupied slots (ms)=280528
                Total time spent by all map tasks (ms)=1080067
                Total time spent by all reduce tasks (ms)=280528
                Total vcore-seconds taken by all map tasks=1080067
                Total vcore-seconds taken by all reduce tasks=280528
                Total megabyte-seconds taken by all map tasks=1105988608
                Total megabyte-seconds taken by all reduce tasks=287260672
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Map output bytes=5222400000
                Map output materialized bytes=2244506781
                Input split bytes=13416
                Combine input records=0
                Combine output records=0
                Reduce input groups=51200000
                Reduce shuffle bytes=2244506781
                Reduce input records=51200000
                Reduce output records=51200000
                Spilled Records=102400000
                Shuffled Maps =624
                Failed Shuffles=0
                Merged Map outputs=624
                GC time elapsed (ms)=21697
                CPU time spent (ms)=647770
                Physical memory (bytes) snapshot=45930205184
                Virtual memory (bytes) snapshot=135060422656
                Total committed heap usage (bytes)=52548861952
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=5120000000
        File Output Format Counters
                Bytes Written=5120000000
16/12/08 23:50:39 INFO terasort.TeraSort: done

real    2m45.467s
user    0m8.454s
sys     0m0.881s
```
