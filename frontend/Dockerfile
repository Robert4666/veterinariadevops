FROM alpine:3.20 AS builder

WORKDIR /src

COPY . .

FROM nginx:alpine

RUN rm -rf /usr/share/nginx/html/*

COPY --from=builder /src /usr/share/nginx/html

EXPOSE 80
