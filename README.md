# Fig ELK Stack

Run a local ELK (Elasticseach, Logstash, Kibana) stack with Fig and Docker.

This aims to give you the ability to quickly test your logstash filters and how the data can be processed in Kibana.

Based on 3 Docker images:

* [elk-elasticsearch](https://github.com/deviantony/docker-elk-elasticsearch)
* [elk-logstash](https://github.com/deviantony/docker-elk-logstash)
* [elk-kibana](https://github.com/deviantony/docker-elk-kibana)

## Installation and use
1. Install [Docker](http://docker.io).
2. Install [Fig](http://fig.sh).
3. Clone this repository
4. Update the logstash-configuration in logstash-conf/logstash.conf
5. fig up
6. nc localhost 5000 < /some/log/file.log
7. http://localhost:8080 to see the messages show up in Kibana.

This will create 3 Docker containers with Elasticsearch, Kibana, and Logstash running in them and connected to each other. Three ports are exposed for access:
* 5000: Logstash TCP input.
* 9200: Elasticsearch HTTP (With Marvel plugin accessible via [http://localhost:9200/_plugin/marvel](http://localhost:9200/_plugin/marvel))
* 8080: Kibana web interface.