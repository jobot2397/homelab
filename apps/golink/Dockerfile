FROM golang:1.23-alpine AS builder
WORKDIR /app
COPY golink-1.0.0/ .
RUN go build -o golink ./cmd/golink

FROM alpine:latest
RUN apk --no-cache add ca-certificates
WORKDIR /root/
COPY --from=builder /app/golink .
CMD ["./golink"]
