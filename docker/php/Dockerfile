FROM php:7.3-fpm
ARG WITH_XDEBUG=false

RUN docker-php-ext-install pdo pdo_mysql

RUN if [ $WITH_XDEBUG = "true" ] ; then \
	pecl install xdebug; \
	docker-php-ext-enable xdebug; \
	echo "error_reporting = E_ALL" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini; \
	echo "display_startup_errors = On" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini; \
	echo "display_errors = On" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini; \
	echo "xdebug.remote_enable=1" >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini; \
fi ;