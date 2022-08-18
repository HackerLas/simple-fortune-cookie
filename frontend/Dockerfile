FROM golang:1.13-alpine3.11 as builder

RUN mkdir /build

ADD ./ /build/

WORKDIR /build

RUN CGO_ENABLED=0 GOOS=linux go build -a -o frontend

FROM alpine:3.11.3
COPY --from=builder /build/frontend . 

ENTRYPOINT [ "./frontend" ]