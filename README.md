# chefapi_chef_server

Create a Chef Infra tserver and populate it with organizations, users and nodes.
Add additional services to run the chefapi demo. These services would
be packaged to run in separate containers.  They were combined with
the chef server for the purposes of the Chef Conf demo. 

Services
========

|Service | Purpose |
|--------|---------|
|chefapi-login| Check credentials and create a JSON Web Token to identify and user|
|chefapi-organizations| REST API to list Chef Organizations|
|chefapi-node-auth| REST API to check user authorizations |
|chefapi-nodes| REST API to list and edit nodes |
|chefapi-users| REST API to list and manage users|
