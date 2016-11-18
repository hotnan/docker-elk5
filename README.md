# docker-elk5
for testing elk5 quickly with docker

##Require:
- docker : https://docs.docker.com/engine/installation/
- docker-compose : can be installed following this link: https://docs.docker.com/compose/install/

##To use it:

- Clone this repo
- Prepare your configuration by editing "logstash/config/logstash.conf" file and add files, filters or whatever you want
- run: 
```
[sudo] docker-compose build && [sudo] docker-compose up
```
- send your logs on the "logstash/incoming_logs/" directory
- open your browser and point it to "http://localhost:5601/" **(user: elastic, password: changeme)** to visualize your data and build horrible dashboards

##Cleaning commands (if you want to restart all from the beginning):
- run: 
```
[sudo] docker rm -f dockerelk5_kibana_1 dockerelk5_elasticsearch_1 dockerelk5_logstash_1 && [sudo] rm -rf logstash/incoming_logs/* elasticsearch/data/* elasticsearch/logs/* 
```

##Troubleshooting:
- In dev machines, you may have this error message from elaticsearch:

```
elasticsearch_1  | ERROR: bootstrap checks failed
elasticsearch_1  | max virtual memory areas vm.max_map_count [65530] likely too low, increase to at least [262144]
[...]
dockerelk5_elasticsearch_1 exited with code 78
```


On your real host, just launch the following commadn to fix it:

```
sudo sysctl -w vm.max_map_count=262144
```

