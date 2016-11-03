# docker-elk5
for testing elk5 quickly with docker

To use it:

- Clone this repo
- Prepare your configuration by editing "logstash/config/logstash.conf" file and add files, filters or whatever you want
- run: "[sudo] docker-compose build && [sudo] docker-compose up"
- send your logs on the "logstash/incoming_logs/" directory
- open your browser and point it to "http://localhost:5601/" to visualize your data and build horrible dashboards

Cleaning commands (if you want to restart all from the beginning):
- run: [sudo] docker rm -f elk5_kibana_1 elk5_elasticsearch_1 elk5_logstash_1 && [sudo] rm -rf logstash/incoming_logs/* elasticsearch/data/* elasticsearch/logs/* 
