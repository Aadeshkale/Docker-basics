Deploying Django App on Docker Container

Reference sites :- 

https://medium.com/@Alibaba_Cloud/how-to-deploy-a-django-application-with-docker-9514be542909

https://dev.to/joekreydt/deploy-django-in-a-docker-container--41n6

Introduction to Docker :- 

Docker is a technology that makes it easier to create, deploy, and run applications by using containers. Containers allow developers to package applications with all the components required by the applications and later ship them out as packages. It also makes it possible to get more apps running on the same server.

Installation of Docker on ubuntu follow the following commands:-

https://linuxize.com/post/how-to-install-and-use-docker-on-ubuntu-18-04/


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

Docker Image :-

A Docker image is made up of a series of filesystem layers representing instructions in the image’s Dockerfile that makes up an executable software application	

A Docker image is Template for creation for Dockers	


Docker Containers:-

An instance of an image is called a container. A container represents a runtime for a single application, process, or service.
It may not be the most appropriate comparison but if you are a programmer you can think of a Docker image as class and Docker container as an instance of a class.
We can start, stop, remove and manage a container with the docker container subcommand
**note :- To Understand Docker Image and Container Let Docker Image is class and Docker Container is runtime Inatanse of that class


Create Docker Image using Docker File :-

    • sudo nano Dockerfile

Add this to your Dockerfile :-

FROM python:3.6

MAINTAINER your_name

ADD . /usr/src/app

WORKDIR /usr/src/app

COPY requirements.txt ./

RUN pip3 install --no-cache-dir -r requirements.txt

EXPOSE 80

CMD exec gunicorn your_site_name.wsgi:application --bind 0.0.0.0:80 --workers 3

Description :-

FROM :- It is uesd to describe the base image for our container

MAINTAINER :- It is uesd to describe the maintainer of the Docker image

ADD :- It is used to copy/download the source project files into docker container specified loccation

WORKDIR :- It is used to select to working directory

COPY :- It is simillar to ADD command but it is not able to dowmload file from remote location	   

RUN :- It is used to run linux commands

EXPOSE :- It is used to expose the port for communiation

CMD :- It is used to start the appliction specific entry point this command is not executed at the cretion of docker it is executed at when we run docker image

Building Docker image :-

    •  sudo docker build -t your_image_name .
      
**note :- here “.” represents the current location for Dockerfile
List All Docker imades :-
    • sudo docker images
      
Run this to launch your container :-

    • sudo docker run -p 80:80 -i -t your_image_name

List All Docker Containers :-

    • sudo docker ps –all
      
Going into Docker Container shell :-

    • sudo docker exec -i -t <ID_OF_DOCKER_CONTAINER> /bin/bash 	


Removing Docker image :-

    • sudo docker image rm  <ID_OF_DOCKER_Image>




Removing Docker cointainer :-

    • sudo docker container rm  <ID_OF_DOCKER_Image>


**note tere are many other important commands you can found on official Docker site


