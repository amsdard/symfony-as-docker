FROM amsdard/php-webapp:7

ENV WORKDIR=/opt

# build apache
COPY ./docker/webapp/000-default.conf /etc/apache2/sites-enabled/000-default.conf

# build data
RUN date > /builddate && mkdir $WORKDIR/var
COPY ./config $WORKDIR/config
COPY ./bin $WORKDIR/bin
COPY ./src $WORKDIR/src
COPY ./templates $WORKDIR/templates
COPY ./translations $WORKDIR/translations
COPY ./public $WORKDIR/public
COPY ./vendor $WORKDIR/vendor
COPY ./composer.json $WORKDIR

RUN chown 1000:1000 -R /opt