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

The scripts in [openshift-developer-tools](https://github.com/BCDevOps/openshift-developer-tools) can be used to manage the builds and deployments.

## First Run
Once everything is up and running in OpenShift, follow the [instructions](https://github.com/usefathom/fathom/blob/master/docs/Installation%20instructions.md#register-your-admin-user) and create your admin user to secure the analytics dashboard.