# docker-api-proxy

Proxy for accessing Docker daemon's remote API. By default, the API proxy blocks all requests that can run containers and commands that are not covered by the stored images and their predefined commands. However, you can easily customize the filter logic by adapting the lib/filter.js file.

Tested against Docker Remote API v1.24 and Docker 1.12.

## Start a container

    $ docker run -d --name docker-api-proxy -P -v /var/run/docker.sock:/docker.sock asannou/docker-api-proxy

## Connect to it using Docker CLI

    $ docker -H $(docker port docker-api-proxy 2375/tcp) info

