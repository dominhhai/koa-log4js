# koa-log4js
A wrapper for [log4js-node](https://github.com/nomiddlename/log4js-node) which support [Koa](https://github.com/koajs/koa) logger middleware.
Log message is forked from Express (Connect) logger [file](https://github.com/nomiddlename/log4js-node/blob/master/lib/connect-logger.js).

## Note
This branch is use to [Koa v2.x](https://github.com/koajs/koa/tree/v2.x).
To use Koa v0.x & v1.x, please check the [master](https://github.com/dominhhai/koa-log4js/tree/master) branch.

## Installation

#### for koa v0.x & v1.x
```
$ npm i --save koa-log4@1
```

#### for koa v2.x
```
$ npm i --save koa-log4@2
```

___The default logger is for [koa v2.x](https://github.com/koajs/koa/tree/v2.x)___
```
$ npm i --save koa-log4
```

## Usage
Config koa-log4js is same as the original [log4js-node](https://github.com/nomiddlename/log4js-node).

### Normal log4js way
This way is same as the original [log4js-node](https://github.com/nomiddlename/log4js-node).

```javascript
const log4js = require('koa-log4')

const log = log4js.getLogger('index')
log.info('index do some awesome things')
```

### Koa-middleware way
Similar to use Express (Connect) logger middleware.

```javascript
const log4js = require('koa-log4')
app.use(log4js.koaLogger(log4js.getLogger("http"), { level: 'auto' }))
```

There are more configuration options:

```javascript
const log4js = require("koa-log4")
app.use(log4js.koaLogger(
    // the logger to log to
    log4js.getLogger("http"),
    // the options object
    {
        // select the level all access logs will be set to, or use "auto" to choose depending on the status code (see next option)
        level: "auto",
        // if `level` is set to "auto" the default rule will map 200-299 to INFO, 300-399 to WARN and 400-599 to ERROR.
        // you can override this behavior by setting your own custom levelMapper.
        // (the example is the default implementation, do not copy unless you want to modify it)
        levelMapper: function(statusCode) {
            if (statusCode >= 400)
                return levels.ERROR
            if (statusCode >= 300)
                return levels.WARN
            return levels.INFO
        }
    }
))
```

## Full Example
Check [this repo](https://github.com/dominhhai/koa-log4js-example/tree/v2.x) for full example with `Koa v2`.

## Others
See [here](https://github.com/nomiddlename/log4js-node) for more info.
