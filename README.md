# headscale-compose-template

this is a docker-commpose template for Headscale [https://github.com/juanfont/headscale]

```
version: '3.5'

services:
  headscale:
    image: headscale/headscale:latest
    container_name: headscale
    command: serve
    restart: unless-stopped # only put this here if you want it to stay on after your computer restarts
    ports:
      - "[port number]:8080"   # the port you want to use for the Web API
      - "[different port number]:9090"   # the port you want to use for admin/metrics
    volumes:
      - ./config:/etc/headscale/
      - ./lib:/var/lib/headscale/
      - ./run:/var/run/headscale
