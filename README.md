# Docker Wordpress

A minimal docker image for running wordpress.

- The image is based off the `alpine php 7` image
- It includes `bash`, `vim` and `[wp-cli](http://wp-cli.org/)`
- I like to keep the full wordpress site in vesion control, that only works
  if you push all the user uploads onto something like `S3` using something like `W3-TotalCache`

My project tree looks like this:

    Dockerfile
    docker-compose.yml
    nginx
    |-conf
      |-site.conf
    |-ssl
      |-server.crt
      |-server.key
    src
    |-#wordpress code

Then use the image like so:

    FROM martinffx/wordpress

    COPY ./src /usr/src/app
    RUN ln -s /usr/src/app /var/www/html


