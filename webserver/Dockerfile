FROM golang:1.14.3 as builder
WORKDIR /go/src/webserver
COPY main.go ./
RUN CGO_ENABLED=0 go install

FROM scratch
COPY --from=builder /go/bin/webserver /webserver
CMD ["/webserver"]
