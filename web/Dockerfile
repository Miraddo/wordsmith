FROM golang
WORKDIR /go/src/app
COPY . .
RUN go build dispatcher.go
CMD [ "./dispatcher" ]