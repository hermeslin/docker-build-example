# Copy our php config
FROM php:7-fpm-alpine

#
MAINTAINER hermeslin <mercury.iwork@gmail.com>

# make guest container directory, let php can execute and store error log
RUN mkdir -p /var/www && chown -R www-data:www-data /var/www
RUN mkdir -p /var/log/php-7-fpm

WORKDIR /var/www

# Install php extension
RUN docker-php-ext-install \
	curl \
	fileinfo \
	gd \
	hash \
	iconv \
	json \
	mbstring \
	mcrypt \
	mysqli \
	opcache \
	pdo_mysql \
	session \
	simplexml \
	soap \
	sockets \
	tokenizer \
	xml \
	xmlreader \
	xmlrpc \ 
	xmlwriter \
	zip

# Install conposer
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

# Expose conrainer port
EXPOSE 9000

# Execute command when container start
CMD ["php-fpm"]