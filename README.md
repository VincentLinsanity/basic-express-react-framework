# Introduction
Provide a basic project to start a express-react web server

## Source
https://github.com/VincentLinsanity/basic-express-react-framework.git

## Version
Current Version: 0.0.0

## Maintainer
###Vincent Lin
###x123356@gmail.com

# Pre Requirement
- Nodejs
- Bower
- nodemon
- gulp
- MongoDB

If you are not start by docker, then you need to install nodejs first, 
and install bower, nodemon by npm install bower -g & npm install nodemon -g, 
all gulp require libary will install during npm install,
eventally you also need to install mongoDB and start it from
https://www.mongodb.org/

# Quick Start by Default
git clone project
```bash
$ git clone https://github.com/VincentLinsanity/basic-express-react-framework.git
```

initial node_module
```bash
$ mkdir -p usr/src/webapp/basic-express-react-framework && cd usr/src/webapp/basic-express-react-framework
$ npm install
```

initial bower_components
```bash
$ npm run postinstall
# note: don't use root permission run it, you can use --allow-root
```

run server
```bash
$ npm start
```

# Quick Start by Docker(not yet already)
get docker-compose file
```bash
$ $ mkdir -p /home/docker/compose/basic-express-react-framework
$ wget https://raw.githubusercontent.com/vincentlinsanity/basic-express-react-framework/master/docker-compose.yml
```

run docker-compose
```bash
$ cd /home/docker/compose/basic-express-react-framework
$ docker-compose up -d
```

# Compose Setting
- listen port 3000:3000 for http protocol
- listen port 443:443 for hhtps protocol
- link mongo and expose port 27017
- link redis and expose port 6379

```
basicexpressreactframework:
  image: vincentlinsanity/basicexpressreactframework:latest
  links:
    - "mongo:mongo"
    - "redis:redis"
  ports:
    - "3000:3000"
    - "443:443"
mongo:
  image: vincentlinsanity/mongodb:3.0.3
  expose:
    - 27017
  volumes:
    - '/home/docker/compose/meta/data/mongo:/data/db'
redis:
  image: vincentlinsanity/redis:3.0.3
  expose:
    - 6379
  volumes:
    - '/home/docker/compose/meta/data/redis:/data'
```
##environment example
- MONGO_ADDR = '10.36.62.101';
- MONGO_PORT = 27017;
- REDIS_ADDR = '10.36.62.101';
- REDIS_PORT = 6379;

#Build Docker Images(not yet already)