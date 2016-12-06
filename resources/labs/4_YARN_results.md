First run using default values in script
```
[ec2-user@ip-172-31-3-11 tmp]$ time sudo -u hdfs ./YARNtest.sh
Testing loop started on Tue Dec 6 04:22:47 EST 2016
Mapper containers is 2
Reducer containers is 2
Container Memory is 512
Mapper JVM heap is 409
Reducer JVM heap is 409
Deleted /results/tg-10GB-2-2-512
Deleted /results/ts-10GB-2-2-512
Container Memory is 1024
Mapper JVM heap is 819
Reducer JVM heap is 819
Deleted /results/tg-10GB-2-2-1024
Deleted /results/ts-10GB-2-2-1024
Testing loop ended on Tue Dec 6 04:24:26 EST 2016

real    1m39.318s
user    0m42.422s
sys     0m4.746s
```
2nd Run
```
[ec2-user@ip-172-31-3-11 tmp]$ time sudo -u hdfs ./YARNtest.sh
Testing loop started on Tue Dec 6 04:25:39 EST 2016
Mapper containers is 4
Reducer containers is 4
Container Memory is 1024
Mapper JVM heap is 819
Reducer JVM heap is 819
Deleted /results/tg-10GB-4-4-1024
Deleted /results/ts-10GB-4-4-1024
Container Memory is 2048
Mapper JVM heap is 1638
Reducer JVM heap is 1638
Deleted /results/tg-10GB-4-4-2048
Deleted /results/ts-10GB-4-4-2048
Testing loop ended on Tue Dec 6 04:27:22 EST 2016

real    1m42.746s
user    0m40.405s
sys     0m4.759s
```
3rd run
```
[ec2-user@ip-172-31-3-11 tmp]$ time sudo -u hdfs ./YARNtest.sh
Testing loop started on Tue Dec 6 04:29:53 EST 2016
Mapper containers is 1
Reducer containers is 1
Container Memory is 2048
Mapper JVM heap is 1638
Reducer JVM heap is 1638
Deleted /results/tg-10GB-1-1-2048
Deleted /results/ts-10GB-1-1-2048
Container Memory is 4096
Mapper JVM heap is 3276
Reducer JVM heap is 3276
Deleted /results/tg-10GB-1-1-4096
Deleted /results/ts-10GB-1-1-4096
Testing loop ended on Tue Dec 6 04:31:32 EST 2016

real    1m39.275s
user    0m40.928s
sys     0m4.813s
```
4th run
```
[ec2-user@ip-172-31-3-11 tmp]$ time sudo -u hdfs ./YARNtest.sh
Testing loop started on Tue Dec 6 04:32:38 EST 2016
Mapper containers is 6
Reducer containers is 6
Container Memory is 4096
Mapper JVM heap is 3276
Reducer JVM heap is 3276
Deleted /results/tg-10GB-6-6-4096
Deleted /results/ts-10GB-6-6-4096
Container Memory is 4096
Mapper JVM heap is 3276
Reducer JVM heap is 3276
Deleted /results/tg-10GB-6-6-4096
Deleted /results/ts-10GB-6-6-4096
Testing loop ended on Tue Dec 6 04:35:22 EST 2016

real    2m43.885s
user    0m42.684s
sys     0m4.829s
```
5th run
```
[ec2-user@ip-172-31-3-11 tmp]$ time sudo -u hdfs ./YARNtest.sh
Testing loop started on Tue Dec 6 04:37:54 EST 2016
Mapper containers is 2
Reducer containers is 2
Container Memory is 4096
Mapper JVM heap is 3276
Reducer JVM heap is 3276
Deleted /results/tg-10GB-2-2-4096
Deleted /results/ts-10GB-2-2-4096
Container Memory is 4096
Mapper JVM heap is 3276
Reducer JVM heap is 3276
Deleted /results/tg-10GB-2-2-4096
Deleted /results/ts-10GB-2-2-4096
Testing loop ended on Tue Dec 6 04:39:34 EST 2016

real    1m40.148s
user    0m40.186s
sys     0m4.711s
```
6th run
```
[ec2-user@ip-172-31-3-11 tmp]$ time sudo -u hdfs ./YARNtest.sh
Testing loop started on Tue Dec 6 04:47:20 EST 2016
Mapper containers is 2
Reducer containers is 2
Container Memory is 5147
Mapper JVM heap is 4117
Reducer JVM heap is 4117
Deleted /results/tg-10GB-2-2-5147
Deleted /results/ts-10GB-2-2-5147
Container Memory is 5147
Mapper JVM heap is 4117
Reducer JVM heap is 4117
Deleted /results/tg-10GB-2-2-5147
Deleted /results/ts-10GB-2-2-5147
Testing loop ended on Tue Dec 6 04:49:27 EST 2016

real    2m7.502s
user    0m39.921s
sys     0m4.825s
```

* Fastest run is the 4th run
```
[ec2-user@ip-172-31-3-11 tmp]$ time sudo -u hdfs ./YARNtest.sh
Testing loop started on Tue Dec 6 04:29:53 EST 2016
Mapper containers is 1
Reducer containers is 1
Container Memory is 2048
Mapper JVM heap is 1638
Reducer JVM heap is 1638
Deleted /results/tg-10GB-1-1-2048
Deleted /results/ts-10GB-1-1-2048
Container Memory is 4096
Mapper JVM heap is 3276
Reducer JVM heap is 3276
Deleted /results/tg-10GB-1-1-4096
Deleted /results/ts-10GB-1-1-4096
Testing loop ended on Tue Dec 6 04:31:32 EST 2016

real    1m39.275s
user    0m40.928s
sys     0m4.813s
```
* Longest run is the 6th run
```
[ec2-user@ip-172-31-3-11 tmp]$ time sudo -u hdfs ./YARNtest.sh
Testing loop started on Tue Dec 6 04:47:20 EST 2016
Mapper containers is 2
Reducer containers is 2
Container Memory is 5147
Mapper JVM heap is 4117
Reducer JVM heap is 4117
Deleted /results/tg-10GB-2-2-5147
Deleted /results/ts-10GB-2-2-5147
Container Memory is 5147
Mapper JVM heap is 4117
Reducer JVM heap is 4117
Deleted /results/tg-10GB-2-2-5147
Deleted /results/ts-10GB-2-2-5147
Testing loop ended on Tue Dec 6 04:49:27 EST 2016

real    2m7.502s
user    0m39.921s
sys     0m4.825s
```
