通过Dockerfile生成镜像:<br>
docker build -t hub.docker.com/shadowsocks:1.0 .<br>
运行镜像：<br>
sudo docker run -d -p 1080:1080 --env-file env hub.docker.com/shadowsocks:1.0<br>
