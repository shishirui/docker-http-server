# docker-http-server

使用 docker 安装的 http server，包含：

1. php 8.1
2. nginx
3. redis
4. phpmyadmin
5. composer

### 1. 构建自定义镜像

    docker build ./php -t meeting/php:8.1-fpm

### 2. 启动服务

    docker compose up -d
    
### 自定义

1. 如果需要修改 php 镜像中的内容（例如增减扩展等），修改 `php/Dockerfile` 文件接口，默认包含了 mysql, imagick, gd 扩展
2. 如果要修改程序目录、端口、增减服务等，修改 `docker-compose.yml` 即可
3. nginx 的配置文件在 `etc/nginx/default.conf`
4. php 的配置文件在 `etc/php/php.ini`
5. 如果想启动多个 php 容器来提升性能，可以：`docker compose up -d --scale php=3`
