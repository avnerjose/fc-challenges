FROM golang:1.22.3-alpine AS builder
WORKDIR /usr/src/app
COPY full-cycle.go .
RUN go mod init full-cycle
RUN go build

FROM scratch
COPY --from=builder /usr/src/app/full-cycle .
ENTRYPOINT ["./full-cycle"]

