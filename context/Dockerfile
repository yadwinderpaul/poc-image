FROM node:8.12.0-alpine

RUN apk add --no-cache --update curl wget postgresql-client postgresql-dev \
  git openssl build-base make perl perl-dev \
  && rm -rf /var/cache/apk/* /tmp/*

# install pg_prove
RUN cpan TAP::Parser::SourceHandler::pgTAP

# install pgtap
ENV PGTAP_VERSION v0.98.0
RUN git clone git://github.com/theory/pgtap.git \
  && cd pgtap && git checkout tags/$PGTAP_VERSION \
  && make

CMD ["/bin/sh"]
