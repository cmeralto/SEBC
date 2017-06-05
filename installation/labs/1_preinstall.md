1. Check vm.swappiness on all your nodes (Set the value to 1 if necessary)

```
[root@ip-172-31-46-176 ~]# sysctl vm.swappiness
vm.swappiness = 60

[root@ip-172-31-46-176 ~]# sysctl vm.swappiness=1
vm.swappiness = 1

[root@ip-172-31-46-176 ~]# sysctl vm.swappiness
vm.swappiness = 1
```

- To configure swapiness to 1 permanently:

```
sudo bash -c "echo 'vm.swappiness = 1' >> /etc/sysctl.conf"
```

2 Show the mount attributes of all volumes

- Mount volume
```
[root@ip-172-31-46-176 ~]# sudo mkdir -p /data/01
[root@ip-172-31-46-176 ~]# sudo mkfs -t ext4 /dev/xvdf
[root@ip-172-31-46-176 ~]# tune2fs -m 0 /dev/xvdf
[root@ip-172-31-46-176 ~]# mount /dev/xvdf /data/01
[root@ip-172-31-46-176 ~]# echo '/dev/xvdf /data/01 ext4 noatime 0 0' >> /etc/fstab
```

- Mount commands
```
[root@ip-172-31-46-176 ~]# mount
/dev/xvde on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)
/dev/xvdf on /data/01 type ext4 (rw)
```

3. Show the reserve space of any non-root, ext-based volumes 
```
[root@ip-172-31-46-176 ~]# tune2fs -l /dev/xvdf | grep Reserved
Reserved block count:     0
Reserved GDT blocks:      992
Reserved blocks uid:      0 (user root)
Reserved blocks gid:      0 (group root)
```

4. Disable transparent hugepage support


5. List your network interface configuration
```
[root@ip-172-31-46-176 ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 16436 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:ed:96:65:c8:4c brd ff:ff:ff:ff:ff:ff
    inet 172.31.46.176/20 brd 172.31.47.255 scope global eth0
    inet6 fe80::8ed:96ff:fe65:c84c/64 scope link
       valid_lft forever preferred_lft forever
```


6. List forward and reverse host lookups using getent or nslookup

- Install bind-utils
```
[root@ip-172-31-46-176 ~]# yum install bind-utils
```

- Forward 
```
[root@ip-172-31-46-176 ~]# nslookup ec2-52-211-52-24.eu-west-1.compute.amazonaws.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ec2-52-211-52-24.eu-west-1.compute.amazonaws.com
Address: 172.31.46.176
```
- Reverse 
```
[root@ip-172-31-46-176 ~]# nslookup 52.211.52.24
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
24.52.211.52.in-addr.arpa       name = ec2-52-211-52-24.eu-west-1.compute.amazonaws.com.
```

7. Show the nscd service is running
```
[root@ip-172-31-46-176 ~]# yum install nscd

[root@ip-172-31-46-176 ~]# service nscd start
Starting nscd:                                             [  OK  ]

[root@ip-172-31-46-176 ~]# service nscd status
nscd (pid 8413) is running...
```

8. Show the ntpd service is running
```
[root@ip-172-31-46-176 ~]# yum install ntp

[root@ip-172-31-46-176 ~]# service ntpd start
Starting ntpd:                                             [  OK  ]

[root@ip-172-31-46-176 ~]# service ntpd status
ntpd (pid  8472) is running...

```