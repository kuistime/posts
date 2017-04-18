
```javascript
/**
 * 是否非负整数
 * @param num
 * @returns {boolean}
 */
function isNonNegativeInteger(num) {
    return Math.abs(num) === parseInt(num, 10);
}

/**
 * 计算下一页码
 * @param rows
 * @param page_size
 * @returns {*}
 */
function pgNext(rows, page_size) {
    if (page_size === 0) {
        throw new Error('page_size ZERO is not allowed')
    } else if (!isNonNegativeInteger(rows) || !isNonNegativeInteger(page_size)) {
        throw new Error('non-negative integers is required')
    }
    var factor = rows / page_size;
    var mod = rows % page_size;
    var pg_next;
    if (factor === 0) {
        pg_next = 1;
    } else if (mod === 0) {
        pg_next = factor + 1;
    } else {
        pg_next = false;
    }
    return pg_next
}
```
