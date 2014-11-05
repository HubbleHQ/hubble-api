spacious-api
============

Documentation for the Spacious API

## Access
API access is available to partners who have been issued with an API key. If you are interested in gaining access to our API, please email team [at] spaciousapp.com with details of your application.

## General
*	all endpoints are accessible at `http://host.spaciousapp.com/api/v1`
*	all calls should include your api key as a query parameter in the url. e.g.
	```
	http://host.spaciousapp.com/api/v1/space-list/?api_key=abcdefghijklmnopqrstuvwxyz
	```

## Endpoints
* `GET` [space-list](./endpoints/space-list.md)
