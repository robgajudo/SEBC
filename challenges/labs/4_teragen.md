```
[root@ip-172-31-15-248 ~]# time sudo -u raffles hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -D dfs.blocksize=64m 51200000 /user/raffles/tgen512m/teragen-out
16/12/08 22:38:20 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-15-248.ap-southeast-1.compute.internal/172.31.15.248:8032
16/12/08 22:38:20 INFO terasort.TeraSort: Generating 51200000 using 2
16/12/08 22:38:20 INFO mapreduce.JobSubmitter: number of splits:2
16/12/08 22:38:21 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1481253242122_0001
16/12/08 22:38:21 INFO impl.YarnClientImpl: Submitted application application_1481253242122_0001
16/12/08 22:38:21 INFO mapreduce.Job: The url to track the job: http://ip-172-31-15-248.ap-southeast-1.compute.internal:8088/proxy/application_1481253242122_0001/
16/12/08 22:38:21 INFO mapreduce.Job: Running job: job_1481253242122_0001
16/12/08 22:38:28 INFO mapreduce.Job: Job job_1481253242122_0001 running in uber mode : false
16/12/08 22:38:28 INFO mapreduce.Job:  map 0% reduce 0%
16/12/08 22:38:42 INFO mapreduce.Job:  map 9% reduce 0%
16/12/08 22:38:45 INFO mapreduce.Job:  map 17% reduce 0%
16/12/08 22:38:48 INFO mapreduce.Job:  map 25% reduce 0%
16/12/08 22:38:51 INFO mapreduce.Job:  map 29% reduce 0%
16/12/08 22:38:54 INFO mapreduce.Job:  map 33% reduce 0%
16/12/08 22:38:57 INFO mapreduce.Job:  map 36% reduce 0%
16/12/08 22:39:00 INFO mapreduce.Job:  map 40% reduce 0%
16/12/08 22:39:03 INFO mapreduce.Job:  map 43% reduce 0%
16/12/08 22:39:06 INFO mapreduce.Job:  map 47% reduce 0%
16/12/08 22:39:09 INFO mapreduce.Job:  map 50% reduce 0%
16/12/08 22:39:12 INFO mapreduce.Job:  map 54% reduce 0%
16/12/08 22:39:15 INFO mapreduce.Job:  map 58% reduce 0%
16/12/08 22:39:18 INFO mapreduce.Job:  map 61% reduce 0%
16/12/08 22:39:21 INFO mapreduce.Job:  map 64% reduce 0%
16/12/08 22:39:24 INFO mapreduce.Job:  map 67% reduce 0%
16/12/08 22:39:27 INFO mapreduce.Job:  map 70% reduce 0%
16/12/08 22:39:31 INFO mapreduce.Job:  map 74% reduce 0%
16/12/08 22:39:34 INFO mapreduce.Job:  map 81% reduce 0%
16/12/08 22:39:37 INFO mapreduce.Job:  map 85% reduce 0%
16/12/08 22:39:40 INFO mapreduce.Job:  map 88% reduce 0%
16/12/08 22:39:44 INFO mapreduce.Job:  map 92% reduce 0%
16/12/08 22:39:47 INFO mapreduce.Job:  map 95% reduce 0%
16/12/08 22:39:49 INFO mapreduce.Job:  map 96% reduce 0%
16/12/08 22:39:50 INFO mapreduce.Job:  map 98% reduce 0%
16/12/08 22:39:51 INFO mapreduce.Job:  map 99% reduce 0%
16/12/08 22:39:52 INFO mapreduce.Job:  map 100% reduce 0%
16/12/08 22:39:52 INFO mapreduce.Job: Job job_1481253242122_0001 completed successfully
16/12/08 22:39:52 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=245752
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=170
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=4
        Job Counters
                Launched map tasks=2
                Other local map tasks=2
                Total time spent by all maps in occupied slots (ms)=161504
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=161504
                Total vcore-seconds taken by all map tasks=161504
                Total megabyte-seconds taken by all map tasks=165380096
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Input split bytes=170
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=676
                CPU time spent (ms)=79480
                Physical memory (bytes) snapshot=407609344
                Virtual memory (bytes) snapshot=3137777664
                Total committed heap usage (bytes)=418381824
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=109963291816450258
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=5120000000

real    1m35.277s
user    0m6.175s
sys     0m0.734s
```
hdfs dfs -ls /user/raffles/tgen512m
```
[root@ip-172-31-15-248 ~]# hdfs dfs -ls /user/raffles/tgen512m
Found 1 items
drwxr-xr-x   - raffles raffles          0 2016-12-08 22:39 /user/raffles/tgen512m/teragen-out
```
Blocks
```
[root@ip-172-31-2-18 ~]# sudo -u hdfs hadoop fsck /user/raffles/tgen512m/teragen-out -files -blocks
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-15-248.ap-southeast-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.2.18 for path /user/raffles/tgen512m/teragen-out at Thu Dec 08 22:45:12 EST 2016
/user/raffles/tgen512m/teragen-out <dir>
/user/raffles/tgen512m/teragen-out/_SUCCESS 0 bytes, 0 block(s):  OK

/user/raffles/tgen512m/teragen-out/part-m-00000 2560000000 bytes, 39 block(s):  OK
0. BP-1640033634-172.31.15.248-1481253187798:blk_1073742565_1741 len=67108864 Live_repl=3
1. BP-1640033634-172.31.15.248-1481253187798:blk_1073742566_1742 len=67108864 Live_repl=3
2. BP-1640033634-172.31.15.248-1481253187798:blk_1073742568_1744 len=67108864 Live_repl=3
3. BP-1640033634-172.31.15.248-1481253187798:blk_1073742570_1746 len=67108864 Live_repl=3
4. BP-1640033634-172.31.15.248-1481253187798:blk_1073742572_1748 len=67108864 Live_repl=3
5. BP-1640033634-172.31.15.248-1481253187798:blk_1073742574_1750 len=67108864 Live_repl=3
6. BP-1640033634-172.31.15.248-1481253187798:blk_1073742576_1752 len=67108864 Live_repl=3
7. BP-1640033634-172.31.15.248-1481253187798:blk_1073742578_1754 len=67108864 Live_repl=3
8. BP-1640033634-172.31.15.248-1481253187798:blk_1073742580_1756 len=67108864 Live_repl=3
9. BP-1640033634-172.31.15.248-1481253187798:blk_1073742583_1759 len=67108864 Live_repl=3
10. BP-1640033634-172.31.15.248-1481253187798:blk_1073742585_1761 len=67108864 Live_repl=3
11. BP-1640033634-172.31.15.248-1481253187798:blk_1073742587_1763 len=67108864 Live_repl=3
12. BP-1640033634-172.31.15.248-1481253187798:blk_1073742589_1765 len=67108864 Live_repl=3
13. BP-1640033634-172.31.15.248-1481253187798:blk_1073742591_1767 len=67108864 Live_repl=3
14. BP-1640033634-172.31.15.248-1481253187798:blk_1073742593_1769 len=67108864 Live_repl=3
15. BP-1640033634-172.31.15.248-1481253187798:blk_1073742595_1771 len=67108864 Live_repl=3
16. BP-1640033634-172.31.15.248-1481253187798:blk_1073742597_1773 len=67108864 Live_repl=3
17. BP-1640033634-172.31.15.248-1481253187798:blk_1073742599_1775 len=67108864 Live_repl=3
18. BP-1640033634-172.31.15.248-1481253187798:blk_1073742601_1777 len=67108864 Live_repl=3
19. BP-1640033634-172.31.15.248-1481253187798:blk_1073742602_1778 len=67108864 Live_repl=3
20. BP-1640033634-172.31.15.248-1481253187798:blk_1073742605_1781 len=67108864 Live_repl=3
21. BP-1640033634-172.31.15.248-1481253187798:blk_1073742606_1782 len=67108864 Live_repl=3
22. BP-1640033634-172.31.15.248-1481253187798:blk_1073742609_1785 len=67108864 Live_repl=3
23. BP-1640033634-172.31.15.248-1481253187798:blk_1073742611_1787 len=67108864 Live_repl=3
24. BP-1640033634-172.31.15.248-1481253187798:blk_1073742614_1790 len=67108864 Live_repl=3
25. BP-1640033634-172.31.15.248-1481253187798:blk_1073742616_1792 len=67108864 Live_repl=3
26. BP-1640033634-172.31.15.248-1481253187798:blk_1073742617_1793 len=67108864 Live_repl=3
27. BP-1640033634-172.31.15.248-1481253187798:blk_1073742620_1796 len=67108864 Live_repl=3
28. BP-1640033634-172.31.15.248-1481253187798:blk_1073742621_1797 len=67108864 Live_repl=3
29. BP-1640033634-172.31.15.248-1481253187798:blk_1073742624_1800 len=67108864 Live_repl=3
30. BP-1640033634-172.31.15.248-1481253187798:blk_1073742626_1802 len=67108864 Live_repl=3
31. BP-1640033634-172.31.15.248-1481253187798:blk_1073742628_1804 len=67108864 Live_repl=3
32. BP-1640033634-172.31.15.248-1481253187798:blk_1073742629_1805 len=67108864 Live_repl=3
33. BP-1640033634-172.31.15.248-1481253187798:blk_1073742631_1807 len=67108864 Live_repl=3
34. BP-1640033634-172.31.15.248-1481253187798:blk_1073742633_1809 len=67108864 Live_repl=3
35. BP-1640033634-172.31.15.248-1481253187798:blk_1073742636_1812 len=67108864 Live_repl=3
36. BP-1640033634-172.31.15.248-1481253187798:blk_1073742638_1814 len=67108864 Live_repl=3
37. BP-1640033634-172.31.15.248-1481253187798:blk_1073742640_1816 len=67108864 Live_repl=3
38. BP-1640033634-172.31.15.248-1481253187798:blk_1073742641_1817 len=9863168 Live_repl=3

/user/raffles/tgen512m/teragen-out/part-m-00001 2560000000 bytes, 39 block(s):  OK
0. BP-1640033634-172.31.15.248-1481253187798:blk_1073742564_1740 len=67108864 Live_repl=3
1. BP-1640033634-172.31.15.248-1481253187798:blk_1073742567_1743 len=67108864 Live_repl=3
2. BP-1640033634-172.31.15.248-1481253187798:blk_1073742569_1745 len=67108864 Live_repl=3
3. BP-1640033634-172.31.15.248-1481253187798:blk_1073742571_1747 len=67108864 Live_repl=3
4. BP-1640033634-172.31.15.248-1481253187798:blk_1073742573_1749 len=67108864 Live_repl=3
5. BP-1640033634-172.31.15.248-1481253187798:blk_1073742575_1751 len=67108864 Live_repl=3
6. BP-1640033634-172.31.15.248-1481253187798:blk_1073742577_1753 len=67108864 Live_repl=3
7. BP-1640033634-172.31.15.248-1481253187798:blk_1073742579_1755 len=67108864 Live_repl=3
8. BP-1640033634-172.31.15.248-1481253187798:blk_1073742581_1757 len=67108864 Live_repl=3
9. BP-1640033634-172.31.15.248-1481253187798:blk_1073742582_1758 len=67108864 Live_repl=3
10. BP-1640033634-172.31.15.248-1481253187798:blk_1073742584_1760 len=67108864 Live_repl=3
11. BP-1640033634-172.31.15.248-1481253187798:blk_1073742586_1762 len=67108864 Live_repl=3
12. BP-1640033634-172.31.15.248-1481253187798:blk_1073742588_1764 len=67108864 Live_repl=3
13. BP-1640033634-172.31.15.248-1481253187798:blk_1073742590_1766 len=67108864 Live_repl=3
14. BP-1640033634-172.31.15.248-1481253187798:blk_1073742592_1768 len=67108864 Live_repl=3
15. BP-1640033634-172.31.15.248-1481253187798:blk_1073742594_1770 len=67108864 Live_repl=3
16. BP-1640033634-172.31.15.248-1481253187798:blk_1073742596_1772 len=67108864 Live_repl=3
17. BP-1640033634-172.31.15.248-1481253187798:blk_1073742598_1774 len=67108864 Live_repl=3
18. BP-1640033634-172.31.15.248-1481253187798:blk_1073742600_1776 len=67108864 Live_repl=3
19. BP-1640033634-172.31.15.248-1481253187798:blk_1073742603_1779 len=67108864 Live_repl=3
20. BP-1640033634-172.31.15.248-1481253187798:blk_1073742604_1780 len=67108864 Live_repl=3
21. BP-1640033634-172.31.15.248-1481253187798:blk_1073742607_1783 len=67108864 Live_repl=3
22. BP-1640033634-172.31.15.248-1481253187798:blk_1073742610_1786 len=67108864 Live_repl=3
23. BP-1640033634-172.31.15.248-1481253187798:blk_1073742612_1788 len=67108864 Live_repl=3
24. BP-1640033634-172.31.15.248-1481253187798:blk_1073742613_1789 len=67108864 Live_repl=3
25. BP-1640033634-172.31.15.248-1481253187798:blk_1073742615_1791 len=67108864 Live_repl=3
26. BP-1640033634-172.31.15.248-1481253187798:blk_1073742618_1794 len=67108864 Live_repl=3
27. BP-1640033634-172.31.15.248-1481253187798:blk_1073742619_1795 len=67108864 Live_repl=3
28. BP-1640033634-172.31.15.248-1481253187798:blk_1073742622_1798 len=67108864 Live_repl=3
29. BP-1640033634-172.31.15.248-1481253187798:blk_1073742623_1799 len=67108864 Live_repl=3
30. BP-1640033634-172.31.15.248-1481253187798:blk_1073742625_1801 len=67108864 Live_repl=3
31. BP-1640033634-172.31.15.248-1481253187798:blk_1073742627_1803 len=67108864 Live_repl=3
32. BP-1640033634-172.31.15.248-1481253187798:blk_1073742630_1806 len=67108864 Live_repl=3
33. BP-1640033634-172.31.15.248-1481253187798:blk_1073742632_1808 len=67108864 Live_repl=3
34. BP-1640033634-172.31.15.248-1481253187798:blk_1073742634_1810 len=67108864 Live_repl=3
35. BP-1640033634-172.31.15.248-1481253187798:blk_1073742635_1811 len=67108864 Live_repl=3
36. BP-1640033634-172.31.15.248-1481253187798:blk_1073742637_1813 len=67108864 Live_repl=3
37. BP-1640033634-172.31.15.248-1481253187798:blk_1073742639_1815 len=67108864 Live_repl=3
38. BP-1640033634-172.31.15.248-1481253187798:blk_1073742642_1818 len=9863168 Live_repl=3

Status: HEALTHY
 Total size:    5120000000 B
 Total dirs:    1
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      78 (avg. block size 65641025 B)
 Minimally replicated blocks:   78 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Thu Dec 08 22:45:12 EST 2016 in 5 milliseconds


The filesystem under path '/user/raffles/tgen512m/teragen-out' is HEALTHY
```
