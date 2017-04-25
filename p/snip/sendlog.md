日志小工具
====

## 客户端

### CONSTANTS.json

```json
{
    "E1001": "XHR_REQUEST_ERROR",
    "E1002": "NET_RES_LOAD_FAILED",
    "E1003": "EXEC_FAIL"
}
```


### utils.js

```javascript
import ERROR_TYPE from './CONSTANTS.json'

export function sendlog(type, loc, err) {
    type = ERROR_TYPE[type]
    const raw = typeof err === 'object' ? JSON.stringify(err) : err
    const xhr = new XMLHttpRequest();
    xhr.open('POST', 'http://api.kuistime.com/test/log');
    xhr.setRequestHeader('Content-Type', 'application/json')
    const json = JSON.stringify({type, loc, raw});
    xhr.send(json);
    console.error(json)
}
```


## 服务器端

```javascript
var express = require('express');
var router = express.Router();
var fs = require('fs')
var Console = require('console').Console
var fd = fs.createWriteStream('../data/runtime/data.txt', {flags: 'a'})
const logger = new Console(fd);

/* GET users listing. */
router.options('/', function (req, res) {
    req.get('lsdkf')
    res.set('Access-Control-Allow-Credentials', true);
    res.set('Access-Control-Allow-Origin', req.get('Origin'))
    res.set('Access-Control-Allow-Methods', 'GET, POST, PUT')
    res.set('Access-Control-Allow-Headers', 'content-type')
    res.send('ok--allow')
})
router.post('/', function (req, res, next) {
    const bd = req.body;
    const line = `${Date.now()} ${bd.type} ${bd.loc} ${JSON.stringify(bd.raw)}`
    logger.log(line)
    res.set('Access-Control-Allow-Credentials', true);
    res.set('Access-Control-Allow-Origin', req.get('Origin'))
    res.send(`${line.length} len`)
});

module.exports = router;

```
