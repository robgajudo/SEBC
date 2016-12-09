```
[orchard@ip-172-31-15-248 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar pi 16 1000
Number of Maps  = 16
Samples per Map = 1000
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Wrote input for Map #10
Wrote input for Map #11
Wrote input for Map #12
Wrote input for Map #13
Wrote input for Map #14
Wrote input for Map #15
Starting Job
16/12/09 00:02:58 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-15-248.ap-southeast-1.compute.internal/172.31.15.248:8032
16/12/09 00:02:59 INFO hdfs.DFSClient: Created token for orchard: HDFS_DELEGATION_TOKEN owner=orchard@ROBGAJUDO.SG, renewer=yarn, realUser=, issueDate=1481259779149, maxDate=1481864579149, sequenceNumber=3, masterKeyId=4 on 172.31.15.248:8020
16/12/09 00:02:59 INFO security.TokenCache: Got dt for hdfs://ip-172-31-15-248.ap-southeast-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.15.248:8020, Ident: (token for orchard: HDFS_DELEGATION_TOKEN owner=orchard@ROBGAJUDO.SG, renewer=yarn, realUser=, issueDate=1481259779149, maxDate=1481864579149, sequenceNumber=3, masterKeyId=4)
16/12/09 00:02:59 INFO input.FileInputFormat: Total input paths to process : 16
16/12/09 00:02:59 INFO mapreduce.JobSubmitter: number of splits:16
16/12/09 00:02:59 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1481257731610_0002
16/12/09 00:02:59 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.15.248:8020, Ident: (token for orchard: HDFS_DELEGATION_TOKEN owner=orchard@ROBGAJUDO.SG, renewer=yarn, realUser=, issueDate=1481259779149, maxDate=1481864579149, sequenceNumber=3, masterKeyId=4)
16/12/09 00:03:00 INFO impl.YarnClientImpl: Submitted application application_1481257731610_0002
16/12/09 00:03:00 INFO mapreduce.Job: The url to track the job: http://ip-172-31-15-248.ap-southeast-1.compute.internal:8088/proxy/application_1481257731610_0002/
16/12/09 00:03:00 INFO mapreduce.Job: Running job: job_1481257731610_0002
16/12/09 00:03:09 INFO mapreduce.Job: Job job_1481257731610_0002 running in uber mode : false
16/12/09 00:03:09 INFO mapreduce.Job:  map 0% reduce 0%
16/12/09 00:03:18 INFO mapreduce.Job:  map 6% reduce 0%
16/12/09 00:03:19 INFO mapreduce.Job:  map 19% reduce 0%
16/12/09 00:03:27 INFO mapreduce.Job:  map 88% reduce 0%
16/12/09 00:03:34 INFO mapreduce.Job:  map 100% reduce 0%
16/12/09 00:03:36 INFO mapreduce.Job:  map 100% reduce 100%
16/12/09 00:03:36 INFO mapreduce.Job: Job job_1481257731610_0002 completed successfully
16/12/09 00:03:36 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=133
                FILE: Number of bytes written=2114000
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=4886
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=67
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=16
                Launched reduce tasks=1
                Data-local map tasks=16
                Total time spent by all maps in occupied slots (ms)=179889
                Total time spent by all reduces in occupied slots (ms)=6125
                Total time spent by all map tasks (ms)=179889
                Total time spent by all reduce tasks (ms)=6125
                Total vcore-seconds taken by all map tasks=179889
                Total vcore-seconds taken by all reduce tasks=6125
                Total megabyte-seconds taken by all map tasks=184206336
                Total megabyte-seconds taken by all reduce tasks=6272000
        Map-Reduce Framework
                Map input records=16
                Map output records=32
                Map output bytes=288
                Map output materialized bytes=544
                Input split bytes=2998
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=544
                Reduce input records=32
                Reduce output records=0
                Spilled Records=64
                Shuffled Maps =16
                Failed Shuffles=0
                Merged Map outputs=16
                GC time elapsed (ms)=874
                CPU time spent (ms)=14770
                Physical memory (bytes) snapshot=7454683136
                Virtual memory (bytes) snapshot=26703413248
                Total committed heap usage (bytes)=8644984832
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=1888
        File Output Format Counters
                Bytes Written=97
Job Finished in 37.819 seconds
Estimated value of Pi is 3.14250000000000000000

real    0m41.642s
user    0m5.901s
sys     0m0.755s
```
