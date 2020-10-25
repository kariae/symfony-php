FROM php:7.4-fpm-alpine

ENV WORKDIR "/var/www/app"

RUN apk upgrade --update && apk --no-cache add \
    gcc g++ make autoconf tzdata openntpd libcurl curl-dev coreutils \
    freetype-dev libxpm-dev libjpeg-turbo-dev libvpx-dev \
    libpng-dev libressl libressl-dev libxml2-dev icu-dev libzip-dev postgresql-dev yarn

RUN apk add --no-cache --virtual build-dependencies icu-dev libxml2-dev freetype-dev libpng-dev libjpeg-turbo-dev g++ make autoconf

RUN docker-php-ext-configure intl \
    && docker-php-ext-configure opcache \
    && docker-php-ext-configure gd --with-freetype --with-jpeg

RUN docker-php-ext-install -j$(nproc) gd iconv pdo pdo_mysql pdo_pgsql curl \
    bcmath json xml xmlrpc zip intl opcache

# Install Redis
RUN docker-php-source extract \
    && pecl install redis \
    && docker-php-ext-enable redis \
    && docker-php-source delete

# Add timezone
RUN ln -s /usr/share/zoneinfo/UTC /etc/localtime && \
    "date"

# Install composer
RUN curl -sS https://getcomposer.org/installer | \
    php -- --install-dir=/usr/local/bin --filename=composer

# Cleanup
RUN rm -rf /var/cache/apk/* \
    && find / -type f -iname \*.apk-new -delete \
    && rm -rf /var/cache/apk/*

RUN mkdir -p ${WORKDIR}
RUN chown www-data:www-data -R ${WORKDIR}

WORKDIR ${WORKDIR}

EXPOSE 9000

CMD ["php-fpm"]
