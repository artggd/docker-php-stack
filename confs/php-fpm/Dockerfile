ARG phptag

FROM php:$phptag

# Install modules
RUN apk add --no-cache postgresql-dev icu-dev \
    && docker-php-ext-install pdo pdo_pgsql iconv intl opcache mbstring

RUN apk del icu-dev

CMD ["php-fpm"]
