# koa-log4js
A wrapper for [log4js-node](https://github.com/nomiddlename/log4js-node) which support [Koa](https://github.com/koajs/koa) logger middleware.
Log message is forked from Express (Connect) logger [file](https://github.com/nomiddlename/log4js-node/blob/master/lib/connect-logger.js).

## Note
This branch is use to Koa v0.x & v1.x.
To use [Koa v2.x](https://github.com/koajs/koa/tree/v2.x), please check the [v2.x](https://github.com/dominhhai/koa-log4js/tree/v2.x) branch.

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
## Full Example
Check [this repo](https://github.com/dominhhai/koa-log4js-example) for full example with Koa v1

## Others
See [here](https://github.com/nomiddlename/log4js-node) for more info.
