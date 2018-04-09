# SKOPE Deployments

SKOPE is a basic microservice architecture with with each service running
within container. At the center of the backend services is Clowder, a Data 
Management System (DMS) designed to manage large collections of scientific
data. Clowder can be extended using addition microservices known as extractors.
Like many microservice system, Clowder depends on RabbitMQ to handle
notifications of new data sets, file uploads, or metadata changes.

![SKOPE Architecture](docs/skope_architecture.png?raw=true "SKOPE Architecture")

## Deploying SKOPE

The SKOPE is deployed as a stack of services from a docker-compose.yml file.
Deployment with docker-compose.yml allows for easy transition from 
development to staging to production. 

The basic system changes required to deploy SKOPE locally are minimal
and shown below. Installation and deployment using existing SKOPE data
comes down to the following 3 steps:

1. prep the local system
1. copy data from the existing SKOPE system
1. start the SKOPE services

For detailed instructions for preparing a new server to run SKOPE and 
getting existing data, see the instructions in the 
[SKOPE server config](https://github.com/openskope/server-config).

### Starting SKOPE

This section is from the skope-deployment repository but repeated here
for convenience. See the skope-deployment instructions for the most recent
changes.

1. clone the GitHub repository
1. change to staging branch
1. use docker-compose to run start services

```
$ git clone https://github.com/openskope/skope-deployment.git
...
$ cd skope-deployment
$ git checkout staging
...
$ sudo docker-compose up -d
...
```
