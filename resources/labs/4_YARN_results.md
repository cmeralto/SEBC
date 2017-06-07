- Fastest run
```
############################

Num Mappers:  2
Num Reducers:  2
Container Memory:  1024
MAP Opts Max heap:  819
RED Opts Max heap:  819
TERAGEN Time:

real    0m25.733s
user    0m6.215s
sys     0m0.776s
TERASORT Time:

real    0m49.457s
user    0m7.569s
sys     0m0.698s
Deleted /results/tg-1GB-2-2-1024
Deleted /results/ts-1GB-2-2-1024

############################
```

- Slower run
```
############################

Num Mappers:  8
Num Reducers:  1
Container Memory:  1024
MAP Opts Max heap:  819
RED Opts Max heap:  819
TERAGEN Time:

real    0m29.703s
user    0m5.863s
sys     0m0.656s
TERASORT Time:

real    1m5.312s
user    0m7.811s
sys     0m0.753s
Deleted /results/tg-1GB-8-1-1024
Deleted /results/ts-1GB-8-1-1024

############################
```