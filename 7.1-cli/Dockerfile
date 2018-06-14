FROM circleci/php:7.1-cli

RUN sudo apt-get update \
    && sudo apt-get install -y libicu-dev g++ \
    && sudo docker-php-ext-install pdo_mysql \
    && sudo docker-php-ext-install intl \
    && sudo apt-get clean

