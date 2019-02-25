# Sprint Poker

Tiny Vue.js app that doesn't do anything, but is dockerized. Use docker-compose for dev, setup compile and reload on change. The "prod" Dockerfile is a cleaner multi-stage build.

### Compiles and hot-reloads for development
```
docker-compose up -d
```
Setup for `http://localhost:8080/`


### Compiles and minifies for production
```
docker build . -t sprint-poker

docker run -d -p 8080:80 sprint-poker
```
