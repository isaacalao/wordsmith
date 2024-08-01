# WEB

ARG GOVER="1.21.12" ALPINEVER="3.20" 

# BUILD STAGE
FROM golang:${GOVER}-alpine${ALPINEVER} as baseimg 

WORKDIR /webdir

COPY static /webdir/static

COPY dispatcher.go /webdir

RUN go build dispatcher.go

# RUN STAGE
FROM scratch as runimg

COPY --from=baseimg /webdir .

EXPOSE 80

CMD [ "./dispatcher" ]
