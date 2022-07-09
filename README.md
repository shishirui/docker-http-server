# docker-http-server

### 1. 构建自定义镜像

    docker build ./php -t meeting/php:8.1-fpm

### 2. 启动服务

    docker compose up -d
    
### 自定义

1. 如果需要修改 php 镜像中的内容（例如增减扩展等），修改 `php/Dockerfile` 文件
1. 如果要修改程序目录、端口、增减服务等，修改 `docker-compose.yml` 即可
1. nginx 的配置文件在 `etc/nginx/default.conf`
1. php 的配置文件在 `etc/php/php.ini`
1. 如果想启动多个 php 容器来提升性能，可以：`docker compose up -d --scale php=3`
