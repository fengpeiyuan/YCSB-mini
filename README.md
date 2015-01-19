Yahoo! Cloud System Benchmark (YCSB)
====================================

Links
-----
http://wiki.github.com/brianfrankcooper/YCSB/
http://research.yahoo.com/Web_Information_Management/YCSB
ycsb-users@yahoogroups.com

Getting Started
---------------

1. Download the latest release of YCSB:

    wget https://github.com/downloads/brianfrankcooper/YCSB/ycsb-0.1.4.tar.gz
    tar xfvz ycsb-0.1.4
    cd ycsb-0.1.4

2. Set up a database to benchmark. There is a README file under each binding
   directory.

3. Run YCSB command. 

    bin/ycsb load basic -P workloads/workloada
    bin/ycsb run basic -P workloads/workloada

   Running the `ycsb` command without any argument will print the usage. 
   
   See https://github.com/brianfrankcooper/YCSB/wiki/Running-a-Workload
   for a detailed documentation on how to run a workload.

   See https://github.com/brianfrankcooper/YCSB/wiki/Core-Properties for 
   the list of available workload properties.


bin/ycsb load redis-bio -P workloads/workloada -p "redis.conn.str=192.168.151.94:6381:12345"|tee logs/bio.log


bin/ycsb load redis-nio -P workloads/workloada -p "redis.conn.str=192.168.151.94:6381:12345" | tee logs/nio.log

bin/ycsb load redis-bio -P workloads/workloada -p "redis.conn.str=192.168.151.94:6381:12345" -p "redis.max.active=10000" -p "redis.max.idle=10"|tee logs/bio.log

bin/ycsb load redis-nio -threads 1000 -s -P workloads/workloada -p "redis.conn.str=172.17.42.88:9001,172.17.42.88:9002,172.17.42.88:9003,172.17.42.88:9004,172.17.42.88:9005,172.17.42.88:9006,172.17.42.88:9007,172.17.42.88:9008" | tee logs/nio.log

bin/ycsb load redis-bio -threads 1000 -s -P workloads/workloada -p "redis.conn.str=172.17.42.88:9001,172.17.42.88:9002,172.17.42.88:9003,172.17.42.88:9004,172.17.42.88:9005,172.17.42.88:9006,172.17.42.88:9007,172.17.42.88:9008" -p "redis.max.active=1" -p "redis.max.idle=1" -p "redis.max.wait=1"|tee logs/bio.log
