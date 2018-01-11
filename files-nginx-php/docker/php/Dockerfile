FROM amsdard/php:7

ENV WORKDIR=/opt

# build data
RUN date > /builddate && mkdir $WORKDIR/var
COPY ./config $WORKDIR/config
COPY ./bin $WORKDIR/bin
COPY ./src $WORKDIR/src
COPY ./templates $WORKDIR/templates
COPY ./translations $WORKDIR/translations
COPY ./public/index.php $WORKDIR/public/index.php
COPY ./vendor $WORKDIR/vendor
COPY ./composer.json $WORKDIR

RUN chown 1000:1000 -R /opt