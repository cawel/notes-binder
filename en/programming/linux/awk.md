# awk

## fetch the n-th token of a line
```
  heroku logs | grep "service=" | awk '{print $12}'
```
