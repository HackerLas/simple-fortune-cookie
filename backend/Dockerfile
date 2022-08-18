FROM golang:1.16 as builder

RUN go get github.com/gomodule/redigo/redis

RUN mkdir /build

ADD ./ /build/

WORKDIR /build

RUN CGO_ENABLED=0 GOOS=linux go build -a -o backend

FROM alpine:3.11.3
COPY --from=builder /build/backend . 

ENTRYPOINT [ "./backend" ]