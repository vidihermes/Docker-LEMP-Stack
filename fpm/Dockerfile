FROM ubuntu

RUN apt-get update && apt-get install -y \
    vim curl \
    software-properties-common \
    && LC_ALL=C.UTF-8 add-apt-repository -y ppa:ondrej/php \
    && apt-get update && apt-get install -y \
    php7.1 php7.1-fpm php7.1-zip php7.1-curl \
    php7.1-gd php7.1-mcrypt php7.1-mysql php7.1-common \
    php7.1-cli php7.1-mbstring php7.1-sqlite3 php7.1-xml \
    php7.1-mcrypt php7.1-intl \
    && mkdir /run/php

RUN apt-get remove -y --purge software-properties-common \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN sed -i -e 's/;daemonize = yes/daemonize = no/g' /etc/php/7.1/fpm/php-fpm.conf \
    && sed -i "s/listen = .*/listen = 9000/" /etc/php/7.1/fpm/pool.d/www.conf

WORKDIR /var/app

EXPOSE 9000

CMD ["php-fpm7.1"]
