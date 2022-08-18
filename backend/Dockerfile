FROM golang:1.13.2

RUN apt-get update -y
RUN apt-get install -y redigo:v1.8.5

RUN go build -o backend

ENTRYPOINT ./backend