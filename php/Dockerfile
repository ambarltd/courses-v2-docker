FROM php:8.3-fpm

RUN rm /etc/localtime
RUN ln -s /usr/share/zoneinfo/UTC /etc/localtime
RUN "date"

RUN apt-get update
RUN apt-get install git -y
RUN apt-get install zip -y
RUN apt-get install unzip -y
RUN apt-get install libssl-dev -y
RUN apt-get install zlib1g-dev -y
RUN apt-get install wget -y
RUN apt-get install nginx -y
# to use top in the container when necessary
RUN apt-get install procps -y
RUN apt-get install supervisor -y

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version
RUN pecl install mongodb
RUN docker-php-ext-enable mongodb
RUN apt-get install -y libpq-dev
RUN docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql
RUN docker-php-ext-install pdo pdo_pgsql pgsql
RUN apt-get install -y libicu-dev
RUN docker-php-ext-configure intl && docker-php-ext-install intl