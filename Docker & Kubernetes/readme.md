Dockers

<img width="1258" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/15c69ac2-118d-4d19-b465-792b0a516187">

DOCKER
1. https://decal.ocf.berkeley.edu/archives/2018-fall/labs/a11
2. https://www.youtube.com/watch?v=F7We8xx1_Lw
3. https://training.play-with-docker.com/beginner-linux/
4. https://github.com/dockersamples -- this  has apps for docker

For the following tasks refer the link 1

Environment Setup
A new virtual machine is created and the Docker Engine Installation instruction is followed according to the documentation.
Before the Docker Engine is installed for the first time on a new host machine, we need to set up the Docker repository. This is done by entering the below command in the Terminal.

<img width="705" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/553c9a79-d73d-47c3-b478-a8c083a39b03">

Running an interactive container


<img width="578" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/8492b49e-135e-4250-aab0-628f294c25ee">

Basic Management

<img width="548" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/3f86136a-2fac-42fd-b5b8-d110a96fc77c">

Docker Logs 

<img width="547" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/22563f84-3594-4347-b4ed-8488edbeda26">

At some point, you may want to cleanup containers that have exited and you don’t plan on using anymore:

<img width="544" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/55208cf6-c1a0-49ac-bbd4-7dda0c0e3fa7">

You may have noticed when you were running the Ubuntu or Fedora containers the first time that Docker downloaded a good chunk of data before running the image. This is the image of the container. You can view all of the images you’ve downloaded with the docker images command:


<img width="574" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/83a12c42-8196-40a1-9787-c617f904a59f">

Images can take up quite a bit of space on your machine, so you may want to clean up images that you don’t plan on using. This is especially relevant if you get errors about not having enough disk space on your machine:

<img width="575" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/e9abde36-fcf7-4616-9358-335b490ff6fd">





