# headscale-compose-template

this is a docker-commpose template for Headscale [https://github.com/juanfont/headscale]

```
version: '3.5'

services:
  headscale:
    image: headscale/headscale:latest
    container_name: headscale
    command: serve
    restart: unless-stopped
    ports:
      - "1010:8080"   # Maps host port 1010 to container port 8080 (Web API)
      - "7070:9090"   # Maps host port 7070 to container port 9090 (admin/metrics)
    volumes:
      - ./config:/etc/headscale/
      - ./lib:/var/lib/headscale/
      - ./run:/var/run/headscale```
