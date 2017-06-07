#!/bin/sh
# Confirm the path values given below correspond to your installation

MR=/opt/cloudera/parcels/CDH-5.8.3-1.cdh5.8.3.p0.2/jars/
HADOOP=/opt/cloudera/parcels/CDH/bin

# Mark start of the loop
echo Testing loop started on `date`

# Mapper containers
for i in 2 4 8   
do
   # Reducer containers
   for j in 1 2
   do                 
      # Container memory
      for k in 512 1024 
      do                         
         # Set mapper JVM heap 
         MAP_MB=`echo "($k*0.8)/1" | bc` 

         # Set reducer JVM heap 
         RED_MB=`echo "($k*0.8)/1" | bc` 

        echo "Num Mappers: " $i 
        echo "Num Reducers: " $j 
        echo "Container Memory: " $k 
        echo "MAP Opts Max heap: " $MAP_MB 
        echo "RED Opts Max heap: " $RED_MB 

        echo "TERAGEN Time: " 
        time ${HADOOP}/hadoop jar ${MR}/hadoop-examples.jar teragen \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     10000000 /results/tg-1GB-${i}-${j}-${k} 1>tera_${i}_${j}_${k}.out 2>tera_${i}_${j}_${k}.err                 


       echo "TERASORT Time: "
       time ${HADOOP}/hadoop jar $MR/hadoop-examples.jar terasort \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.job.reduces=$j \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     -Dmapreduce.reduce.memory.mb=$k \
                     -Dmapreduce.reduce.java.opts.max.heap=$RED_MB \
	             /results/tg-1GB-${i}-${j}-${k}  \
                     /results/ts-1GB-${i}-${j}-${k} 1>>tera_${i}_${j}_${k}.out 2>>tera_${i}_${j}_${k}.err                         

        $HADOOP/hadoop fs -rm -r -skipTrash /results/tg-1GB-${i}-${j}-${k}                         
        $HADOOP/hadoop fs -rm -r -skipTrash /results/ts-1GB-${i}-${j}-${k} 

        echo "" 
        echo "############################" 
        echo ""     

      done
   done
done

echo Testing loop ended on `date`
