# WEB

# BUILD STAGE
ARG GOVER="1.21.12" ALPINEVER="3.20" 

FROM golang:${GOVER}-alpine${ALPINEVER} as gobuild 

WORKDIR /webdir

COPY static /webdir/static

COPY dispatcher.go /webdir

RUN go build dispatcher.go

# RUN STAGE
FROM scratch as gorun 

COPY --from=0 /webdir .

EXPOSE 80

CMD [ "./dispatcher" ]
