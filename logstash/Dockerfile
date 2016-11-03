FROM openjdk:8-jre

RUN wget https://artifacts.elastic.co/downloads/logstash/logstash-5.0.0.tar.gz \
	&& tar xvfz logstash-5.0.0.tar.gz \
	&& mv logstash-5.0.0 /logstash

WORKDIR /logstash

RUN mkdir incoming_logs 
VOLUME /logstash/incoming_logs

CMD ["bin/logstash", "-f", "/logstash/config/logstash.conf"]
