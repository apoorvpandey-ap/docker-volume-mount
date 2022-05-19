# docker-volume-mount

### Step:1 Pull image from docker hub
`docker pull jenkins:2.46.3-alpine`

### Step: 2 make directory 
```
cd /var/
mkdir jenkins_alpine
```
### Step: 3 run the container 
`docker run  [detached mode ] [port] [-name of image] [volume] [path/of/host]:[/path/in/container] [image name/id]
`
**example** 
`docker run -d -p 9090:8080   --name jenkins-storage-alpine   --volume /var/jenkins_alphine:/var/jenkins_home jenkins:2.46.3-alpine
`

### Step: 4 Make a job on jenkins 
job name - docker_contianer_delete 

### Step:5 Check the file on host 
`cd /var/docker_contianer_delete`

### Step: 6  Delete the container  
`docker rm -f [container_name]`

### Step: 7 Attache host-volume again to the container 
`docker run -d -p 9090:8080   --name jenkins-storage-alpine   --volume /var/jenkins_alphine:/var/jenkins_home jenkins:2.46.3-alpine
`


### Step: 8 Check the file inside the docker container
`docker exec -it [container-id] bash
`
```
cd  /var/jenkins_home /
ls
docker_contianer_delete

```


