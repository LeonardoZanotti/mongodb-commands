# MongoDB useful commands

## Create jsons files from all database collections
```bash
$ mongo --quiet mydatabase --eval "db.getCollectionNames().join('\n')" | \
$ grep -v system.indexes | \
$ xargs -L 1 -I {} mongoexport -d mydatabase -c {} --out {}.json
```


## Create dump of a database
```bash
$ mongodump -h localhost:27017 -d mydatabase
```

## Import the dump
```bash
$ mongorestore -h localhost:27017 -d mydatabase path/to/dump/mydatabase/
```
