# Endpoint Readiness Check Action

Github Action to run docker compose if required and check the readiness of an endpoint of the service that one wants to run integration test against.

# Usage

This is a very simple action which performs readniness check of an endpoint of a sevice that one wishes to run integration test against. The definition of the parameters are defined bewlo

* `readiness-endpoint`: Is the url that we want to check for the health status of the service.
* `timeout`: Is the timeout in seconds of how long to wait for the readiness endpoint to become reacheable. It is optinal if not provided it will default to 40 seconds.
* `docker-compose`: Is a flag if set to true this action will run the docker-compose as part of the readniness check. It is optional, if not set it will default to false

```
  - name: Check the readiness of the endpoint
    uses: akhettar/readiness-check@master
    with:
      readiness-endpoint: 'http://localhost:8080/v1' 
      timeout: '2' 
      docker-compose: 'true'
```        
