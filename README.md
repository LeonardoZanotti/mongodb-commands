# MongoDB useful commands

## Create jsons files from all database collections
mongo --quiet mydatabase --eval "db.getCollectionNames().join('\n')" | \
grep -v system.indexes | \
xargs -L 1 -I {} mongoexport -d mydatabase -c {} --out {}.json

## Create dump of a database
mongodump -h localhost:27017 -d welever-new

## Import the dump
mongorestore -h localhost:27017 -d welever-new welever-new/
