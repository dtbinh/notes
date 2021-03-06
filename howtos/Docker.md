## Docker Usage 
### Personal Docker commands
*This section captures frequently used commands by me for quick reference*
* Run ubuntu container, execute bash on it 
```sh
docker run --name <name> -it -d ubuntu 
docker exec -it <container_id> bash
```
* Commit container to new image and save to docker hub
```sh
docker commit <container-name> [image-name[:tag]]
```
* Push image to dockerhub
```sh
docker login
docker push imagename[:tag]
```
if push fails with error message - *denied: requested access to the resource is denied*, the rename the repo first using command
```sh
docker tag <image_name> ankdesh/<image_name>
```


### Generic Docker commands 
*This section captures frequently used generic docker commands*
* Create container, run image (If image not available, it downloads from docker hub). -it makes it interactive and -d (stands for detached) makes the container stand running.
```sh
docker run -it -d <image_name>
```
* Execute interactive bash on detached container
```sh
docker exec -it <container_id> bash
```
* Stop container 
```sh
docker <container_id> stop
```
* Commit changes to a new Docker image 
```sh
docker commit <container_id> <username>/<new imagename>
```
* Delete a Docker container
```sh
docker rm <container-id>
```
* Delete all Docker containers
```sh
docker rm $(docker ps -aq)
```
* Delete an image (make sure all the related containers are deleted using above commands)
```sh
docker rmi <image-name>
```
* Create an image from Dockerfile
```sh
docker build -t <image-name> [-f dockerfileName] <folder containing Dockerfile and other to be packed files>
```
