# docker-lamp
An orchestrated bundle of Docker containers for developing and testing complete web applications using PHP and MySQL.

## Adding a virtual host to web container
1. Add a apache virtual host file to conf/apache/sites-available directory (eg. 999-example.conf)
2. enable the site: `docker exec lamp_web_1 a2ensite 999-example`
3. reload web server: `docker exec lamp_web_1 service apache2 reload`
4. Commit changes to container into a image for future use: `docker commit lamp_web_1 llslim/lamp_web:latest`
5. Change the image name of the 'web' service in the 'docker-compose.yml' file to the new local committed image above.
