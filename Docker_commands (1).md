# To Install docker
- yum install docker -y

# to start the docker services
- systemctl start docker
- systemctl enable docker

# to Pull the images from Docker hub 
- docker pull "imagename"

# to see the docker images
- docker images

# to see the docker container running 
- docker ps

# to see all the container running and other stopped container 
- docker ps -a 

# to run the docker images
- docker run "imagename"

# to start the conatainer
- docker start  "container_id"


# to stop the conatainer
- docker stop "container_id"

# to remove the conatainer
- docker rm "container_id"

# To run the Httpd docker image, if we run without the portno, this will  not work  sine the HTTPD is also running on the port 80

docker run -d -p 80:80 httpd

# To run the tomcat with  docker image -d to riun in detached mode
docker run -d --name mytomcat3 -p 8081:8080 tomcat

# To run the ubuntu docker images, this will enter the ubuntu machine
docker run -it ubuntu

# To run the container in the interactive mode (to Enter inside th e container)
docker exec -it "container_id" /bin/bash

# Start the container with the --restart flag, specifying the desired restart policy. There are several restart policies available, including no, on-failure, unless-stopped, and always. 
# In this  case, unless-stopped or always would be appropriate

docker run --restart unless-stopped <your-container-options>

**To Build Docker Image**
docker build -t tomcat_helloworld_project .    (Where dot represents Present folder, tomcat_helloworld_project represents project name, docker bulid -t represents command to build docker file)

**To Push Docker Images to Docker Hub**
docker login -u "userid" -p "password"
docker tag tomcat_helloworld_project manjunathr03/tomcat_helloworld_project  (Where tomcat_helloworld_project is a name of docker image & manjunathr03 is a user id of docker hub)
docker push manjunathr03/tomcat_helloworld_project

