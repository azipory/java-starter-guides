# OpenShift Starter Workshop Guides [![Build Status](https://travis-ci.org/openshift-labs/starter-guides.svg?branch=master)](https://travis-ci.org/openshift-labs/starter-guides)

Workshop content designed to be used by the [Workshopper tool](https://github.com/osevg/workshopper).

## Using this content

Either use the content directly by pointing at this repository

```
https://raw.githubusercontent.com/openshift-labs/starter-guides/master/
```

## Create a full workshop

You can follow this instructions to create a full workshop site:

```
$ oc new-project guides
$ oc apply -f https://raw.githubusercontent.com/jorgemoralespou/java-starter-guides/master/guides-template.yaml
$ oc new-app guides \
             -p CONSOLE_ADDRESS=master.osevg.openshiftworkshop.com 
             -p ROUTER_ADDRESS=apps.osevg.openshiftworkshop.com
```

NOTE: You will need the following ENV values:

* *CONSOLE_ADDRESS*: Address to the master server's console
* *ROUTER_ADDRESS*: Wildcard DNS used for deployed apps

# Run Guides Locally
```
$ git clone https://github.com/openshift-labs/starter-labs.git
$ cd starter-labs

$ docker run -it --rm -p 8080:8080 -v $(pwd):/app-data \
              -e CONTENT_URL_PREFIX="file:///app-data" \
              -e WORKSHOPS_URLS="file:///app-data/_workshops/java-starter-guide.yml" \
              osevg/workshopper:latest 
```
