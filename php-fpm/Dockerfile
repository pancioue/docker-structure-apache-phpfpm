FROM php:8.1.0-fpm

RUN docker-php-ext-install pdo_mysql

# 安裝 redis
RUN pecl install -o -f redis \
    &&  rm -rf /tmp/pear \
    &&  docker-php-ext-enable redis

#cron && vim && zip,unzip
RUN apt update && apt install --yes zip unzip cron
RUN apt install --yes vim


# # imagick
# RUN apt install -y libmagickwand-dev --no-install-recommends
# RUN mkdir -p /usr/src/php/ext/imagick;
# RUN curl -fsSL https://github.com/Imagick/imagick/archive/06116aa24b76edaf6b1693198f79e6c295eda8a9.tar.gz | tar xvz -C "/usr/src/php/ext/imagick" --strip 1;

# RUN apt -y install imagemagick --yes
# ## imagick extension
# RUN docker-php-ext-install imagick
# RUN docker-php-ext-enable imagick

# php.ini example
# RUN echo "memory_limit = 1G" >> /usr/local/etc/php/php.ini
# RUN echo "upload_max_filesize = 50M" >> /usr/local/etc/php/php.ini
# RUN echo "post_max_size = 50M" >> /usr/local/etc/php/php.ini
# RUN echo "max_input_time = 60" >> /usr/local/etc/php/php.ini
# RUN echo "file_uploads = On" >> /usr/local/etc/php/php.ini
# RUN echo "max_execution_time = 300" >> /usr/local/etc/php/php.ini
# RUN echo "LimitRequestBody = 100000000" >> /usr/local/etc/php/php.ini
# RUN echo "date.timezone = Asia/Taipei" >> /usr/local/etc/php/php.ini

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# COPY app/ /var/www/html/bbc-api
WORKDIR /var/www/html
RUN chown -R www-data:www-data /var/www/html