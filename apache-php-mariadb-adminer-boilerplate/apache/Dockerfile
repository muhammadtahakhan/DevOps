ARG APACHE_VERSION=""
FROM httpd:${APACHE_VERSION:+${APACHE_VERSION}-}alpine

RUN apk update; \
    apk upgrade;

RUN apk add \
  bash \
  apache2 \
  php7.4-apache2 \
  curl \
  ca-certificates \
  openssl \
  git \
  php7 \
  php7.4-phar \
  php7.4-json \
  php7.4-iconv \
  php7.4-openssl \
  tzdata \
  openntpd \
  php7.4-ftp \
  php7.4-xdebug \
  php7.4-mcrypt \
  php7.4-mbstring \
  php7.4-soap \
  php7.4-gmp \
  php7.4-pdo_odbc \
  php7.4-dom \
  php7.4-pdo \
  php7.4-zip \
  php7.4-mysqli \
  php7.4-sqlite3 \
  php7.4-bcmath \
  php7.4-gd \
  php7.4-odbc \
  php7.4-pdo_mysql \
  php7.4-pdo_sqlite \
  php7.4-gettext \
  php7.4-xmlreader \
  php7.4-xmlwriter \
  php7.4-tokenizer \
  php7.4-xmlrpc \
  php7.4-bz2 \
  php7.4-pdo_dblib \
  php7.4-curl \
  php7.4-ctype \
  php7.4-session \
  php7.4-exif;

RUN sed -i "s/#LoadModule\ rewrite_module/LoadModule\ rewrite_module/" /usr/local/apache2/conf/httpd.conf;

# COPY .bashrc /root/.bashrc

# Copy apache vhost file to proxy php requests to php-fpm container
COPY demo.apache.conf /usr/local/apache2/conf/demo.apache.conf
RUN echo "Include /usr/local/apache2/conf/demo.apache.conf" \
    >> /usr/local/apache2/conf/httpd.conf