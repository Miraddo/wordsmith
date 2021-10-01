# Build Stage
FROM golang:alpine AS builder
WORKDIR /go/src/app
COPY . .
RUN go build dispatcher.go && rm -rf static dispatcher.go

# Copy the build output from builder image into the production image,
# to have less size 
FROM alpine AS production
WORKDIR /go/src/app
COPY --from=builder /go/src/app/dispatcher .
CMD ["./dispatcher"]