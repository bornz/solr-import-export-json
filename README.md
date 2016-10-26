# solr-backup-restore-json

This is a simple command line application able to backup/restore a solr collection to/from a json file.

enjoy :)

- environment dependency: java 8 e maven

- list of parameters:

 -a,--actionType <arg>    action type [backup|restore]
 -d,--deleteAll <arg>     delete all documents before restore
 -D,--dryRun              dry run test
 -f,--filterQuery <arg>   filter Query during backup
 -h,--help                help
 -o,--output <arg>        output file
 -s,--solrUrl <arg>       solr url


With linux execute:
```
#!bash

  sudo apt-get update
  sudo apt-get remove openjdk-7-jdk
  sudo add-apt-repository ppa:openjdk-r/ppa
  sudo apt-get update
  sudo apt-cache search java | grep 8
  sudo apt-get install openjdk-8-jdk
  sudo apt-get install maven
  
  mvn clean package

```

- build 


```
#!bash
  mvn clean package

```

- help

  ./run.sh -h

- backup all documents into a json file

```
#!bash
  ./run.sh -s http://localhost:8983/solr/collection -a backup -o /tmp/collection.json

```

- restore documents from json

```
#!bash
  ./run.sh -s http://localhost:8983/solr/collection -a restore -o /tmp/collection.json 

```

- backup filtering documents, same as fq Solr parameter

```
#!bash
  ./run.sh -s http://localhost:8983/solr/collection -a backup -o /tmp/collection.json --filterQuery field:value

```

- restore documents from json but first delete all documents

```
#!bash
  ./run.sh -s http://localhost:8983/solr/collection -a restore -o /tmp/collection.json --deleteAll

```
