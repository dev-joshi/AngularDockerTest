FROM nginx:alpine

RUN apk add --update nodejs npm \
    && npm install -g @angular/cli

WORKDIR /app

COPY frontend-one ./frontend-one
COPY frontend-two ./frontend-two

RUN rm -rf /usr/share/nginx/html/*

RUN cd frontend-one \
    && npm ci \
    && npm run build:docker \
    && cd ..

RUN cd frontend-two \
    && npm ci \
    && npm run build:docker \
    && cd ..

EXPOSE 80