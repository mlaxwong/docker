FROM mlaxwong/php:8.2-fpm

# Update
RUN apt-get update && \
    apt-get upgrade -y

# Packages
RUN apt-get -y install git

# php.ini
RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"

# Install xdebug
RUN yes | pecl install xdebug \
	&& echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" \
		 > /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.mode=debug" >> /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.start_with_request=yes" >> /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.client_host=host.docker.internal" >> /usr/local/etc/php/conf.d/xdebug.ini \
	&& echo "xdebug.log_level=0" >> /usr/local/etc/php/conf.d/xdebug.ini

# Clean up
RUN apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*