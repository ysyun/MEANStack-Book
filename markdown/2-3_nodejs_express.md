# Express

## HTTP Methods

## Middlewares

### bodyParser()

### cookieParser()

### session()

### static()

# Passport

## Session

### Cookie

``` javascript
var express = require('express');
var app = express();
app.use(express.cookieParser());
```

### Encryption

``` javascript
var express = require('express');
var app = express();
app.use(express.cookieParser());
app.use(express.session({ secret: 'TheSecret' }));
```

### Session Storage

#### Memory

#### Redis

``` javascript
var express = require('express');
var redisStore = require('connect-redis')(express);
var app = express();
app.use(express.cookieParser());
app.use(express.session({
  secret: 'TheSecret',
  store: new redisStore({
  })
});
```

#### MongoDB

``` javascript
var express = require('express');
var mongoStore = require('connect-mongo')(express);
var app = express();
app.use(express.cookieParser());
app.use(express.session({
  secret: 'TheSecret',
  store: new mongoStore({
  })
});
```

## Strategies

## Local Strategies

### Mongoose

### Password Hashing

### Signup

### Signin
