FROM openjdk:8-jre

WORKDIR "/"
RUN wget https://artifacts.elastic.co/downloads/kibana/kibana-5.0.0-linux-x86_64.tar.gz \
	&& tar xvfz kibana-5.0.0-linux-x86_64.tar.gz \
	&& mv kibana-5.0.0-linux-x86_64 kibana 
	
WORKDIR "/kibana"

EXPOSE 5601
CMD ["bin/kibana"]
