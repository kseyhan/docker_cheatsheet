# Docker Cheatsheet

### list all installed images
```
docker images -a
```

### list all installed containers
```
docker container ls -a
```

---

### remove container
```
docker rm <container_name | ID>
```

### remove image
```
docker rmi <image_name | ID>
```

---

### drop shell into running container
```
docker exec -it "container_id" bash
```

### drop root shell into running container
```
docker exec -u 0 -it "container_id" bash
```

---

### show running containers
```
docker ps
```

### show settings of a container
```
docker inspect <container_name | ID>
```

### show resource usage
```
docker stats
```

---

### list configured networks
```
docker network ls
```

### connect a running container to a network
```
docker network connect [OPTIONS] NETWORK CONTAINER
```

### disconnect a running container from a network
```
docker network disconnect [OPTIONS] NETWORK CONTAINER
```

---

### search official image on docker hub
```
docker search -f is-official=true <searchterm>
```
  
### renaming a container
```
docker rename CONTAINER NEW_NAME
```

### container Logs
```
docker logs <container_name | ID>
```

---

### CPU Constraints
You can limit CPU, either using a percentage of all CPUs, or by using specific cores.

For example, you can tell the cpu-shares setting. The setting is a bit strange -- 1024 means 100% of the CPU, so if you want the container to take 50% of all CPU cores, you should specify 512. See https://goldmann.pl/blog/2014/09/11/resource-management-in-docker/#_cpu for more:
```
docker run -ti --c 512 agileek/cpuset-test
```
You can also only use some CPU cores using cpuset-cpus. See https://agileek.github.io/docker/2014/08/06/docker-cpuset/ for details and some nice videos:

```
docker run -ti --cpuset-cpus=0,4,6 agileek/cpuset-test
```
Note that Docker can still see all of the CPUs inside the container -- it just isn't using all of them. See https://github.com/docker/docker/issues/20770 for more details.

### Memory Constraints
You can also set memory constraints on Docker:

```
docker run -it -m 300M ubuntu:14.04 /bin/bash
```
