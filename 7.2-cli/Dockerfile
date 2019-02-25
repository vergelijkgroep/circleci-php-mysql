FROM circleci/php:7.2-cli

# Install PHP extensions:
RUN sudo apt-get update \
    && sudo apt-get install -y libicu-dev g++ libc-client-dev libkrb5-dev libxml2-dev libpng-dev \
    && sudo -E docker-php-ext-install gd \
    && sudo -E docker-php-ext-install pdo_mysql \
    && sudo -E docker-php-ext-install intl \
    && sudo -E docker-php-ext-configure imap --with-kerberos --with-imap-ssl \
    && sudo -E docker-php-ext-install imap \
    && sudo -E docker-php-ext-install soap \
    && sudo apt-get clean

# Install Dockerize:
ENV DOCKERIZE_VERSION v0.6.1
RUN sudo wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && sudo tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && sudo rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

