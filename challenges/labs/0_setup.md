- List the cloud provider you are using (AWS, GCE, Azure, other)
```
AWS
```

- List the Linux release you have chosen
```
Centos 6.4
```

- Show that the disk space on each node is at least 30 GB
```
[root@ip-172-31-18-35 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  720M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm
```
```
[root@ip-172-31-27-21 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  720M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm
```
```
[root@ip-172-31-20-160 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  720M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm
```
```
[root@ip-172-31-28-201 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  721M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm
```
```
[root@ip-172-31-21-17 ~]# df -h
Filesystem            Size  Used Avail Use% Mounted on
/dev/xvde              50G  720M   47G   2% /
tmpfs                 7.4G     0  7.4G   0% /dev/shm
```

- List the command and output for yum repolist enabled
```
[root@ip-172-31-18-35 ~]# yum repolist enabled
Loaded plugins: fastestmirror, presto
Determining fastest mirrors
 * base: ftp.heanet.ie
 * extras: ftp.heanet.ie
 * updates: ftp.heanet.ie
repo id                                                                repo name                                                                          status
base                                                                   CentOS-6 - Base                                                                    6,706
extras                                                                 CentOS-6 - Extras                                                                     45
updates                                                                CentOS-6 - Updates                                                                   354
repolist: 7,105
```

- Create Users and Groups
```
sudo groupadd conservative
sudo groupadd labour
sudo useradd -u 2000 -g conservative theresa
sudo useradd -u 3000 -g labour jeremy
```

- List the /etc/passwd entries for theresa and jeremy in your setup file
```
[root@ip-172-31-18-35 ~]# cat /etc/passwd | grep 'theresa\|jeremy'
theresa:x:2000:500::/home/theresa:/bin/bash
jeremy:x:3000:501::/home/jeremy:/bin/bash
```

- List the /etc/group entries for conservative and labour in your setup file
```
[root@ip-172-31-18-35 ~]# cat /etc/group | grep 'conservative\|labour'
conservative:x:500:
labour:x:501:
```