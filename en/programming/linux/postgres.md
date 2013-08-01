# postgres

```
psql
create database <database_name>;
```

## drop a database
```
psql
drop database <database_name>;
```

## dump
```
psql databasename < data_base_dump
```

```
pg_dump dbname > outfile
```

Drop and reload a postgres db with rails:
```
rake db:drop db:create && pg_restore --verbose --no-acl --no-owner -h localhost -d databbase_name db.dump