本组镜像实现对交换机端口带宽实时展示，使用了snmp-exporter、prometheus、grafana<br>
如何不使用docker-compose，三个容器的启动命令参考下面<br>
snmp-exporter:<br>
sudo docker run --name snmp-exporter --detach --restart always -v /opt/swmonconfig/snmp-exporter:/config  -p 9116:9116 oakman/snmp-exporter<br>
prometheus:<br>
sudo docker run -p 9090:9090 --detach -v /opt/swmonconfig/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml rycus86/prometheus<br>
grafana:<br>
sudo docker run -d -v /var/lib/grafana --name grafana-storage busybox:latest<br>
sudo docker run -d -p 3000:3000 --name=grafana --volumes-from grafana-storage grafana/grafana<br>

启动容器后，可以通过hostip:3000对grafana进行配置，便可以访问监控数据<br>
备注：grafana的graph模板为文件snmp-interface-throughput_rev4.json，根据需要对它的metrics进行修改<br>
链接：https://grafana.com/plugins/prometheus<br>
