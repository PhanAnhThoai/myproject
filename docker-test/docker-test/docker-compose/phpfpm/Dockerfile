FROM php:7.4-fpm-alpine
USER root
ARG XDEBUG
ARG XDEBUG_CLIENT_PORT=9003
ARG XDEBUG_CLIENT_HOST=host.docker.internal
RUN if [ "${XDEBUG}" = 'true' ]; then \
    pecl channel-update pecl.php.net \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && export XDEBUG_CONFIG_PATH="/usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini" \
    && echo "xdebug.client_port = ${XDEBUG_CLIENT_PORT}" >>  $XDEBUG_CONFIG_PATH \
    && echo "xdebug.client_host = ${XDEBUG_CLIENT_HOST}" >> $XDEBUG_CONFIG_PATH \
    && echo "xdebug.mode = off" >> $XDEBUG_CONFIG_PATH \
    && echo "xdebug.start_with_request = yes" >> $XDEBUG_CONFIG_PATH ;\
  fi;

# Arguments defined in docker-compose.yml
#ARG UID=1000
#ARG GID=1000
#RUN usermod -u ${UID} coffeemug
#RUN groupmod -g ${GID} coffeemug
#RUN chown -R ${UID}:${GID} /home/coffeemug
#USER ${UID}
