# Start up the MySQL Containers

First, we should start up a MySQL database for storing the data in WordPress. 
We will make use of the official docker image `mysql:8` in the Docker hub.

Create a docker network for communication between MySQL and WordPress containers.

> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> docker network create wordpress-network </span>

Startup a container `mysql` in the background (using `-d` option). 

> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> docker run --name mysql -d -e  MYSQL_ROOT_PASSWORD=12345 -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wordpress -e MYSQL_PASSWORD=12345 --network=wordpress-network -v db_data:/var/lib/mysql mysql:8 </span>


The `-v` options maps the container's path `/var/lib/mysql` to the persistent volume *db_data* in the docker host. Also, the following environment variables are defined:

* `MYSQL_ROOT_PASSWORD=12345`: Initialize the root's password in the MySQL database.
* `MYSQL_DATABASE=wordpress`: Create a  database with the specified name.
* `MYSQL_USER=wordpress` and `MYSQL_PASSWORD=12345`: Create a user with the specified password. This user will be granted the superuser permissions for the database specified by the `MYSQL_DATABASE` variable. 


Verify that the `mysql:8` container is running.

> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> docker ps </span>

Check the logs of the `mysql` container.

> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> docker logs mysql </span>

Verify that the MySQL Server is started up successfully.

**Exercises**: 
* Execute the following command to understand more about the `docker run` command.
> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> docker run --help </span>
*  Visit https://hub.docker.com/_/mysql for details about the parameters in the mysql docker image

<br/>
