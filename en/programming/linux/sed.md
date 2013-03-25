# sed

## Replacing "{{key}}" to "%{key}" in a bunch of files (without backuping files)
```
  sed -i "" -e "s/{{/%{/g" -e "s/}}/}/g" config/locales/*
```
