- Create a precious directory in HDFS; copy the ZIP course file into it.
```
[root@ip-172-31-47-3 ~]# sudo -u hdfs hdfs dfs -mkdir /precious
[root@ip-172-31-47-3 ~]# sudo -u hdfs hdfs dfs -put /tmp/SEBC-master.zip /precious
```

- Enable snapshots for precious
```
[root@ip-172-31-47-3 ~]# sudo -u hdfs hdfs dfsadmin -allowSnapshot /precious
Allowing snaphot on /precious succeeded
```

- Create a snapshot called sebc-hdfs-test
```
[root@ip-172-31-47-3 ~]# sudo -u hdfs hdfs dfs -createSnapshot /precious sebc-hdfs-test
Created snapshot /precious/.snapshot/sebc-hdfs-test
```

- Delete the directory
```
[root@ip-172-31-47-3 ~]# sudo -u hdfs hdfs dfs -rm -r -skipTrash /precious
rm: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
```

- Delete the ZIP file
```
[root@ip-172-31-47-3 ~]# sudo -u hdfs hdfs dfs -rm /precious/SEBC-master.zip
17/06/06 15:19:06 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-36-205.eu-west-1.compute.internal:8020/precious/SEBC-master.zip' to trash at: hdfs://ip-172-31-36-205.eu-west-1.compute.internal:8020/user/hdfs/.Trash/Current/precious/SEBC-master.zip
```

- Restore the deleted file
```
[root@ip-172-31-47-3 ~]# sudo -u hdfs hdfs dfs -cp /precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /precious/
[root@ip-172-31-47-3 ~]# hdfs dfs -ls /precious/
Found 1 items
-rw-r--r--   3 hdfs supergroup     449822 2017-06-06 15:22 /precious/SEBC-master.zip
```
