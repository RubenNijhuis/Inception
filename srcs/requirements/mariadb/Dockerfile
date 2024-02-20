FROM alpine:latest

RUN apk update && apk add mariadb

EXPOSE 3306

CMD ["mysqld", "--bind-address=0.0.0.0"]