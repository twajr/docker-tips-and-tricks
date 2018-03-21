# docker-tips-and-tricks
Just a compendium of docker commands and various tricks needed in day-to-day docker, and kubernetes work. 

## Basic Command Examples
Launching and attaching

```
docker run -dit [image]
docker exec -it [image-id-or-name] [command]
docker run -dit -p 8080:8080 --name apache apache2-test
docker exec -it apache bash
```

## Docker Cleanup
```
docker container prune
docker system prune
```
