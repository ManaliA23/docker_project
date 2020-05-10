# DOCKER_PROJECT
I learnt about Docker under the guidance of **Vimal Daga Sir** under **IIEC RISE-1.0 campaign** . This is project using Docker to set-up a WebApp called **DRUPAL**

## SETUP 
My redhat-8 has docker and docker-compose installed.It also has images for mysql as well as for drupal
Otherwise the images can also be pulled from https://hub.docker.com/

## STEPS TO BUILD THIS PROJECT
1. Created a file docker-compose.yml and edit it using vim text editor `vim docker-compose.yml`
2. code to be written in docker-compose.yml file is given on docker-compose.yml as well as in the screenshots below
![screenshot](1.jpg?raw=true)
![screenshot](2.jpg?raw=true)

3. Now run `docker-compose up` command and that's it.Just in one click your environment will setup.
You can check it using `docker-compose ps` command
![screenshot](3.jpg?raw=true)


Webapp **drupal** can be seen by using local system IP
![screenshot](6.jpg?raw=true)

## DETAILED EXPLANATION OF docker-compose.yml file
* **version:**
In each version the style and syntax are different. I used version 3.
* **services:**
In docker compose we use the term services to rectify which things will run when we start the compose file.
* **container name:**
Docker-compose automatically creates the name for the containers using our defined container name. We just only have to tell that these containers we are using.
* **image and restart:**
image and restart these two key is used to specify which image we want to use and due to any reason if any of the container stops docker-compose will again restart it.
* **volumes:**
In docker as soon as we terminate an container our whole data inside that container destroyed. But if we want to make our data permanent then we have to use docker volume. Using the last volumes key we at first created two volumes. We know that MySQL and Drupal stores their data inside which folder. We simply make those folders permanent by mounting these volumes. That means due to any reason if our container terminated our data will not loose.
* **environment:**
There are many images in Docker which needs some pre-defined environment variables to run. That's why we need to pass these variables. 
* **depends_on and ports:**
As we know Drupal needs MySQL database server to store there files that's why we are using depends_on. Also we know that we have to expose our container(where drupal running) to a specific port otherwise from outside world we will not be able to access our WebApp.


*I HAVE CREATED THIS PROJECT ON LOCAL SYSTEM BUT USING CLOUD IT CAN BE EXPOSED TO OUTSIDE WORLD AND CAN BE USED BY CLIENTS*








