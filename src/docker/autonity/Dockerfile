# Build Autonity using a stock Go builder container
FROM golang:1.21-alpine as builder

RUN apk add --no-cache make gcc musl-dev linux-headers libc-dev git perl-utils
RUN mkdir /app
WORKDIR /app

# Clone repository, fetch tags, and checkout v0.12.3
RUN git clone --depth 1 https://github.com/autonity/autonity.git /app/autonity
RUN cd /app/autonity && git fetch --tags && git checkout v0.12.3 && make autonity

FROM alpine:latest

RUN apk add --no-cache ca-certificates
COPY --from=builder /app/autonity/build/bin/autonity /usr/local/bin/

EXPOSE 8545 8546 8547 30303 30303/udp
ENTRYPOINT ["autonity"]
