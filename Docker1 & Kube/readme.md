For the following task refer the link 1
* Create and use a Docker container interactively
* Create a Dockerfile, which allows you to declaratively define your containers
* Run detached containers and understand port forwarding
* Use docker-compose to run a multi-container web application

For the following task 1, 2, 3 refer link 3
* Task 1: Run some simple Docker containers
* Task 2: Package and run a custom app using Docker
* Task 3: Modify a Running Website

1.	https://decal.ocf.berkeley.edu/archives/2018-fall/labs/a11
2.	https://www.youtube.com/watch?v=F7We8xx1_Lw
3.	https://training.play-with-docker.com/beginner-linux/
https://github.com/dockersamples -- this  has apps for docker

# Set Up the Environment:

## Install Docker Desktop:

1. Visit the Docker Desktop for Windows download page.
2. Download the Docker Desktop installer.
3. Double-click Docker Desktop Installer.exe to run the installer.
4. Follow the installation instructions.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/723e6f27-c27a-4695-9558-3177b1e63046)

## Verify Installation:

1. Open a command prompt (Windows PowerShell or Command Prompt).
2. Run the command: docker --version
It should show client and server both installation where client is our host os command Prompt and server is Docker Engine.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/c012998d-c76e-44de-b3ae-634b02df6bbd)

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/5330c306-5c39-44df-b242-8f8696dfa40d)

Run the hello-world Image
docker run hello-world

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/11e9172a-80d3-4be7-b334-5abfb48816e5)

### Create and use a Docker container interactively

> docker run -it ubuntu bash

In this command -i refers to an interactive, -t refers to the tag that needs to be pulled. ubuntu is the tag
name that gets pulled, bash is the command that would be run interactively.


![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/50344b78-e54f-40de-9d5e-1fd7e0a312fc)

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/da23566e-3fab-489a-9952-43f8eb0e17fa)

> docker images

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/b0039818-f2b1-4811-bc06-33937374774d)

### Create a Dockerfile, which allows you to declaratively define your containers

Create a file named Dockerfile in the current directory with the following contents.

FROM ubuntu:bionic

RUN apt-get update && \
apt-get install --no-install-recommends -y \
python3.6

CMD ["/usr/bin/python3.6", "-i"]

Build an image using the instructions written in the Dockerfile.

> docker build -t mypython:latest .

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/ffe59c92-49ab-49de-83b1-a3673ca672f3)

Verify the created Docker Image.

> docker images

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/05d351ec-fd2c-4a74-87dc-7cdc5dda4d78)

Interactively run the Docker Image and execute Python commands.

> docker run -it mypython

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/f949d834-f850-44d4-bc33-1a3207538d74)

### Run detached containers and understand port forwarding

> docker run -d -p=5050:80 httpd

The -d in the above command instructs the Docker Engine to run the container in detached mode. This will make the container to keep running until we explicitly stop it.

The httpd is the name of an image already built and available in the Docker Hub.
The -p flag takes in a colon separated pair of HOST_PORT:CONTAINER_PORT.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/937f4d58-970a-4f75-b74b-a5bb3e4ba961)

httpd image is downloaded successfully

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/0e132254-2664-47c6-9d74-96b1934ab3eb)

If we check in browser it works 

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/fd11effb-69e1-4163-a6d6-a7859f6c96b7)

### Use docker-compose to run a multi-container web application

docker compose is installed by typing the below commands in the Terminal.
As windows is there as hostOS, So docker compose is available 

> docker-compose version

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/b03dde04-cb80-493f-a469-3dbc8cdb7c5b)


A Dockerfile is written in the project directory which would contain the instructions required for the
deployment of the NodeJS project.

The NodeJS project is downloaded from the provided location by typing the below commands.
git clone https://github.com/0xcf/decal-sp18-a10
cd decal-sp18-a10

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/5b9ca206-e1ee-4983-a007-d083762ee7fc)

We navigate back to the parent directory using the below command.

A docker-compose.yml file is written which would glue the above NodeJS container with a database container
(Example: MongoDB).

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/46687594-bad6-4e39-85f0-0ffcf9de3231)


![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/9c40005c-a322-4faf-bd85-85b024dd6d93)

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/02ad0282-4f09-4ed8-88ca-80ff8a917aaa)

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/98d79117-43fa-45dc-95c6-a7f6ab84eed8)

We open browser at http://localhost:80.

![image](https://github.com/jayshah17/Secure-System-Engineering-/assets/76842630/430f0bcd-d703-4d6f-964e-0288c6fd696a)
