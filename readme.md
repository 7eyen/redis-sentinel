#redis哨兵模式案例
1. 启动容器

`docker-compose up`
2. 进入redis-master容器运行下列命令，通过比对前后信息可发现主节点已经切换
    
`redis-cli -p 26379 info sentinel`
   
`redis-cli -a admin123456 shutdown`

`redis-cli -p 26379 info sentinel`

> ps：切换节点后，对应的redis配置文件中的`replicaof`项会被哨兵修改