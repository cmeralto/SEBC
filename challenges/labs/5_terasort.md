```
[root@ip-172-31-18-35 ~]# sudo su - theresa
[theresa@ip-172-31-18-35 ~]$ kinit
Password for theresa@CMERALTO.CO.UK:
[theresa@ip-172-31-18-35 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_2000
Default principal: theresa@CMERALTO.CO.UK

Valid starting     Expires            Service principal
06/09/17 10:29:58  06/10/17 10:29:58  krbtgt/CMERALTO.CO.UK@CMERALTO.CO.UK
        renew until 06/16/17 10:29:58
```

```
[theresa@ip-172-31-18-35 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/theresa/tgen512m /user/theresa/tgen512m_sorted
17/06/09 10:30:32 INFO terasort.TeraSort: starting
17/06/09 10:30:34 INFO hdfs.DFSClient: Created token for theresa: HDFS_DELEGATION_TOKEN owner=theresa@CMERALTO.CO.UK, renewer=yarn, realUser=, issueDate=1497004234431, maxDate=1497609034431, sequenceNumber=1, masterKeyId=2 on 172.31.18.35:8020
17/06/09 10:30:34 INFO security.TokenCache: Got dt for hdfs://ip-172-31-18-35.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.18.35:8020, Ident: (token for theresa: HDFS_DELEGATION_TOKEN owner=theresa@CMERALTO.CO.UK, renewer=yarn, realUser=, issueDate=1497004234431, maxDate=1497609034431, sequenceNumber=1, masterKeyId=2)
17/06/09 10:30:34 INFO input.FileInputFormat: Total input paths to process : 6
Spent 414ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 421ms
Sampling 10 splits of 156
Making 8 from 100000 sampled records
Computing parititions took 795ms
Spent 1218ms computing partitions.
17/06/09 10:30:35 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-18-35.eu-west-1.compute.internal/172.31.18.35:8032
17/06/09 10:30:35 INFO mapreduce.JobSubmitter: number of splits:156
17/06/09 10:30:36 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1497003787220_0001
17/06/09 10:30:36 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.18.35:8020, Ident: (token for theresa: HDFS_DELEGATION_TOKEN owner=theresa@CMERALTO.CO.UK, renewer=yarn, realUser=, issueDate=1497004234431, maxDate=1497609034431, sequenceNumber=1, masterKeyId=2)
17/06/09 10:30:37 INFO impl.YarnClientImpl: Submitted application application_1497003787220_0001
17/06/09 10:30:37 INFO mapreduce.Job: The url to track the job: http://ip-172-31-18-35.eu-west-1.compute.internal:8088/proxy/application_1497003787220_0001/
17/06/09 10:30:37 INFO mapreduce.Job: Running job: job_1497003787220_0001
17/06/09 10:30:48 INFO mapreduce.Job: Job job_1497003787220_0001 running in uber mode : false
17/06/09 10:30:48 INFO mapreduce.Job:  map 0% reduce 0%
17/06/09 10:30:58 INFO mapreduce.Job:  map 1% reduce 0%
17/06/09 10:31:00 INFO mapreduce.Job:  map 2% reduce 0%
17/06/09 10:31:05 INFO mapreduce.Job:  map 8% reduce 0%
17/06/09 10:31:09 INFO mapreduce.Job:  map 9% reduce 0%
17/06/09 10:31:11 INFO mapreduce.Job:  map 10% reduce 0%
17/06/09 10:31:15 INFO mapreduce.Job:  map 15% reduce 0%
17/06/09 10:31:17 INFO mapreduce.Job:  map 16% reduce 0%
17/06/09 10:31:19 INFO mapreduce.Job:  map 17% reduce 0%
17/06/09 10:31:25 INFO mapreduce.Job:  map 23% reduce 0%
17/06/09 10:31:28 INFO mapreduce.Job:  map 24% reduce 0%
17/06/09 10:31:30 INFO mapreduce.Job:  map 25% reduce 0%
17/06/09 10:31:35 INFO mapreduce.Job:  map 31% reduce 0%
17/06/09 10:31:38 INFO mapreduce.Job:  map 32% reduce 0%
17/06/09 10:31:39 INFO mapreduce.Job:  map 33% reduce 0%
17/06/09 10:31:44 INFO mapreduce.Job:  map 35% reduce 0%
17/06/09 10:31:45 INFO mapreduce.Job:  map 38% reduce 0%
17/06/09 10:31:46 INFO mapreduce.Job:  map 39% reduce 0%
17/06/09 10:31:47 INFO mapreduce.Job:  map 40% reduce 0%
17/06/09 10:31:53 INFO mapreduce.Job:  map 41% reduce 0%
17/06/09 10:31:54 INFO mapreduce.Job:  map 44% reduce 0%
17/06/09 10:31:55 INFO mapreduce.Job:  map 47% reduce 0%
17/06/09 10:31:57 INFO mapreduce.Job:  map 48% reduce 0%
17/06/09 10:32:02 INFO mapreduce.Job:  map 49% reduce 0%
17/06/09 10:32:03 INFO mapreduce.Job:  map 51% reduce 0%
17/06/09 10:32:04 INFO mapreduce.Job:  map 53% reduce 0%
17/06/09 10:32:05 INFO mapreduce.Job:  map 55% reduce 0%
17/06/09 10:32:06 INFO mapreduce.Job:  map 56% reduce 0%
17/06/09 10:32:12 INFO mapreduce.Job:  map 58% reduce 0%
17/06/09 10:32:13 INFO mapreduce.Job:  map 60% reduce 0%
17/06/09 10:32:14 INFO mapreduce.Job:  map 62% reduce 0%
17/06/09 10:32:15 INFO mapreduce.Job:  map 63% reduce 0%
17/06/09 10:32:20 INFO mapreduce.Job:  map 64% reduce 0%
17/06/09 10:32:21 INFO mapreduce.Job:  map 67% reduce 0%
17/06/09 10:32:22 INFO mapreduce.Job:  map 68% reduce 0%
17/06/09 10:32:23 INFO mapreduce.Job:  map 69% reduce 0%
17/06/09 10:32:24 INFO mapreduce.Job:  map 71% reduce 0%
17/06/09 10:32:29 INFO mapreduce.Job:  map 72% reduce 0%
17/06/09 10:32:30 INFO mapreduce.Job:  map 74% reduce 0%
17/06/09 10:32:31 INFO mapreduce.Job:  map 76% reduce 0%
17/06/09 10:32:32 INFO mapreduce.Job:  map 77% reduce 0%
17/06/09 10:32:33 INFO mapreduce.Job:  map 79% reduce 0%
17/06/09 10:32:39 INFO mapreduce.Job:  map 81% reduce 0%
17/06/09 10:32:40 INFO mapreduce.Job:  map 84% reduce 0%
17/06/09 10:32:41 INFO mapreduce.Job:  map 85% reduce 0%
17/06/09 10:32:42 INFO mapreduce.Job:  map 87% reduce 0%
17/06/09 10:32:48 INFO mapreduce.Job:  map 88% reduce 0%
17/06/09 10:32:49 INFO mapreduce.Job:  map 89% reduce 0%
17/06/09 10:32:51 INFO mapreduce.Job:  map 90% reduce 0%
17/06/09 10:32:56 INFO mapreduce.Job:  map 91% reduce 0%
17/06/09 10:32:57 INFO mapreduce.Job:  map 92% reduce 0%
17/06/09 10:32:58 INFO mapreduce.Job:  map 93% reduce 12%
17/06/09 10:32:59 INFO mapreduce.Job:  map 93% reduce 15%
17/06/09 10:33:00 INFO mapreduce.Job:  map 93% reduce 23%
17/06/09 10:33:01 INFO mapreduce.Job:  map 94% reduce 23%
17/06/09 10:33:02 INFO mapreduce.Job:  map 94% reduce 27%
17/06/09 10:33:03 INFO mapreduce.Job:  map 96% reduce 27%
17/06/09 10:33:05 INFO mapreduce.Job:  map 96% reduce 28%
17/06/09 10:33:07 INFO mapreduce.Job:  map 97% reduce 28%
17/06/09 10:33:08 INFO mapreduce.Job:  map 98% reduce 28%
17/06/09 10:33:09 INFO mapreduce.Job:  map 99% reduce 28%
17/06/09 10:33:12 INFO mapreduce.Job:  map 100% reduce 29%
17/06/09 10:33:14 INFO mapreduce.Job:  map 100% reduce 31%
17/06/09 10:33:16 INFO mapreduce.Job:  map 100% reduce 45%
17/06/09 10:33:17 INFO mapreduce.Job:  map 100% reduce 49%
17/06/09 10:33:18 INFO mapreduce.Job:  map 100% reduce 58%
17/06/09 10:33:20 INFO mapreduce.Job:  map 100% reduce 61%
17/06/09 10:33:22 INFO mapreduce.Job:  map 100% reduce 69%
17/06/09 10:33:23 INFO mapreduce.Job:  map 100% reduce 79%
17/06/09 10:33:24 INFO mapreduce.Job:  map 100% reduce 83%
17/06/09 10:33:27 INFO mapreduce.Job:  map 100% reduce 84%
17/06/09 10:33:28 INFO mapreduce.Job:  map 100% reduce 88%
17/06/09 10:33:29 INFO mapreduce.Job:  map 100% reduce 90%
17/06/09 10:33:30 INFO mapreduce.Job:  map 100% reduce 94%
17/06/09 10:33:34 INFO mapreduce.Job:  map 100% reduce 97%
17/06/09 10:33:36 INFO mapreduce.Job:  map 100% reduce 100%
17/06/09 10:33:37 INFO mapreduce.Job: Job job_1497003787220_0001 completed successfully
17/06/09 10:33:37 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=2285720008
                FILE: Number of bytes written=4546687744
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=5120024024
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=492
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=156
                Launched reduce tasks=8
                Data-local map tasks=156
                Total time spent by all maps in occupied slots (ms)=1311949
                Total time spent by all reduces in occupied slots (ms)=353552
                Total time spent by all map tasks (ms)=1311949
                Total time spent by all reduce tasks (ms)=353552
                Total vcore-seconds taken by all map tasks=1311949
                Total vcore-seconds taken by all reduce tasks=353552
                Total megabyte-seconds taken by all map tasks=1343435776
                Total megabyte-seconds taken by all reduce tasks=362037248
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Map output bytes=5222400000
                Map output materialized bytes=2240103638
                Input split bytes=24024
                Combine input records=0
                Combine output records=0
                Reduce input groups=51200000
                Reduce shuffle bytes=2240103638
                Reduce input records=51200000
                Reduce output records=51200000
                Spilled Records=102400000
                Shuffled Maps =1248
                Failed Shuffles=0
                Merged Map outputs=1248
                GC time elapsed (ms)=29078
                CPU time spent (ms)=852580
                Physical memory (bytes) snapshot=81116495872
                Virtual memory (bytes) snapshot=454773555200
                Total committed heap usage (bytes)=82356207616
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
17/06/09 10:33:37 INFO terasort.TeraSort: done

real    3m5.635s
user    0m10.841s
sys     0m1.113s
```