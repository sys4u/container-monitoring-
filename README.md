I refered https://botleg.com/stories/monitoring-docker-swarm-with-cadvisor-influxdb-and-grafana/

first, make docker-compose.yml file. I named it 'docker-stack.yml'

go to docker-stack.yml path, execute this command
```
docker stack deploy -c docker-stack.yml monitor
```
-c is shorten key for --compose-file. 


next, you make influx DB to save data that collect from cadvisor.
```
docker exec `docker ps | grep -i influx | awk '{print $1}'` influx -execute 'CREATE DATABASE cadvisor'
```


if you check docker-stack.yml file, you can know grafana's port is 3000 because I set that 3000. 

you can change grafana's port number. 

second, open http://'docker-machine ip manager'. In our company case, 'xxx.xx.xx.94:3000'

Refer https://botleg.com/stories/monitoring-docker-swarm-with-cadvisor-influxdb-and-grafana/ for grafana setting.

But use dashboard.json file uploaded on sys4u'github.

