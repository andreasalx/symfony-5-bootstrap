FROM php:fpm-alpine

# Install dependencies
RUN apk --update --no-cache add \
	bash \
	curl \
	git \
	unzip \
	vim \
	zip

# Install PHP extensions
RUN docker-php-ext-install \
	pdo \
	pdo_mysql

# Clean cache
CMD setup-apkcache; apk cache clean

WORKDIR /var/www/html

EXPOSE 9000

CMD php-fpm 