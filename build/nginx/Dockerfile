# Copy our nginx config
FROM nginx:stable-alpine

#
MAINTAINER hermeslin <mercury.iwork@gmail.com>

# Change nginx user and group, for php-fpm to use
RUN set -x ; \
  addgroup -g 82 -S www-data ; \
  adduser -u 82 -D -S -G www-data www-data && exit 0 ; exit 1

# Set project directory
RUN mkdir -p /var/www && chown -R www-data:www-data /var/www
WORKDIR /var/www

# Change nginx owner
RUN touch /var/run/nginx.pid && \
  chown -R www-data:www-data /var/run/nginx.pid && \
  chown -R www-data:www-data /var/cache/nginx

# Expose conrainer port
EXPOSE 80 443

# Execute command when container start
CMD ["nginx", "-g", "daemon off;"]