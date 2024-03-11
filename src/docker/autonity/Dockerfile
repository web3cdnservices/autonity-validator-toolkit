# Build Autonity in a stock Go builder container
FROM golang:1.21-alpine as builder

RUN apk add --no-cache make gcc musl-dev linux-headers libc-dev git perl-utils

RUN mkdir /app
RUN cd /app
RUN git clone -b v0.13.0 --depth 1 https://github.com/autonity/autonity.git /app/autonity
RUN cd /app/autonity && make all
FROM alpine:latest

RUN apk add --no-cache ca-certificates
COPY --from=builder /app/autonity/build/bin/autonity /usr/local/bin/
COPY --from=builder /app/autonity/build/bin/ethkey /usr/local/bin/

EXPOSE 8545 8546 8547 30303 30303/udp
ENTRYPOINT ["autonity"]
 
