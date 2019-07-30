# Pact Stub Server

Run a Stub Server from one or more local or remote Pact files.

Handy for automating external API dependencies of a project.

Docker image: https://hub.docker.com/r/pactfoundation/pact-stub-server/

# Running 

See https://github.com/uglyog/pact-stub-server for the available CLI options.

# Example


```sh
# Create a Stub API
docker pull zescher/pact-stub-server
docker run -t -p 8080:8080 -v "$(pwd)/pacts/:/app/pacts" zescher/pact-stub-server -p 8080 -d pacts

# Test your stub endpoints
curl -v $(docker-machine ip $(docker-machine active)):8080/bazbat
curl -v $(docker-machine ip $(docker-machine active)):8080/foobar
```

