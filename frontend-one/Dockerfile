FROM node:alpine as frontend-one

RUN apk update && apk add --no-cache make git

WORKDIR /app

COPY frontend-one/package*.json  /app/

RUN npm install @angular/cli@6.0.8 -g \
    && npm ci

COPY frontend-one /app

EXPOSE 4200