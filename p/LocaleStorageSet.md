```javascript
/**
 * Operate localStorage like an Array
 * 
 */
class LocaleStorageSet {
    constructor(key, len, trackBy) {
        this.key = key;
        this.len = len;
        this.trackBy = trackBy;
        this.data = this._read()
    }

    _read() {
        const ls = localStorage.getItem(this.key) || '[]';
        return JSON.parse(ls);
    }

    _write() {
        if (this.data.length > this.len) {
            this.data.length = this.len;
        }
        const ls = JSON.stringify(this.data);
        localStorage.setItem(this.key, ls);
        return true;
    }

    // return true on repeat item found
    _checkRepeat(needle) {
        const trackBy = this.trackBy;
        let res = false;
        this.data.forEach(item => {
            if (trackBy) {
                res = item[trackBy] === needle[trackBy];
            } else {
                res = item === needle;
            }
            if (res) {
                console.warn('repeat item found');
                return false;
            }
        });
        return res;
    }

    push(item) {
        if (this._checkRepeat(item)) {
            return;
        }
        this.data.push(item)
        return this._write()
    }

    unshift(item) {
        if (this._checkRepeat(item)) {
            return;
        }
        this.data.unshift(item)
        return this._write()
    }

    pop() {
        const item = this.data.pop()
        this._write()
        return item
    }

    shift() {
        const item = this.data.shift()
        this._write()
        return item
    }

    getAll() {
        return this._read()
    }
}
```
