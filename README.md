Deploying Django App on Docker Container

Reference sites :- 

https://medium.com/@Alibaba_Cloud/how-to-deploy-a-django-application-with-docker-9514be542909

https://dev.to/joekreydt/deploy-django-in-a-docker-container--41n6

Introduction to Docker :- 

Docker is a technology that makes it easier to create, deploy, and run applications by using containers. Containers allow developers to package applications with all the components required by the applications and later ship them out as packages. It also makes it possible to get more apps running on the same server.

Inatallation of Docker on ubuntu follow the following commands:-

    • sudo apt update
    • sudo apt install apt-transport-https ca-certificates curl software-properties-common
    • curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    • sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable
    • sudo apt update
    • sudo apt install docker-ce

Check Docker Status :-

    • sudo systemctl status docker

Check the Docker version by typing :-

    • docker -v

Start and Stop Docker :-

    • sudo syatemctl start docker
    • sudo syatemctl stop docker

Image and container :-

A Docker image is made up of a series of filesystem layers representing instructions in the image’s Dockerfile that makes up an executable software application	




Docker Containers:-

An instance of an image is called a container. A container represents a runtime for a single application, process, or service.
It may not be the most appropriate comparison but if you are a programmer you can think of a Docker image as class and Docker container as an instance of a class.
We can start, stop, remove and manage a container with the docker container subcommand
	
