FROM mlaxwong/php:8.2-base

# Update
RUN apt-get update && \
    apt-get upgrade -y

RUN docker-php-ext-install opcache

# Setup Opcache
COPY ./opcache.ini /usr/local/etc/php/conf.d/opcache.ini

# Clean up
RUN apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*