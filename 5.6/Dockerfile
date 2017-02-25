FROM php:5.6-cli

ENV COMPOSER_VERSION 1.3.2

RUN apt-get update -yqq
RUN apt-get install git -yqq
RUN apt-get install zlib1g-dev -yqq
RUN apt-get install parallel -yqq

RUN /usr/bin/env php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN /usr/bin/env php composer-setup.php --install-dir=/usr/local/bin --filename=composer --version=$COMPOSER_VERSION
RUN /usr/bin/env php -r "unlink('composer-setup.php');"

RUN docker-php-ext-install zip
RUN docker-php-ext-install mysqli

RUN apt-get autoclean
RUN apt-get autoremove
RUN rm -rf /var/lib/apt/lists/*
