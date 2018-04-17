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

## Docker Security / Privileges
You can specify the user to run-as when launching docker
```
docker exec -it --user root {image} sh
docker exec -it --user 1000 {image} bash
```
To run the container in privileged mode (to say enable mounting):
```
docker run -dit --privileged {image} bash
```


