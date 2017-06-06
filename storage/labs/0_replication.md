Source directory:
```
[root@ip-172-31-47-3 ~]# hdfs fsck /cmeralto/teragenout -files -blocks
Connecting to namenode via http://ip-172-31-36-205.eu-west-1.compute.internal:50070
FSCK started by root (auth:SIMPLE) from /172.31.47.3 for path /cmeralto/teragenout at Tue Jun 06 14:20:13 UTC 2017
/cmeralto/teragenout <dir>
/cmeralto/teragenout/_SUCCESS 0 bytes, 0 block(s):  OK

/cmeralto/teragenout/part-m-00000 256000000 bytes, 2 block(s):  OK
0. BP-1517820624-172.31.36.205-1496749763496:blk_1073742606_1782 len=134217728 Live_repl=3
1. BP-1517820624-172.31.36.205-1496749763496:blk_1073742607_1783 len=121782272 Live_repl=3

/cmeralto/teragenout/part-m-00001 256000000 bytes, 2 block(s):  OK
0. BP-1517820624-172.31.36.205-1496749763496:blk_1073742605_1781 len=134217728 Live_repl=3
1. BP-1517820624-172.31.36.205-1496749763496:blk_1073742608_1784 len=121782272 Live_repl=3

Status: HEALTHY
 Total size:    512000000 B
 Total dirs:    1
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 128000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Jun 06 14:20:13 UTC 2017 in 3 milliseconds


The filesystem under path '/cmeralto/teragenout' is HEALTHY
```

Target directory:
```
[root@ip-172-31-47-3 ~]# hdfs fsck /fpcel/teragenout -files -blocks
Connecting to namenode via http://ip-172-31-36-205.eu-west-1.compute.internal:50070
FSCK started by root (auth:SIMPLE) from /172.31.47.3 for path /fpcel/teragenout at Tue Jun 06 14:21:40 UTC 2017
/fpcel/teragenout <dir>
/fpcel/teragenout/_SUCCESS 0 bytes, 0 block(s):  OK

/fpcel/teragenout/part-m-00000 256000000 bytes, 2 block(s):  OK
0. BP-1517820624-172.31.36.205-1496749763496:blk_1073742672_1848 len=134217728 Live_repl=3
1. BP-1517820624-172.31.36.205-1496749763496:blk_1073742675_1851 len=121782272 Live_repl=3

/fpcel/teragenout/part-m-00001 256000000 bytes, 2 block(s):  OK
0. BP-1517820624-172.31.36.205-1496749763496:blk_1073742674_1850 len=134217728 Live_repl=3
1. BP-1517820624-172.31.36.205-1496749763496:blk_1073742676_1852 len=121782272 Live_repl=3

Status: HEALTHY
 Total size:    512000000 B
 Total dirs:    1
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 128000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Jun 06 14:21:40 UTC 2017 in 2 milliseconds


The filesystem under path '/fpcel/teragenout' is HEALTHY

```