# Docker-Wordpress

## Instalation 

Install [Docker](https://docs.docker.com/engine/getstarted/step_one/) on your 
computer 

Clone this repo to a working directory on your machine and run `docker-compose up`

## What Happens

Docker reads the docker-compose.yml file and pulls down images from docker hub for the MySQL database (in this case I am using mariadb) and for the latestes version of Wordpress.

Once the images get pulled down and the containers are running it maps the port of the container from 80 to 8080 on you localhost. You can now visit the local install of Wordpress in your browser at localhost:8080

The docker-compose.yml also maps the wp-content folder in the docker wordpress container to the wordpress folder in your working directory. 

### Issues 

The first time you run `docker-compose up` there is an issue with the containers getting linked. You can `Control-C` to gracefully shut down the containers and then run `docker-compose up` again to get a successful linkage of the containers.

### Additional Info

If you want to run the containers in detached mode you can run `docker-compose up -d` and this will not output the requests that are made to localhost:8080. You can then run `docker-compose stop` to gracefully shut down the containers.

You can modify the docker-compose.yml to use any database you want and also map to any port. __If you are going to be running multiple sites at once you will want to have them running on different ports.__
