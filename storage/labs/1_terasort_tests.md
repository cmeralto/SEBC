- Teragen command
```
[cmeralto@ip-172-31-47-3 ~]# time hadoop jar /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/hadoop-examples.jar teragen -D dfs.block.size=33554432 -D mapreduce.job.maps=4 100000000 /user/cmeralto/teragen10G
```

- Terasort command
```
[cmeralto@ip-172-31-47-3 ~]# time hadoop jar /opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/hadoop-examples.jar terasort /user/cmeralto/teragen10G /user/cmeralto/teragen10G-sorted
```

- Teragen time results
```
real    4m30.226s
user    0m6.808s
sys     0m0.723s

```

- Terasort time results
```
real    10m30.618s
user    0m10.126s
sys     0m1.060s
```