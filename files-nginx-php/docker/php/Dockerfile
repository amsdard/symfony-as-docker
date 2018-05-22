FROM amsdard/php:7

ENV WORKDIR=/opt

# build data = the order do matter
RUN date > /builddate && mkdir $WORKDIR/var
COPY ./vendor $WORKDIR/vendor
COPY ./bin $WORKDIR/bin
COPY ./templates $WORKDIR/templates
COPY ./translations $WORKDIR/translations
COPY ./config $WORKDIR/config
COPY ./public $WORKDIR/public
COPY ./src $WORKDIR/src
COPY ./composer.json $WORKDIR

RUN chown 1000:1000 -R /opt