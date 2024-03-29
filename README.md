# elastic-stack-sample
This is a sample project to setup Elastic Search and Kibana with SSL communication
## Installation

### Prerequisites
A Centos 7 Server which requires more than 16G memory since we have 2 elastic nodes with 4G memory for each one, anyway you can adjust memory to a lower size. And in this sample, a single harddisk with 1TB size under volumes /data is pointed to Docker default folder as well. 
### Initial ElasticSearch Setting
Refer to https://www.elastic.co/guide/en/elasticsearch/reference/7.3/configuring-tls-docker.html
#### A certification needs to be generated by using create-certs
```bash
$ docker-compose -f create-certs.yml run --rm create_certs
```
> **Note**: Since my docker default folder is /data, so the certs will be generated to /data/volumes/es_certs/ folder
### Start ElasticSearch
```bash
$ cd elastic-search && docker-compose up -d
```
### Start Kibana
```bash
$ cd Kibana && docker-compose up -d
```
### Visit Kibana
Visit https://127.0.0.1:5601 for Kibana
