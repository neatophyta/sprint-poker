# Sprint Poker

Tiny Vue.js app that doesn't do anything, but is dockerized.

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
