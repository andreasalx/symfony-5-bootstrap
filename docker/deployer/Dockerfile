FROM php:7.4-alpine

ARG version=dev-master

RUN apk update --no-cache \
 && apk add --no-cache rsync

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN composer global require deployer/deployer:$version \
 && composer global require symfony/yaml \
 && composer global require symfony/filesystem \
 && composer global require sebastian/comparator \
 && ln -s /root/.composer/vendor/bin/dep /usr/bin/deployer

WORKDIR /var/www/html/deployer