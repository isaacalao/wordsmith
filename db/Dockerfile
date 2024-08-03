# DATABASE

# INITIALIZE AND START STAGE
ARG ALPINEVER="3.19"

FROM postgres:alpine${ALPINEVER} AS initdb 

WORKDIR /docker-entrypoint-initdb.d/

COPY words.sql .

USER postgres

ENV POSTGRES_HOST_AUTH_METHOD=trust
