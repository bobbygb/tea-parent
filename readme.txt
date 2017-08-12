#centos
root/root

#zookeeper
./zkServer.sh start

#redis
./redis-trib.rb create --replicas 1 127.0.0.1:7000 127.0.0.1:7001 127.0.0.1:7002 127.0.0.1:7003 127.0.0.1:7004 127.0.0.1:7005

[ERR] Node 192.168.40.130:7000 is not empty. Either the node already knows other nodes (check with CLUSTER NODES) or contains some key in database 0

find / -name "nodes-6379.conf" | xargs rm -rf 
find / -name "dump.rdb" | xargs rm -rf
find / -name "appendonly.aof" | xargs rm -rf

#rabbitmq
rabbitmq-server –detached
rabbitmqctl stop
http://192.168.1.103:15672/ admin/admin

