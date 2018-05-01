# docker_cheatsheet

### list all installed images
docker images -a

### remove container
rm <container_name | ID>

### remove image
rmi <image_name | ID>

### drop shell into running container
docker exec -it "container_id" bash

### show running containers
docker ps

### show settings of a container
docker inspect <container_name | ID>

### show resource usage
docker stats
