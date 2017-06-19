# How to use this image

The following environment variables are optional for docker-cloud:

-       `VIRTUAL_HOST=...`              (to use with docker-cloud automatic haproxy)
-       `USER_UID=...`                  (change www-data uid if variable exist)
-       `USER_GID=...`                  (change www-data gid if variable exist, default USER_UID)
-	`WWW_INCLUDES=...`		(specify forlder for global php functions)
-	`WWW_SITES=...`			(specify forlder for additional apache sites cfg)
-	`WWW_WEBROOT=...`		(specify default apache webroot folder)

Example stack file for docker-cloud
~~~ text
php-demo:
  environment:
    - VIRTUAL_HOST=php-demo.example.com
    - USER_UID=1001
    - USER_GID=1002
    - WWW_INCLUDES=/var/www/includes
    - WWW_SITES=/etc/apache2/sites-enabled
    - WWW_WEBROOT=/var/www/html
  image: 'mhaluska/php-orgplan:latest'
  volumes:
    - <path to webroot>:/var/www/html
    - <path to includes>:/var/www/includes
    - <path to apache sites>:/etc/apache2/sites-enabled
    - <path to sitres folder>:/var/www/sites
~~~
