# Base image for building the Go application
FROM golang:1.21.13-alpine3.20 AS build

WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download

COPY . .
RUN go build -o auth-api

# Base image for running the application
FROM debian:bookworm-slim
WORKDIR /app
COPY --from=build /app/auth-api .

EXPOSE 8081
CMD ["./auth-api"]
