# Deploying Reliable Software
A CSCD94 - Computer Science Project with Professor [Thierry Sans](https://github.com/thierrysans).

## Introduction
[Our website](https://deployingreliable.software)

An extension to the existing “Programming on the Web” course at the University of Toronto Scarborough. This research project aims to follow the two books by Google, Site Reliability Engineering and Site Reliability Workbook. There are two main objectives:
- What is the Google way of deploying software used by millions of people?
- How to maintain high availability while allowing for frequent software updates?

## Development Setup
Prerequisites: Docker and Docker Compose installed in your system.

1. To start all servers in development mode, simply run
```
$ docker-compose up -d
```

## Production
- We use ansible scripts to push applications to our production servers hosted on Google Cloud. See `ansible/README.md`.

## Technologies
We try to use a range of technologies in this demo. Here are the list of technologies used at some time in this project.

### Deployment
- [Github Packages](https://github.com/features/packages): Docker image repository
- [Github Actions](https://github.com/features/actions): Continuous integration and Deployment
- [Ansible](https://www.ansible.com/): Playbooks to automate deployment
- [Docker Swarm](https://docs.docker.com/engine/swarm/): Docker across many hosts

### Application Stack
- [Ruby](https://rubyonrails.org/) on Rails: Backend server REST framework
- [Angular 8](https://angular.io/): Frontend framework
- [nginx](https://www.nginx.com/): Reverse proxying for applications

### Packaging applications
- [Docker](https://www.docker.com/): Deploy applications cross-platform in a standardized environment

### Monitoring Stack
#### Prometheus-based
- [Grafana](https://grafana.com/): Dashboard to show statistics and alert if thresholds are exceeded.
- [Prometheus](https://prometheus.io/): A time series database to store data.
- [node_exporter](https://github.com/prometheus/node_exporter): A companion for Prometheus to export server statistics.

#### Elasticsearch-based
- [Kibana](https://www.elastic.co/kibana): Dashboard to visualize data from Elasticsearch
- [Elasticsearch](https://www.elastic.co/elasticsearch): Full text search engine to store log data
- [Elastic APM](https://www.elastic.co/apm): Application performance monitoring server (\*uses elastic-apm agent in Rails application)

#### Others
- [Sentry](https://sentry.io/): An external service to track application errors.
