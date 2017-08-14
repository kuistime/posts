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

gpw2(32)
gpw2(32)

```
