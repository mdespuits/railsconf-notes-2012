# Schemaless SQL

## Speaker: Will Leinweber - [@leinweber](http://twitter.com/lienweber)
## [Slides](http://ssql-railsconf.herokuapp.com/)

* Discovered ActiveRecord
* Discovered CouchDB

### CouchDB

* http => Caching, load balancing
* shemaless
* json
* document based

### easy to understand love for mongo and couchdb

* SQL is hard
* tables suck
* migrations are painful (so avoid them)
* Often my data is not relational
* I want my storage to look like my code
* postgres

### Reasons to choose postgres

* mvcc
* fulltext search
* geo
* knn
* listen/notify
* datatypes
* replication

### [wal-e](https://github.com/heroku/wal-e)

`rollback;`

### I missed documents
### hstore & plv8

### 1. hstore

* key/value store in a column
* usage => `SELECT * FROM products WHERE attrs->'color'='red';`
* install: `CREATE EXTENSION hstone`
* built into Rails 4.0.0

[http://hstore_demo.herokuapp.com](http://hstore_demo.herokuapp.com)

#### observations
#### bulkbag

* Try something new, shove it in the hstore
* hstore cannot nest hstores

* time: `*_at`
* int: `num_*` or `*_size`
* bool: `*?`

### 2. pvl8

##### why javascript?

* everywhere
* good part
* trusted language
* code.google.com/p/plv8
* Write JS for functions. INCREDIBLY FAST!
* documents
  * create an index on expressions
* json datatype! (postres 9.2)
* mustache.js
* json:select() [jsonselect.org](http://jsonselect.org)
  * css selectors to search your json trees
* rough edges still, but can be made better in the future

##### ruby

* all of the should be transparent
* what we have
  * datatype
  * language
* advanced db features
* locality

### [postgres.app](http://postgressapp.com)
