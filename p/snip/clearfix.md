清除浮动
====

### scss
```scss
// Mixin itself
.clearfix() {
  &:before,
  &:after {
    content: " ";
    display: table;
  }
  &:after {
    clear: both;
  }
}

// Usage as a mixin
.element {
  .clearfix();
}
```

### css
```css
.clearfix::before,
.clearfix::after {
  content: " ";
  display: table;
}
.clearfix::after {
  clear: both;
}
```
