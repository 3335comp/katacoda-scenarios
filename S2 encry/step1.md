First, we want to setup a enviroment first:

Pulliing the MySQL image and running it on a docker container

`docker run --name mysql -e MYSQL_ROOT_PASSWORD=root -d percona:latest`{{execute}} 

Run the MySQL container in Interactive Mode to get access of the bash shell of the container

`docker exec -it mysql bash`{{execute}} 

Now we can login into our mySQL database with user ROOT

`mysql -u root -proot`{{execute}} 
