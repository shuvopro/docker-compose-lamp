# Docker Commands


### Boot up the containers
`sudo docker-compose up -d`


### Stop the containers
`sudo docker-compose down`

#### Remove all exited containers 
`sudo docker rm $(docker ps -a -q -f status=exited)`
`sudo docker container prune`


#### Remove a single or multiple containers
`sudo docker rm 305297d7a235 ff0a5c3750b9`
305297d7a235 = container id


#### Get all containers list
`sudo docker ps -a`


#### Get interactive TTY terminal of an image
`sudo docker run -it busybox sh`
busybox = image name
To exit the container (type exit and press Enter)



#### Download and Run a image and remove the container once exited 
`sudo docker run --rm prakhar1989/static-site`
prakhar1989/static-site = image name
--rm = remove the container once exited


#### Run a image with detach mode, export port and add a name
`sudo docker run -d -P --name static-site prakhar1989/static-site`
-d = detach terminal
-P = export port randomly
--name = give a container name
static-site = container name
prakhar1989/static-site = image name


#### Get exported port list by a container
`sudo docker port static-site`
static-site = container name


#### Assign a port number for exported container port
`sudo docker run -p 8888:80 prakhar1989/static-site`
-p = export port by assigned number
8888 = exported port
80 = docker port


#### Stop a container by container name
`sudo docker stop static-site`
static-site = container name


#### Get list of images
`sudo docker images`


#### Build a docker image from Dockerfile
`sudo docker build -t shuvo575/catnip .`
shuvo575/catnip = image name
( . ) = Dot is mandatory here

 
#### Run the image we build
`sudo docker run -p 8888:5000 shuvo575/catnip`


#### Run command in running container
`sudo docker exec -it lamp-php8 /bin/bash`
lamp-php8 = container name
/bin/bash = open terminal
-it = give us interactive TTY
exec = execute command


