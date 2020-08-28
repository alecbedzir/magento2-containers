# https://hub.docker.com/_/httpd
FROM httpd:2.4-alpine

WORKDIR /var/www/html

# Install runtime dependencies
# - fcgi for testing php-fpm (see http://www.inanzzz.com/index.php/post/653v/testing-php-fpm-without-having-a-web-server)
RUN apk add --no-cache \
	php7 \
	apache2 \
	php7-apache2 \
	fcgi \
    shadow \
    bash \
    lsof \
    sed \
    less \
    nano \
    curl \
  # Change uid to 1000 and gid to 1000
  && usermod -u 1000 www-data \
  && groupmod -g 1000 www-data

USER www-data

RUN mkdir -p pub