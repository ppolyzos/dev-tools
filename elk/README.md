# Elastic Stack (ELK)

Elastic Stack is a group of open source products from Elastic designed to help users take data from any type of source and in any format and search, analyze, and visualize that data in real time.

For more advanced scenarios please visit [deviantony/docker-elk](https://github.com/deviantony/docker-elk) repository.

The stack contains the following projects:

* Elasticsearch: [github](https://github.com/elastic/elasticsearch), [docs](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
* Logstash: [github](https://github.com/elastic/logstash), [docs](https://www.elastic.co/guide/en/logstash/current/index.html)
* Kibana: [github](https://github.com/elastic/kibana), [docs](https://www.elastic.co/guide/en/kibana/current/index.html)

# Requirements

By default, the stack exposes the following ports:
* [5000](http://localhost:5000): Logstash TCP input
* [9200](http://localhost:9200): Elasticsearch HTTP
* [9300](http://localhost:9300): Elasticsearch TCP transport
* [5601](http://localhost:5601): Kibana dashboard
* Default credentials: `elastic` / `changeme`

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the `-d` flag to the above command.

> You must rebuild the stack images with docker-compose build whenever you switch branch or update the version of an already existing stack

* Dashboard available at [http://localhost:5601](http://localhost:5601)
* Default credentials: `elastic` / `changeme`

# Cleanup 

Data is peristed inside a volume by default.

To shutdown the stack **without** removing all persisted data, use the following Docker Compose command:
```
$ docker-compose down
```

In order to entirely shutdown the stack and remove all persisted data, you can add the `-v` flag to the above command:

```
$ docker-compose down -v
```
