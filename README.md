# Prerequisites
#
- JDK 11 
- Maven 3 
- MySQL 8

# Technologies 
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- Tomcat
- MySQL
- Memcached
- Rabbitmq
- ElasticSearch
# Database
Here,we used Mysql DB 
sql dump file:
- /src/main/resources/db_backup.sql
- db_backup.sql file is a mysql dump file.we have to import this dump to mysql db server
- > mysql -u <user_name> -p accounts < db_backup.sql
  

  # PROVISISIONING #

1.NGINX (web-service)
2.TOMCAT(application-service)
3.RABBITMQ(broking/queuing service)
4.MYSQL (data base) 

# DOCKER ENGINE SET-UP #

1)vagrant intit bent/ubuntu-22.04.
to place the vagrant file in the directory on our local machine.
2.make the changes in the file vagrant file by hitting "vim vagrant file".
3.then hit "vagrant up" command.
It will bring up the vagrant vms provisioned.
4.vagrant ssh.
it is used to login in to the vm.
5.Now you need you need to install the docker engine in the vm.
you need to follow the doc "https://docs.docker.com/engine/install/ubuntu/".
-it will install the docker engine in the vagrant vm.
6.Then you need to add the ubuntu user in the docker group by hitting "usermod -aG docker vagrant".
7.then you can also cross check the same by hitting the command "id vagrant".
8.then exit out of the vm and again login into the same vm.
9.for taking login into the vm you need to hit "vagrant ssh"
10.the you need to clone the source code from github vcs platform into the vs code studio.
11.after the repository is been clone into your vs code you need to change the branch from main to "containers".
12.once you are in the containers branch there we have all directories which consists of the all the dockerfiles for the three
of services a.app,DB,nginx(web) and in the same branch there is the dockercompose.yml file also written there in the repo.
13.then you need to modify the docker files and docker compose files according to your need and then we need to push it into the git-hub repository
14.then you need to bring  your vagrant vms up by hitting the command "vagrant up".
15.then for accessing the vm you need to hit the command "vagrant ssh"
this will give you a login into your vagrant vm.
16.then you need to clone the repository from github vcs platform by hitting the command "git clone repo url"
clone this repo "git clone https://github.com/Rajpreetsingh12/vprofile-project-Rajee.git".
17.and then you need to change the directory to the vprofile-project-Rajee by hitting the command cd "vprofile-project"
there you will have all your docker files of the services a.nginx(web-servver),tomcat(app-server),mysql(db).
and the docker-compose.yml files which consists the information for building the multi containers for the different sercvices.
18.And for performing all the actions you need to be the root user by hitting the command "sudo -i".
19.Then you need to hit the command "docker compose build"
this will create the docker images from the docker files written in your docker-engine vm".
20.then you can also cross check the images by hitting the command "docker images".
21.once the images are created then you need to hit the command "docker compose up -d "
it will build containerize all the images which are been created from the docker files you have created.
22.you can also cross check the containers by hitting the command "docker ps" it will display all the working containers.
and "docker ps -a" is used for displaying the stopped containers.
23.then you need to check the public ip of your vagrant vm by hitting the command "ip addr show"
24.and now you can see that the front end of the vprofile-applicatiopn is been displayed for you
and now you can check the functionalites once again for the all users-caching,Rabbit mq-(messaging and broking service),
"elastic search".
25.Now we need to push this images to the docker-hub by hitting the command docker push image name but first you need to take login 
in to your docker by hitting the command "docker login".!!
26.then hit command "docker images"
this will disply all your docker images youve created from docker files.
27.you can also push this three images app,web,db by creating the seperate repos for each on the ecr public repo.
28.if you need to stop all the containers you bought up if the work is over then you can hit the command "docker compose down"
29.if you need to permanantly delete all the images and containers then you need to hit the command "docker system prun -a.


# Summarization of the above project performed #
1.steps to set-up our stack services
2.find right base image from docker-file
3.edit the docker-file in case you need to customize your image
4.write docker-compose.yml file to build the multi containers using the images we have created.
5.Test all those containers by hitting the public ip of your vagrant vm or ec2 public ip and push the images to docker-hub and aws ecr in case you need to deploy the application 
aws cloud.
