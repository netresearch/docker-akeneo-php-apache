FROM php:5-apache

COPY setup/ /

RUN chmod +x /usr/local/bin/akeneo-php-*

RUN akeneo-php-install-deps && rm /usr/local/bin/akeneo-php-install-deps

RUN a2enmod rewrite \
    && a2ensite akeneo_pim \
    && a2dissite 000-default.conf

WORKDIR /var/www/html
VOLUME /var/www/html

CMD ["akeneo-php-apache-command"]
