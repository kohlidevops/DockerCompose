# Docker Compose

## Role of Docker Compose

![image](https://github.com/user-attachments/assets/5e4c5b4f-56f0-4d75-ae4b-655f447a43d2)

## Communication between Containers

![image](https://github.com/user-attachments/assets/1afa4ee7-a8e8-49d1-a6ed-b09240f216c3)

## Docker Service Containers

![image](https://github.com/user-attachments/assets/b7b6e585-7b47-49fa-9366-1ac962a42b77)

➢ Manage the whole Application Lifecycle.

○ Start, Stop and Rebuild Services.

○ View the Status of Running Services.

○ Stream the Log output of Running Services.

○ Run a one-off command on a service.

## Docker Compose Workflow

![image](https://github.com/user-attachments/assets/04645571-34da-42d0-9f0f-df5d148d7ba4)

## What is Docker Compose?

➢ Docker Compose is a tool for defining and running multi-container Docker applications.

➢ It allows you to define an entire application stack, including services, networks, and volumes, in a single file called ‘docker-compose.yml’.

**key concepts and components of a Docker Compose file**

➢ Version : The version of the Docker Compose file syntax. This version indicates which features and syntax are supported.

➢ Services : This section defines the various containers (services) that make up your application. Each service has a name, and under each service, you can configure parameters such as the Docker image to use, environment variables, ports to expose, volumes to mount, and more

![image](https://github.com/user-attachments/assets/213c2e65-c95f-41c3-9c79-9ee2fb7286a7)

➢ Volumes : This section allows you to define named volumes or bind mounts for your services. Volumes are used to persist data between container restarts.

![image](https://github.com/user-attachments/assets/e673f413-ce56-4065-a0be-3c77c39caeac)

➢ Networks : This section lets you define custom networks and connect services to them. This is useful for controlling communication between services.

![image](https://github.com/user-attachments/assets/ebb9bd43-25ca-460d-b877-b42b0de01801)

➢ Environment Variables : You can set environment variables for your services using the ‘environment’ key. This is useful for configuring your applications dynamically.

![image](https://github.com/user-attachments/assets/6fa81da0-9cc1-4175-a788-cee9e1d00772)

➢ Ports : This key allows you to map ports from the host to the container. This is essential for accessing services from outside the Docker environment.

![image](https://github.com/user-attachments/assets/bf613658-5983-42f1-b113-a235a9478ab0)

➢ Command : This key lets you override the default command for the container. This is useful when you need to specify how the container should start.

![image](https://github.com/user-attachments/assets/628204e6-99b8-4bdc-8c59-37bbfdd0dd24)

## Build Images with Docker Compose

➢ Normal Flow

Docker file → Docker Build Command → Docker Image

➢ Build Image in Docker Compose Workflow

```
docker-compose build
docker compose build
```

## Docker Compose Build Properties

➢ build/context : It defines either a path to a directory containing a Dockerfile, or a URL to a git repository.

![image](https://github.com/user-attachments/assets/65f6e2c4-d33a-4449-ac75-bf7194546b54)

➢ Image : Overrides the image name specified in the Dockerfile.

![image](https://github.com/user-attachments/assets/54161a16-fda1-481d-8bfb-4ac60ce49a28)

➢ dockerfile : Specifies an alternative Dockerfile for the build.

![image](https://github.com/user-attachments/assets/c27c7d4c-4fbf-4e94-ae38-a0d7e780e2e3)

➢ args : Passes build arguments to the build context. Useful for dynamically setting values during the build.

![image](https://github.com/user-attachments/assets/1c04f680-a738-43e1-acc3-eefbb0613c29)

➢ tags : This defines a list of tag mappings that must be associated to the build image.

![image](https://github.com/user-attachments/assets/226c2f1f-5ba0-43c4-b0f4-3773907f739e)

## Docker Compose Demo

### Install docker compose

```
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

**Clone the repo into your docker daemon host machine**

```
https://github.com/kohlidevops/DockerComposeFiles.git
cd DockerComposeFiles
```

**To build the docker images using Docker Compose**

```
docker-compose build

//If you are facing any issues with above command do below things
docker system prune
docker-compose build --no-cache
```

![image](https://github.com/user-attachments/assets/35cf6198-52b1-4f93-84c6-f2b34a0887bd)

**To check the docker images**

```
docker images
```

![image](https://github.com/user-attachments/assets/662cb60b-dc59-41a2-a66b-a56dd54dd1b4)

You can rename the docker image version and re-run the docker-compose command

```
//Docker-compose yaml file
image: anshuldevops/python_web:2.2
```

**To run the docker container using Docker Compose**

```
docker-compose up
```

![image](https://github.com/user-attachments/assets/8431e9ae-bd0d-496d-9b6b-6bbdcc328d07)

**To check the container**

```
docker ps -a
```

![image](https://github.com/user-attachments/assets/ceb41516-214c-4760-abe2-55cbf259b497)


## Deploy a Wordpress and MySQL using Docker compose

```
https://github.com/anshulc55/Docker_for_DevOps/blob/master/docker_compose_wordpress_mysql/docker-compose.yml
docker-compose up -d
dockes ps
```

![image](https://github.com/user-attachments/assets/77278eaf-24ab-4dd3-933a-4750b2f306ec)
