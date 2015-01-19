Mini Yahoo! Cloud System Benchmark (YCSB)
====================================

Description
-----
This project is still experimental and under early development. 

Getting Started
---------------
 Run YCSB command. 

    bin/ycsb load redis-nio -P workloads/workloada
    bin/ycsb run redis-bio -P workloads/workloada


Examples
--------

bin/ycsb load redis-bio -P workloads/workloada -p "redis.conn.str=192.168.151.94:6381:12345"|tee logs/bio.log


bin/ycsb load redis-nio -P workloads/workloada -p "redis.conn.str=192.168.151.94:6381:12345" | tee logs/nio.log

bin/ycsb load redis-bio -P workloads/workloada -p "redis.conn.str=192.168.151.94:6381:12345" -p "redis.max.active=10000" -p "redis.max.idle=10"|tee logs/bio.log

bin/ycsb load redis-nio -threads 1000 -s -P workloads/workloada -p "redis.conn.str=172.17.42.88:9001,172.17.42.88:9002,172.17.42.88:9003,172.17.42.88:9004,172.17.42.88:9005,172.17.42.88:9006,172.17.42.88:9007,172.17.42.88:9008" | tee logs/nio.log

bin/ycsb load redis-bio -threads 1000 -s -P workloads/workloada -p "redis.conn.str=172.17.42.88:9001,172.17.42.88:9002,172.17.42.88:9003,172.17.42.88:9004,172.17.42.88:9005,172.17.42.88:9006,172.17.42.88:9007,172.17.42.88:9008" -p "redis.max.active=1" -p "redis.max.idle=1" -p "redis.max.wait=1"|tee logs/bio.log
