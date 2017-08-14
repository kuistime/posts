### IMPL

```javascript
// call stack
function gpw1(len){
  const arr = [];
  while(len--){
    arr.push(String.fromCharCode(Math.floor(Math.random()*93)+32))
  }
  return arr.join('');
}

// temp value
function gpw2(len){
  const arr = [];
  while(len--){
    const r = Math.random();
    const n = Math.floor(r*93) + 32;
    const c = String.fromCharCode(n);
    arr.push(c);
  }
  return arr.join('');
}

```

### TEST

```javascript
// test
var i = 1e4;
var start;
var end;
console.log(start = Date.now());
while(i--){
  gpw1(32);
}
console.log(end = Date.now());
console.log(end-start);
```
