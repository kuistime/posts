groupBy.js
====

```javascript
function push(target, k, v) {
    target[k] = target[k] || []
    target[k].push(v)
}
function groupBy(list, key, proc) {
    const res = {}
    list.forEach((o) => {
        const k = proc ? proc(o[key]) : o[key];
        if (!k) {
            throw new Error('')
        }
        push(res, k, o)
    });
    return res;
}
```
