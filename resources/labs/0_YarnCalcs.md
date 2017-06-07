1 - OS Memory and Cores
```
From Cloudera's excel YARN tunning: 
	-> Most operating systems use 4-8GB minimum. OS Memory defined to 8 GB
	-> Reduce the numbers of cores from 2 to 1
```

2 - YARM RM Properties
```
From Cloudera's recommendation YARN tunning (https://www.cloudera.com/documentation/enterprise/5-8-x/topics/cm_mc_yarn_service.html):
  -> yarn.scheduler.maximum-allocation-vcores set to match yarn.nodemanager.resource.cpu-vcores
  -> yarn.scheduler.maximum-allocation-mb set to match yarn.nodemanager.resource.memory-mb
```

3 - Task Container Settings
```
From Cloudera's recommendation YARN tunning (https://www.cloudera.com/documentation/enterprise/5-8-x/topics/cm_mc_yarn_service.html):
  -> mapreduce.map.java.opts.max.heap defined as 0,75 * mapreduce.map.memory.mb
  -> mapreduce.reduce.java.opts.max.heap defined as 0,75 * mapreduce.reduce.memory.mb
  -> mapreduce.map.memory.mb MIN defined to 1024 Mb Set a lower value in order to applications request a minimmun/fair start up resource
  -> mapreduce.map.cpu.vcores MIN defined to 1 Set a lower value in order to applications request a minimmun/fair start up resource
```

4 - MapReduce AM Settings
```
  -> yarn.app.mapreduce.am.resource.mb must be defined as Mb. Changed from 1 to 1024
  -> yarn.app.mapreduce.am.resource.command-opts defined as 0,75 * yarn.app.mapreduce.am.resource.mb
```

5 - Gateway Settings
```
From Cloudera's recommendation YARN tunning (https://www.cloudera.com/documentation/enterprise/5-8-x/topics/cm_mc_yarn_service.html):
	->  mapreduce.map.java.opts.max.heap parameter changed to be 0,75 * mapreduce.map.memory.mb
	-> mapreduce.reduce.java.opts.max.heap parameter changed to be 0,75 * mapreduce.reduce.memory.mb
	-> mapreduce.job.maps not defined because in YARN, the best practice is to use the number of mappers based on input splits.
```

6 - What criteria affects workload factor? What does a value of 1, 2, or 4 signify?
```
The workload factor represents the ratio between CPU/Mmmory/IO. Based on the workload/uses cases this value must be updated. Example: Machine Learning worloads uses more CPU bound, but ETL jobs (Data movement and transformation) uses more IO.
```