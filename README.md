master: docker run -d --name redis-master -v /home/vagrant/moip/github/redis_tests/redis_master.conf:/etc/redis/redis.conf -P redis redis-server /etc/redis/redis.conf

slave: docker run -d  --name redis-slave1 -v /home/vagrant/moip/github/redis_tests/redis_slave.conf:/etc/redis/redis.conf -P --link redis-master:master  redis redis-server /etc/redis/redis.conf
