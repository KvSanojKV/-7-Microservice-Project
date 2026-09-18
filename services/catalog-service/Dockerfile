FROM golang:1.24 AS builder

WORKDIR /app

COPY go.mod go.sum ./

RUN go mod download

COPY . .

RUN go build -o catalog-service .

FROM debian:bookworm-slim

WORKDIR /app

COPY --from=builder /app/catalog-service .

EXPOSE 8082

CMD ["./catalog-service"]
