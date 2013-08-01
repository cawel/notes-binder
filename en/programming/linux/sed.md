# sed

## Replacing "{{key}}" to "%{key}" in a bunch of files (without backuping files)
```
  sed -i "" -e "s/{{/%{/g" -e "s/}}/}/g" config/locales/*
```
-i "": no backups

## Commenting/uncommenting specific lines in an input file

The lines to comment/uncomment are those:
```
export http_proxy="http://proxy.example.com:80"
export https_proxy="http://proxy.example.com:80"
```

```
sed -i 's/^\(export https\?_proxy=\)/# \1/g' input_file
sed -i 's/^# \(export https\?_proxy=\)/\1/g' input_file
```