# koa-log4js
A wrapper for [log4js-node](https://github.com/nomiddlename/log4js-node) which support Koa logger middleware.
Log message is forked from Express (Connect) logger [file](https://github.com/nomiddlename/log4js-node/blob/master/lib/connect-logger.js).

## Installation

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

See [here](https://github.com/nomiddlename/log4js-node) for more info.