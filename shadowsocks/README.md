通过Dockerfile生成镜像:
docker build -t hub.docker.com/shadowsocks:1.0 .
运行镜像：
sudo docker run -d -p 1080:1080 --env-file env hub.docker.com/shadowsocks:1.0
