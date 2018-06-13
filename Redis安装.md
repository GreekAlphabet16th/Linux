- 下载Redis安装包 
```
https://redis.io/download
tar zxvf redis-3.2.1.tar.gz  -C /home/redis/
cd redis-3.2.1
make
make install
```
>  注意：编译redis时 提示make cc Command not found
>  安装gcc环境 yum install gcc

- redis.conf 配置
- 修改前
```
daemonize no
bind 127.0.0.1
protected-mode yes
#requirepass foobared 
```
- 修改后
```
#守护进程
daemonize yes
#外网通信连接
#bind 127.0.0.1
protected-mode no
#初始化密码配置
requirepass 123.com
```
- 启动服务
```
cd redis-3.2.1/src
./redis-server /home/redis/redis-3.2.1/redis.conf
```
- 查看进程

```
ps -ef|grep redis
```

- 启动客户端
```
redis-cli -p 6379
```
- 修改密码

```
config set requirepass 123.com
```


