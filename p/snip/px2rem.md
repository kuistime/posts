```javascript
cat input.css |px python -c "import sys,re;[sys.stdout.write(re.sub(r'([\d.]+)\s*px',(lambda m:str(float(m.group(1))/16)+'rem'),line)) for line in sys.stdin]" > output.rem.css
```
