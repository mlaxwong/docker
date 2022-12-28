FROM golang:alpine

RUN apk update && apk add --no-cache git && apk add --no-cach bash && apk add build-base

RUN apk add git
RUN go install -v golang.org/x/tools/gopls@latest

WORKDIR /workspace