```
[root@ip-172-31-18-35 ~]# sudo su - jeremy
[jeremy@ip-172-31-18-35 ~]$ kinit
Password for jeremy@CMERALTO.CO.UK:
[jeremy@ip-172-31-18-35 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_3000
Default principal: jeremy@CMERALTO.CO.UK

Valid starting     Expires            Service principal
06/09/17 10:36:22  06/10/17 10:36:22  krbtgt/CMERALTO.CO.UK@CMERALTO.CO.UK
        renew until 06/16/17 10:36:22
[jeremy@ip-172-31-18-35 ~]$
```

```
[jeremy@ip-172-31-18-35 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar pi 4 100000
Number of Maps  = 4
Samples per Map = 100000
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Starting Job
17/06/09 10:37:22 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-18-35.eu-west-1.compute.internal/172.31.18.35:8032
17/06/09 10:37:22 INFO hdfs.DFSClient: Created token for jeremy: HDFS_DELEGATION_TOKEN owner=jeremy@CMERALTO.CO.UK, renewer=yarn, realUser=, issueDate=1497004642741, maxDate=1497609442741, sequenceNumber=2, masterKeyId=2 on 172.31.18.35:8020
17/06/09 10:37:22 INFO security.TokenCache: Got dt for hdfs://ip-172-31-18-35.eu-west-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.18.35:8020, Ident: (token for jeremy: HDFS_DELEGATION_TOKEN owner=jeremy@CMERALTO.CO.UK, renewer=yarn, realUser=, issueDate=1497004642741, maxDate=1497609442741, sequenceNumber=2, masterKeyId=2)
17/06/09 10:37:22 INFO input.FileInputFormat: Total input paths to process : 4
17/06/09 10:37:22 INFO mapreduce.JobSubmitter: number of splits:4
17/06/09 10:37:23 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1497003787220_0002
17/06/09 10:37:23 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.18.35:8020, Ident: (token for jeremy: HDFS_DELEGATION_TOKEN owner=jeremy@CMERALTO.CO.UK, renewer=yarn, realUser=, issueDate=1497004642741, maxDate=1497609442741, sequenceNumber=2, masterKeyId=2)
17/06/09 10:37:23 INFO impl.YarnClientImpl: Submitted application application_1497003787220_0002
17/06/09 10:37:23 INFO mapreduce.Job: The url to track the job: http://ip-172-31-18-35.eu-west-1.compute.internal:8088/proxy/application_1497003787220_0002/
17/06/09 10:37:23 INFO mapreduce.Job: Running job: job_1497003787220_0002
17/06/09 10:37:32 INFO mapreduce.Job: Job job_1497003787220_0002 running in uber mode : false
17/06/09 10:37:32 INFO mapreduce.Job:  map 0% reduce 0%
17/06/09 10:37:42 INFO mapreduce.Job:  map 100% reduce 0%
17/06/09 10:37:48 INFO mapreduce.Job:  map 100% reduce 100%
17/06/09 10:37:48 INFO mapreduce.Job: Job job_1497003787220_0002 completed successfully
17/06/09 10:37:48 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=68
                FILE: Number of bytes written=632048
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1192
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=19
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=4
                Launched reduce tasks=1
                Data-local map tasks=4
                Total time spent by all maps in occupied slots (ms)=33675
                Total time spent by all reduces in occupied slots (ms)=3264
                Total time spent by all map tasks (ms)=33675
                Total time spent by all reduce tasks (ms)=3264
                Total vcore-seconds taken by all map tasks=33675
                Total vcore-seconds taken by all reduce tasks=3264
                Total megabyte-seconds taken by all map tasks=34483200
                Total megabyte-seconds taken by all reduce tasks=3342336
        Map-Reduce Framework
                Map input records=4
                Map output records=8
                Map output bytes=72
                Map output materialized bytes=140
                Input split bytes=720
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=140
                Reduce input records=8
                Reduce output records=0
                Spilled Records=16
                Shuffled Maps =4
                Failed Shuffles=0
                Merged Map outputs=4
                GC time elapsed (ms)=463
                CPU time spent (ms)=4630
                Physical memory (bytes) snapshot=2025222144
                Virtual memory (bytes) snapshot=13870129152
                Total committed heap usage (bytes)=2167406592
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=472
        File Output Format Counters
                Bytes Written=97
Job Finished in 26.529 seconds
Estimated value of Pi is 3.14161000000000000000

real    0m30.053s
user    0m9.109s
sys     0m1.001s
```