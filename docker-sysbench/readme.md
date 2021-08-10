## 1. CPU Model Names on EKS Fargate 

Run `kubectl apply -f lscpu-fargate.yaml`

```
Model name:                      Intel(R) Xeon(R) CPU E5-2686 v4 @ 2.30GHz (Broadwell, i3 instances)
Model name:                      Intel(R) Xeon(R) Platinum 8259CL CPU @ 2.50GHz (m5 instances)
Model name:                      Intel(R) Xeon(R) Platinum 8175M CPU @ 2.50GHz (m5 instances)
Model name:                      Intel(R) Xeon(R) Platinum 8124M CPU @ 3.00GHz (c5 instances)
```

Summary: 
1. CPU on AWS Fargate can be powered by C5, M5 or R5
2. Not consistent performance can be expected  

## 2. Running sysbench on containers

- Refer to sysbench.yaml 
```
...
          args:
            ["cpu", "--threads=4", "--cpu-max-prime=20000", "--time=30", "run"]
...
          resources:
            limits:
              cpu: "4"
              memory: "4Gi"
```


### 2.1 Sysbench results on Fargate: 4 vCPU, 4 GB RAM 

- Score 39894
```
CPU speed:
    events per second:  1329.61

General statistics:
    total time:                          30.0027s
    total number of events:              39894
```

### 2.2 Sysbench results on c5.2xlarge worker node 

- Score 54963
```
CPU speed:
    events per second:  1831.91

General statistics:
    total time:                          30.0018s
    total number of events:              54963
```

### 2.3 Sysbench results on m5.2xlarge worker node

```
CPU speed:
    events per second:  1575.83

General statistics:
    total time:                          30.0024s
    total number of events:              47281
```

### 2.4 Sysbench results on r5.2xlarge worker node 

```
CPU speed:
    events per second:  1572.25

General statistics:
    total time:                          30.0014s
    total number of events:              47172
```

