# automation-webservice

Greeting webservice used for my automation tests. To run the container, use something like:

> `docker run -i -t --rm --name=GreetingService dangermike64/automation-webservice`

You must give the container a name to expose the IP address to other containers. 

To test that the container is running, assuming you are on the same machine as the conatiner, open a web browser and nvaigate to:

> `http://localhost:3000`

To get a JSON response, hit the greeting endpoint:

> `http://localhost:3000/hello/world`

You can link this container to other containers. e.g.:

> `docker run -i -t --rm --link=GreetingService:GreetingEndpoint dangermike64/automation-webserver-tests gradle test`

here we link to the name given to the greeting container (GreetingServer). GreetingEndpoint is host name add to the `dangermike64/automation-webserver-tests` containers etc/host file. (In this example, the container uses that endpoint to test the web service.)


