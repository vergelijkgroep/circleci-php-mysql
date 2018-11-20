FROM circleci/php:7.1-cli

# Install PHP extensions:
RUN sudo apt-get update \
    && sudo apt-get install -y libicu-dev g++ \
    && sudo -E docker-php-ext-install pdo_mysql \
    && sudo docker-php-ext-install intl \
    && sudo apt-get clean

# Install Dockerize:
ENV DOCKERIZE_VERSION v0.6.1
RUN sudo wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && sudo tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && sudo rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

