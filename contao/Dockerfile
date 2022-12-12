
FROM registry.addmore.de/addmore/php:8.1-apache-buster

ENV APACHE_DOCUMENT_ROOT=/var/www/html/public

ADD ./etc/php/php.ini /usr/local/etc/php/php.ini
ENV PHP_VALUE="memory_limit=2G"

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf; \
    sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf

RUN apt-get update; \
    apt-get install -y --no-install-recommends git unzip;

RUN chown www-data.www-data /var/www

ADD --chown=www-data:www-data . .

USER www-data

RUN composer2 install --no-progress --no-dev --prefer-dist

RUN php vendor/bin/contao-console contao:install \
    && php vendor/bin/contao-console contao:install-web-dir \
    && php vendor/bin/contao-console contao:symlinks \
    && php vendor/bin/contao-console assets:install public \
    && php vendor/bin/contao-console cache:clear --no-warmup

VOLUME ["/var/www/html/contao/config", "/var/www/html/contao/system/config", "/var/www/html/templates", "/var/www/html/files"]

USER root
CMD ["apache2-foreground"]
