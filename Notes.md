
### 3. 


stress-ng: info:  [331] dispatching hogs: 2 matrix
stress-ng: info:  [331] successful run completed in 60.00s (1 min, 0.00 secs)
stress-ng: info:  [331] stressor       bogo ops real time  usr time  sys time   bogo ops/s   bogo ops/s
stress-ng: info:  [331]                           (secs)    (secs)    (secs)   (real time) (usr+sys time)
stress-ng: info:  [331] matrix           204002     60.00    116.84      0.04      3400.04      1745.40
root@ubuntu-65cc85d95b-f2qcm:/# stress-ng --matrix 0 -t 60s --metrics-brief
stress-ng: info:  [334] dispatching hogs: 2 matrix
stress-ng: info:  [334] successful run completed in 60.01s (1 min, 0.01 secs)
stress-ng: info:  [334] stressor       bogo ops real time  usr time  sys time   bogo ops/s   bogo ops/s
stress-ng: info:  [334]                           (secs)    (secs)    (secs)   (real time) (usr+sys time)
stress-ng: info:  [334] matrix           204366     60.00    116.68      0.03      3406.10      1751.06
root@ubuntu-65cc85d95b-f2qcm:/# lscpu | grep Model


Model name:                      Intel(R) Xeon(R) Platinum 8175M CPU @ 2.50GHz

root@ubuntu-65cc85d95b-fwl5q:/# stress-ng --matrix 0 -t 60s --metrics-brief
stress-ng: info:  [337] dispatching hogs: 2 matrix
stress-ng: info:  [337] successful run completed in 60.00s (1 min, 0.00 secs)
stress-ng: info:  [337] stressor       bogo ops real time  usr time  sys time   bogo ops/s   bogo ops/s
stress-ng: info:  [337]                           (secs)    (secs)    (secs)   (real time) (usr+sys time)
stress-ng: info:  [337] matrix           229625     60.00    116.96      0.18      3827.09      1960.26

https://www.intel.com/content/dam/www/public/us/en/documents/product-briefs/cloudtech-brief-aws.pdf


Model name:                      Intel(R) Xeon(R) Platinum 8259CL CPU @ 2.50GHz   

root@ubuntu-665586db95-x4mtk:/# stress-ng --matrix 0 -t 60s --metrics-brief
stress-ng: info:  [4000] dispatching hogs: 4 matrix
stress-ng: info:  [4000] successful run completed in 60.00s (1 min, 0.00 secs)
stress-ng: info:  [4000] stressor       bogo ops real time  usr time  sys time   bogo ops/s   bogo ops/s
stress-ng: info:  [4000]                           (secs)    (secs)    (secs)   (real time) (usr+sys time)
stress-ng: info:  [4000] matrix           431944     60.00    235.46      0.18      7199.07      1833.07


^C
root@ubuntu-665586db95-x4mtk:/# sysbench --test=cpu --num-threads=4 --cpu-max-prime=50000 run
WARNING: the --test option is deprecated. You can pass a script name or path on the command line without any options.
WARNING: --num-threads is deprecated, use --threads instead
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 4
Initializing random number generator from current time


Prime numbers limit: 50000

Initializing worker threads...

Threads started!

CPU speed:
    events per second:   361.71

General statistics:
    total time:                          10.0092s
    total number of events:              3621

Latency (ms):
         min:                                    8.78
         avg:                                   11.05
         max:                                   34.09
         95th percentile:                       11.24
         sum:                                40015.87

Threads fairness:
    events (avg/stddev):           905.2500/3.63
    execution time (avg/stddev):   10.0040/0.00

root@ubuntu-665586db95-x4mtk:/# 
