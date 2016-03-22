FROM ubuntu

################################################################################
# Build instructions
################################################################################

# Remove default nginx configs.
RUN rm -f /etc/nginx/conf.d/*

RUN apt-add-repository ppa:phalcon/stable

# Install packages
RUN apt-get update && apt-get install -y \
  curl \
  mcrypt \
  php5-phalcon \
  php5-curl \
  php5-gd \
  php5-mysql \
  php5-mcrypt \
  php5-sqlite \
  php5-xdebug \
  php5-cli \
  php5-intl \
  php5-mongo \
  git \
  mc \
  nano


#XDEBUG

RUN echo "xdebug.remote_enable=on" >> /etc/php5/cli/conf.d/20-xdebug.ini \
    && echo "xdebug.remote_autostart=off" >>  /etc/php5/cli/conf.d/20-xdebug.ini \
    && echo "xdebug.profiler_enable=off" >>  /etc/php5/cli/conf.d/20-xdebug.ini \
    && echo "xdebug.profiler_enable_trigger=on" >>  /etc/php5/cli/conf.d/20-xdebug.ini \
    && echo "xdebug.profiler_output_dir=/usr/src/profiler" >>  /etc/php5/cli/conf.d/20-xdebug.ini \
    && echo "xdebug.remote_host=172.17.0.1" >>  /etc/php5/cli/conf.d/20-xdebug.ini

RUN curl -sS https://getcomposer.org/installer | php -- --filename=composer --install-dir=bin


WORKDIR ./var/www