1. Check vm.swappiness on all your nodes (Set the value to 1 if necessary)

```
[root@ip-172-31-46-176 ~]# sysctl vm.swappiness
vm.swappiness = 60

[root@ip-172-31-46-176 ~]# sysctl vm.swappiness=1
vm.swappiness = 1

[root@ip-172-31-46-176 ~]# sysctl vm.swappiness
vm.swappiness = 1
```

1.1 To configure swapiness to 1 permanent:

```
sudo bash -c "echo 'vm.swappiness = 1' >> /etc/sysctl.conf"
```

2 Show the mount attributes of all volumes

2.1 Mount volume
```
[root@ip-172-31-46-176 ~]# sudo mkdir -p /data/01
[root@ip-172-31-46-176 ~]# sudo mkfs -t ext4 /dev/xvdf
[root@ip-172-31-46-176 ~]# tune2fs -m 0 /dev/xvdf
[root@ip-172-31-46-176 ~]# mount /dev/xvdf /data/01
[root@ip-172-31-46-176 ~]# echo '/dev/xvdf /data/01 ext4 noatime 0 0' >> /etc/fstab
```

2.2 Mount commands
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

