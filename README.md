# chefapi_chef_server

This cookbook is part of the code used for a demonstration of some uses
for the Chef Infra Server API.  Its intended use is to create a Chef server
and populate it with organizations, users and nodes. It also adds additional
services to run the chefapi demo. These services would usually be packaged to
run in separate containers.  They were combined with the Chef server for the
purposes of the Chef Conf demo.

Services
========

|Service | Purpose |
|--------|---------|
|chefapi-login| Check credentials and create a JSON Web Token to identify and user|
|chefapi-organizations| REST API to list Chef Organizations|
|chefapi-node-auth| REST API to check user authorizations |
|chefapi-nodes| REST API to list and edit nodes |
|chefapi-users| REST API to list and manage users|

Use
===

Configuration Checklist
* Get the go repositories
* Set up a code directory
* Get this repository, chefapi_chef_server
* Use test kitchen to build a Chef Server Instance using the chefapi_chef_server cookbook
* Set up the demonstration web site.  Nginx config, html, javascript, and css files are in the chefapi_web repository.

A prerequisite for running this cookbook and starting services is access to the
other git repositories that are part of the chefapi demonstration.  On the author's
development box, where the demonstration ran, this was the configuration.

**In directory /dev/mine these repositories were cloned.**
* https://github/MarkGibbons/chefapi_chef_server
* https://github/MarkGibbons/chefapi_web

**These repositories were fetched using go get.**
* github.com/MarkGibbons/chefapi_client
* github.com/MarkGibbons/chefapi_client_nodes
* github.com/MarkGibbons/chefapi_client_organizations
* github.com/MarkGibbons/chefapi_node_auth
* github.com/MarkGibbons/chefapi_lib
* github.com/MarkGibbons/chefapi_login
* github.com/MarkGibbons/chefapi_client_users
* github.com/MarkGibbons/chefapi_test_setup
* github.com/go-chef/chef

**These symbolic links were created in /dev/mine to point to the go modules.**
The links are used by test kitchen to mount the go modules inside the Chef Server
instance in order to run the extra services

* chefapi_client
* chefapi_client_nodes
* chefapi_client_organizations
* chefapi_node_auth
* chefapi_lib
* chefapi_login
* chefapi_client_users
* chefapi_test_setup
* go-chef/chef

**Web site configuration**
The github/MarkGibbons/chefapi_web repository contains the web pages and nginx
configuration used for the demonstration.  The web site is not managed by a cookbook.
For the demo the website was served by nginx running on the development server.
Most of the pieces will be available in habitat packages in a few weeks.
