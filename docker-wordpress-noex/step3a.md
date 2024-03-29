# Exploring the WordPress container

First, show the running containers.

> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> docker ps </span>

Launch a shell to the WordPress container by using the container name.

> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> docker exec -it wordpress bash </span>

Check that the current folder is `/var/www/html`. 

Execute <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> ls </span> to show the files in the folder where you will find the PHP files for the application.

Execute <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> ps aux </span> to examine the processes running in the container.

Execute <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> printenv </span> to examine the environment variable. 

You will find the various environment variables (`WORDPRESS_DB_HOST`, `WORDPRESS_DB_USER`,  `WORDPRESS_DB_PASSWORD`) you have passed to the docker container. These environment variables are used by WordPress application to connect to the MySQL database.

Exit the bash shell in the wordpress container:
> <span align="left" style="color:#FFF;background:#555;font:Courier New; font-size: 90%; padding-left: 5px; padding-right: 5px; padding-top: 5px; padding-bottom: 5px;"> exit </span>

<br/>
