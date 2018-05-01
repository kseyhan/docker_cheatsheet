# docker_cheatsheet

### list all installed images
docker images -a

---

### remove container
rm <container_name | ID>

### remove image
rmi <image_name | ID>

---

### drop shell into running container
docker exec -it "container_id" bash

### drop root shell into running container
docker exec -u 0 -it "container_id" bash

---

### show running containers
docker ps

### show settings of a container
docker inspect <container_name | ID>

### show resource usage
docker stats

---

### search official image on docker hub
docker search -f is-official=true <searchterm>

### list configured networks
docker network ls

### connect a running container to a network
docker network connect [OPTIONS] NETWORK CONTAINER

### disconnect a running container from a network
docker network disconnect [OPTIONS] NETWORK CONTAINER

### renaming a container
docker rename CONTAINER NEW_NAME
