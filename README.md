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
- Nodemon
- Gulp
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
$ mkdir -p /home/docker/compose/basic-express-react-framework
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

#Package Name	Description
* alt	
Flux library for React.

* async	
For managing asynchronous flow.

* body-parser	
For parsing POST request data.

* colors	
Pretty console output messages.

* compression	
Gzip compression.

* express	
Web framework for Node.js.

* history	
Manage session history in browsers, used by react-router.

* mongoose  
MongoDB ODM with validation and schema support.

* morgan	
HTTP request logger.

* react	
React.

* react-dom	
React rendering, it is no longer bundled with React.

* react-router	
Routing library for React.

* request	
For making HTTP requests to EVE Online API.

* serve-favicon	
For serving favicon.png icon.

* socket.io	
To display how many users are online in real-time.

* swig	
To render the initial HTML template.

* underscore	
Helper JavaScript utilities.

* xml2js	
For parsing XML response from EVE Online API.

#Gulp Task Description
##http://www.sitepoint.com/introduction-gulp-js/
* vendor	
Concatenates all JS libraries into one file.

* browserify-vendor	
For performance reasons, NPM modules specified in the dependencies array are compiled and bundled separately. As a result, bundle.js recompiles a few hundred milliseconds faster.

* browserify	
Compiles and bundles just the app files, without any external modules like react and react-router.

* browserify-watch	
Essentially 
the same task as above but it will also listen for changes and re-compile bundle.js.

* styles	
Compiles LESS stylesheets and automatically adds browser prefixes if necessary.

* watch	
Re-compiles LESS stylesheets on file changes.

* default	
Runs all of the above tasks and starts watching for file changes.

* build	
Runs all of the above tasks then exits.