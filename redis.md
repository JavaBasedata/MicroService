```shell
[services/package]$ wget https://download.redis.io/releases/redis-6.2.3.tar.gz
[services/package]$ tar -zxf redis-6.2.3.tar.gz
[services/package]$ mv redis-6.2.3 ../redis/6.2
[services/package]$ cd ../redis/6.2
[services/redis/6.2]$ make
# 启动redis，默认端口6379
[services/redis/6.2]$ ./src/redis-server
# 使用指定配置文件启动redis
[services/redis/6.2]$ ./src/redis-server [file]
# 后台启动，日志输出到log文件
[services/redis/6.2]$ nohup ./src/redis-server > log/redis.log &
# 关闭redis
[services/redis/6.2]$  ./src/redis-cli shutdown

# redis中一些文件的作用
[services/redis/6.2/src]$ ./redis-benchmark //用于进行redis性能测试的工具
# 怀疑新版本redis-check-dump文件名换成了redis-check-rdb
[services/redis/6.2/src]$ ./redis-check-dump //用于修复出问题的dump.rdb文件
[services/redis/6.2/src]$ ./redis-cli //redis的客户端
[services/redis/6.2/src]$ ./redis-server //redis的服务端
[services/redis/6.2/src]$ ./redis-check-aof //用于修复出问题的AOF文件
[services/redis/6.2/src]$ ./redis-sentinel //用于集群管理

https://blog.csdn.net/liqingtx/article/details/60330555
```

```shell
# 创建软链接
[.local_ms]$ ln -s ../services/redis/6.2/src/redis-server ./
[.local_ms]$ ln -s ../services/redis/6.2/src/redis-cli ./
```

