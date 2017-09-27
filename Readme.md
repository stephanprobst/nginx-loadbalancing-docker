The web container image uses docker multistage build with ASP.<span>NET Core.<br>
So ASP.<span>NET Core setup is not necessary for this sample.

Build the web container image:

```
docker build web -t web
```

To deploy containers to swarm:
```
docker stack deploy -c docker-compose.yml lb
```

URLs to test the different loadbalancing modes:
```
http://localhost/roundrobin
http://localhost/leastconn
http://localhost/iphash
http://localhost/weighted
```