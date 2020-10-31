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

# Add user and group for application
ARG USER_ID
ARG GROUP_ID
RUN addgroup -g $GROUP_ID user
RUN	adduser --disabled-password -u $USER_ID -G user user

# Setting permission to user
RUN chown -R user:user /var/www/html

# Change the current user to user
USER user

WORKDIR /var/www/html

EXPOSE 9000

CMD php-fpm 