FROM golang:1.14.3 as builder
WORKDIR /go/src/forkbomb
COPY main.go ./
RUN CGO_ENABLED=0 go install

FROM scratch
COPY --from=builder /go/bin/forkbomb /forkbomb
CMD ["/forkbomb"]
