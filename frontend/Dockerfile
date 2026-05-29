FROM alpine:3.20 AS builder

WORKDIR /src

COPY . .

FROM nginxinc/nginx-unprivileged:alpine

COPY --from=builder /src /usr/share/nginx/html

EXPOSE 8080
