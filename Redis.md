+ [Install Redis on Linux](https://redis.io/docs/getting-started/installation/install-redis-on-linux/)

```shell
# Check Redis Version
redis-server --version
# Or
redis-server -v | cut -d= -f2 | cut -d ' ' -f1


```

```shell
sudo cp /etc/redis/redis.conf /etc/redis/redis.conf.original
# sudo sed -r -i 's/^bind 127.0.0.1 ::1/bind 0.0.0.0 ::1/g' /etc/redis/redis.conf
sudo sed -r -i 's/^bind 127.0.0.1 -::1/bind 0.0.0.0 -::1/g' /etc/redis/redis.conf
sudo sed -r -i "s/^daemonize no/daemonize yes/g" /etc/redis/redis.conf
sudo sed -r -i "s/^supervised no/supervised systemd/g" /etc/redis/redis.conf
# openssl rand 60 | openssl base64 -A
sudo sed -r -i "s/^# requirepass foobared/requirepass Dx7X\$BqCUfVL0\&5OZ/g" /etc/redis/redis.conf
# sudo systemctl restart redis-server
```

+ [How to Install and Configure Redis on Ubuntu 20.04](https://www.linode.com/docs/guides/install-redis-ubuntu/)
+ [4 Ways to Check your Redis Version](https://database.guide/4-ways-to-check-your-redis-version/)