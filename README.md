# docker-tips-and-tricks
Just a compendium of docker commands and various tricks needed in day-to-day docker, and kubernetes work. 

## Basic Command Examples
Launching and attaching

```
docker run -dit [image]
docker exec -it [image-id-or-name] bash
docker run -dit -p 8080:8080 apache2-test
```

## Docker Cleanup
```
docker container prune
docker system prune
```
