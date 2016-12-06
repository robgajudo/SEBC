HDFS Lab: Replicate to another cluster
Choose a partner in class

Name a source directory after your GitHub handle
```
[ec2-user@ip-172-31-3-11 ~]$ sudo -u hdfs hadoop fs -mkdir /robgajudo
[ec2-user@ip-172-31-3-11 ~]$ sudo -u hdfs hadoop fs -ls /
Found 3 items
drwxr-xr-x   - hdfs supergroup          0 2016-12-05 21:26 /robgajudo
drwxrwxrwt   - hdfs supergroup          0 2016-12-05 06:18 /tmp
drwxr-xr-x   - hdfs supergroup          0 2016-12-05 06:19 /user
```
Name a target directory after your partner's GitHub handle
```
[ec2-user@ip-172-31-3-11 ~]$ sudo -u hdfs hadoop fs -mkdir /targetgithub
[ec2-user@ip-172-31-3-11 ~]$ sudo -u hdfs hadoop fs -ls /
Found 4 items
drwxr-xr-x   - hdfs supergroup          0 2016-12-05 21:26 /robgajudo
drwxr-xr-x   - hdfs supergroup          0 2016-12-05 21:41 /targetgithub
drwxrwxrwt   - hdfs supergroup          0 2016-12-05 06:18 /tmp
drwxr-xr-x   - hdfs supergroup          0 2016-12-05 06:19 /user
```
Use teragen to create a 500 MB file
```
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ sudo -u hdfs hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen 5242880 /robgajudo/terasort-inputrob
16/12/05 22:28:53 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-3-11.ap-southeast-1.compute.internal/172.31.3.11:8032
16/12/05 22:28:54 INFO terasort.TeraSort: Generating 5242880 using 2
16/12/05 22:28:54 INFO mapreduce.JobSubmitter: number of splits:2
16/12/05 22:28:55 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1480987579239_0003
16/12/05 22:28:55 INFO impl.YarnClientImpl: Submitted application application_1480987579239_0003
16/12/05 22:28:55 INFO mapreduce.Job: The url to track the job: http://ip-172-31-3-11.ap-southeast-1.compute.internal:8088/proxy/application_1480987579239_0003/
16/12/05 22:28:55 INFO mapreduce.Job: Running job: job_1480987579239_0003
16/12/05 22:29:01 INFO mapreduce.Job: Job job_1480987579239_0003 running in uber mode : false
16/12/05 22:29:01 INFO mapreduce.Job:  map 0% reduce 0%
16/12/05 22:29:10 INFO mapreduce.Job:  map 50% reduce 0%
16/12/05 22:29:11 INFO mapreduce.Job:  map 100% reduce 0%
16/12/05 22:29:11 INFO mapreduce.Job: Job job_1480987579239_0003 completed successfully
16/12/05 22:29:11 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=244296
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=167
                HDFS: Number of bytes written=524288000
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=4
        Job Counters
                Launched map tasks=2
                Other local map tasks=2
                Total time spent by all maps in occupied slots (ms)=15171
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=15171
                Total vcore-seconds taken by all map tasks=15171
                Total megabyte-seconds taken by all map tasks=15535104
        Map-Reduce Framework
                Map input records=5242880
                Map output records=5242880
                Input split bytes=167
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=182
                CPU time spent (ms)=14200
                Physical memory (bytes) snapshot=724471808
                Virtual memory (bytes) snapshot=3120947200
                Total committed heap usage (bytes)=862978048
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=11257830824958050
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=524288000
```
Issue encountered before generating the correct teragen output.
* Had a problem in generating 500 mb file with teragen since I used direct conversion from MB to Bytes
* Allocated Capacity for HDFS was used up and became full
* HDFS and YARN prompted critical level
Solution
* Delete the created file
```
[ec2-user@ip-172-31-3-14 ~]$ sudo -u hdfs hadoop fs -rm -r /robgajudo/terasort-inputrob
16/12/05 22:06:56 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-3-11.ap-southeast-1.compute.internal:8020/robgajudo/terasort-inputrob' to trash at: hdfs://ip-172-31-3-11.ap-southeast-1.compute.internal:8020/user/hdfs/.Trash/Current/robgajudo/terasort-inputrob1480993616377
```
* Also from trash
```
[ec2-user@ip-172-31-3-14 ~]$ sudo -u hdfs hadoop fs -rm -r /user/hdfs/.Trash/Current/robgajudo/terasort-inputrob
Deleted /user/hdfs/.Trash/Current/robgajudo/terasort-inputrob
```
Copy your partner's file to your target directory

Since I have no partner, I copied my own file to the target directory using distcp.

Let one partner use distCp on the command line
```
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ sudo -u hdfs hadoop distcp hdfs://52.77.255.85:8020/robgajudo/terasort-inputrob  hdfs://52.77.255.85:8020/targetgithub/terasort-inputrob
16/12/05 22:32:50 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hdfs://52.77.255.85:8020/robgajudo/terasort-inputrob], targetPath=hdfs://52.77.255.85:8020/targetgithub/terasort-inputrob, targetPathExists=false, filtersFile='null'}
16/12/05 22:32:50 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-3-11.ap-southeast-1.compute.internal/172.31.3.11:8032
16/12/05 22:32:51 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 4; dirCnt = 1
16/12/05 22:32:51 INFO tools.SimpleCopyListing: Build file listing completed.
16/12/05 22:32:51 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
16/12/05 22:32:51 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
16/12/05 22:32:51 INFO tools.DistCp: Number of paths in the copy list: 4
16/12/05 22:32:51 INFO tools.DistCp: Number of paths in the copy list: 4
16/12/05 22:32:51 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-3-11.ap-southeast-1.compute.internal/172.31.3.11:8032
16/12/05 22:32:52 INFO mapreduce.JobSubmitter: number of splits:3
16/12/05 22:32:52 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1480987579239_0004
16/12/05 22:32:52 INFO impl.YarnClientImpl: Submitted application application_1480987579239_0004
16/12/05 22:32:52 INFO mapreduce.Job: The url to track the job: http://ip-172-31-3-11.ap-southeast-1.compute.internal:8088/proxy/application_1480987579239_0004/
16/12/05 22:32:52 INFO tools.DistCp: DistCp job-id: job_1480987579239_0004
16/12/05 22:32:52 INFO mapreduce.Job: Running job: job_1480987579239_0004
16/12/05 22:32:58 INFO mapreduce.Job: Job job_1480987579239_0004 running in uber mode : false
16/12/05 22:32:58 INFO mapreduce.Job:  map 0% reduce 0%
16/12/05 22:33:04 INFO mapreduce.Job:  map 33% reduce 0%
16/12/05 22:33:09 INFO mapreduce.Job:  map 100% reduce 0%
16/12/05 22:33:09 INFO mapreduce.Job: Job job_1480987579239_0004 completed successfully
16/12/05 22:33:09 INFO mapreduce.Job: Counters: 33
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=375030
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=524289639
                HDFS: Number of bytes written=524288000
                HDFS: Number of read operations=56
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=13
        Job Counters
                Launched map tasks=3
                Other local map tasks=3
                Total time spent by all maps in occupied slots (ms)=21432
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=21432
                Total vcore-seconds taken by all map tasks=21432
                Total megabyte-seconds taken by all map tasks=21946368
        Map-Reduce Framework
                Map input records=4
                Map output records=0
                Input split bytes=345
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=192
                CPU time spent (ms)=12460
                Physical memory (bytes) snapshot=932343808
                Virtual memory (bytes) snapshot=4709724160
                Total committed heap usage (bytes)=1130889216
        File Input Format Counters
                Bytes Read=1294
        File Output Format Counters
                Bytes Written=0
        org.apache.hadoop.tools.mapred.CopyMapper$Counter
                BYTESCOPIED=524288000
                BYTESEXPECTED=524288000
                COPY=4
```
Let the other use BDR

* Used Scheduled replication through CM with source directory /robgajudo to /targetgithub
* Use hdfs fsck <path> -files -blocks on your source and target directories

Source
```
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ hdfs fsck /robgajudo -files -blocks
Connecting to namenode via http://ip-172-31-3-11.ap-southeast-1.compute.internal:50070
FSCK started by ec2-user (auth:SIMPLE) from /172.31.3.11 for path /robgajudo at Mon Dec 05 22:58:48 EST 2016
/robgajudo <dir>
/robgajudo/terasort-inputrob <dir>
/robgajudo/terasort-inputrob/_SUCCESS 0 bytes, 0 block(s):  OK

/robgajudo/terasort-inputrob/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-884406542-172.31.3.11-1480936588799:blk_1073743096_2272 len=134217728 Live_repl=3
1. BP-884406542-172.31.3.11-1480936588799:blk_1073743098_2274 len=127926272 Live_repl=3

/robgajudo/terasort-inputrob/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-884406542-172.31.3.11-1480936588799:blk_1073743095_2271 len=134217728 Live_repl=3
1. BP-884406542-172.31.3.11-1480936588799:blk_1073743097_2273 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    2
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Mon Dec 05 22:58:48 EST 2016 in 4 milliseconds


The filesystem under path '/robgajudo' is HEALTHY
```
* Before replication is triggered
```
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ hdfs fsck /targetgithub -files -blocks
Connecting to namenode via http://ip-172-31-3-11.ap-southeast-1.compute.internal:50070
FSCK started by ec2-user (auth:SIMPLE) from /172.31.3.11 for path /targetgithub at Mon Dec 05 22:59:05 EST 2016
/targetgithub <dir>
/targetgithub/terasort-inputrob <dir>
/targetgithub/terasort-inputrob/_SUCCESS 0 bytes, 0 block(s):  OK

/targetgithub/terasort-inputrob/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-884406542-172.31.3.11-1480936588799:blk_1073743118_2294 len=134217728 Live_repl=3
1. BP-884406542-172.31.3.11-1480936588799:blk_1073743121_2297 len=127926272 Live_repl=3

/targetgithub/terasort-inputrob/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-884406542-172.31.3.11-1480936588799:blk_1073743119_2295 len=134217728 Live_repl=3
1. BP-884406542-172.31.3.11-1480936588799:blk_1073743122_2298 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    2
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Mon Dec 05 22:59:05 EST 2016 in 1 milliseconds


The filesystem under path '/targetgithub' is HEALTHY
```
* After Replication
```
[ec2-user@ip-172-31-3-11 hadoop-0.20-mapreduce]$ hdfs fsck /targetgithub -files -blocks
Connecting to namenode via http://ip-172-31-3-11.ap-southeast-1.compute.internal:50070
FSCK started by ec2-user (auth:SIMPLE) from /172.31.3.11 for path /targetgithub at Mon Dec 05 23:00:32 EST 2016
/targetgithub <dir>
/targetgithub/robgajudo <dir>
/targetgithub/robgajudo/terasort-inputrob <dir>
/targetgithub/robgajudo/terasort-inputrob/_SUCCESS 0 bytes, 0 block(s):  OK

/targetgithub/robgajudo/terasort-inputrob/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-884406542-172.31.3.11-1480936588799:blk_1073743170_2346 len=134217728 Live_repl=3
1. BP-884406542-172.31.3.11-1480936588799:blk_1073743172_2348 len=127926272 Live_repl=3

/targetgithub/robgajudo/terasort-inputrob/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-884406542-172.31.3.11-1480936588799:blk_1073743171_2347 len=134217728 Live_repl=3
1. BP-884406542-172.31.3.11-1480936588799:blk_1073743173_2349 len=127926272 Live_repl=3

/targetgithub/terasort-inputrob <dir>
/targetgithub/terasort-inputrob/_SUCCESS 0 bytes, 0 block(s):  OK

/targetgithub/terasort-inputrob/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-884406542-172.31.3.11-1480936588799:blk_1073743118_2294 len=134217728 Live_repl=3
1. BP-884406542-172.31.3.11-1480936588799:blk_1073743121_2297 len=127926272 Live_repl=3

/targetgithub/terasort-inputrob/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-884406542-172.31.3.11-1480936588799:blk_1073743119_2295 len=134217728 Live_repl=3
1. BP-884406542-172.31.3.11-1480936588799:blk_1073743122_2298 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:    1048576000 B
 Total dirs:    4
 Total files:   6
 Total symlinks:                0
 Total blocks (validated):      8 (avg. block size 131072000 B)
 Minimally replicated blocks:   8 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Mon Dec 05 23:00:32 EST 2016 in 3 milliseconds


The filesystem under path '/targetgithub' is HEALTHY
```
