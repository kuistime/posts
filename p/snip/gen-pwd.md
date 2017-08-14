### IMPL

```javascript
function gpw(len){
  const arr = [];
  while(len--){
    const r = Math.random();
    const n = Math.floor(r * 93) + 32;
    const c = String.fromCharCode(n);
    arr.push(c);
  }
  return arr.join('');
}

```

### TEST

```javascript
var i = 10;
while(i--){
  let pw = gpw1(32);
  console.log(pw);
}
```
