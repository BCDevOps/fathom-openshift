# Fathom
This is a set of OpenShift configurations to set up an instance of the Fathom web analytics server. See: usefathom.com

## Architecture
The service is composed by the following components:
- *fathom*: this is the main analytics service.
- *fathom-db*: a [postgresql](https://www.postgresql.org) instance that will beused to store the analytics data.
- *fathom-proxy*: the [nginx](https://www.nginx.com) service used as reverse-proxy

## Deployment / Configuration
The templates provided in the `openshift` folder include everything that is necessary to create the required builds and deployments.

Since there are interdependencies between deployment configurations, please make sure to follow this order when creating them for the first time:
1) build and deploy the database
2) build and deploy the Fathom analytics server
3) build and deploy the proxy