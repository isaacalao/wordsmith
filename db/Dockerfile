# DATABASE

ARG ALPINEVER="3.19"

FROM postgres:alpine${ALPINEVER} as baseimg

WORKDIR /docker-entrypoint-initdb.d/

COPY words.sql .

USER postgres

ENV POSTGRES_HOST_AUTH_METHOD=trust

CMD [ "postgres" ]
