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
## Docker Security / Privileges
You can specify the user to run-as when launching docker
```
docker exec -it --user root [image] sh
docker exec -it --user 1000 [image] bash
```
To run the container in privileged mode (to say enable mounting):
```
docker run -dit --privileged [image] bash
```
## Dockerfile Items
### CMD versus ENTRYPOINT
An ENTRYPOINT specifies a command what will ALWAYS run when the container starts. 
The CMD basically provides an optional command passed to the 'entry point', but can be overridden. 
```
FROM ubuntu:16.04
ENTRYPOINT ["/bin/ping"]
CMD ["localhost"]
```
A docker run on the above without parameters will ping the localhost. However, you can also pass in another hostname and it will overlay localhost. 
```
FROM ubuntu:16.04
CMD ["/bin/ping", "localhost"]
```
This will do the same as above, but you can overide the whole CMD with, say bash with:
```
$docker run -it image bash
```
## Docker Cleanup
```
docker container prune
docker system prune
```



