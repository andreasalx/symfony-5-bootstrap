FROM php:fpm-alpine

# Install PHP extensions
RUN docker-php-ext-install \
	pdo \
	pdo_mysql

# Clean cache
CMD setup-apkcache; apk cache clean

WORKDIR /var/www/html

EXPOSE 9000

CMD php-fpm 