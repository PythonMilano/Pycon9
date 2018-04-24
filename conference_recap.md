# Pycon 9 recap.
Ok, it was great. The skype call to the Concordia Antartic Base last Sunday was simply wonderful!

## Friday

### (EN) Scaling your Data Infrastructure. Attendee: keobox.
This was a collection of practices about Data Science projects.
This was one of the few talk I followed in the Pydata Track, and to say the truth it was not so easy for me to follow, since I'm not in the field, unfortunately.
#### Takeaways
- Is possible to execute python code using Atom and [Hydrogen](https://atom.io/packages/hydrogen) as an alternative to use a Jupyter Notebook.
- Some issues about scaling when we are in presence of a lot of data were listed. Basically they are about how to storage a lot of data and how to compute them.
- For storage, "parquet" files storage may help.
- Some solution of threating a computation of a lot of data are the use of "chuncks" or "partial fit".
- An alternative to Spark may be [Ray](https://github.com/ray-project/ray)
- But how put model on production? The lesson learned is to use docker container as much as possible.
- The last advice was to give a look at [Cassiny](https://docs.cassiny.io/)

### (EN) Unveiling the potential of graph databases with Python and Neo4j. Attendee: keobox.
This was an interesting talk about Neo4J, a graph database.
#### Takeaways
- Neo4J, basically is a NoSql database, but it stores a graph structure instead of keys,values.
- It implements index free adjacency, so that graph navigation it's quick.
- The DDL language is "cypher" this language describes what are the node fields and what are the relationships among nodes.
- Neo4J is [ACID](https://en.wikipedia.org/wiki/ACID)
- Neo4J has an official driver called [Bolt](https://neo4j.com/docs/api/python-driver/current/) that permits to connect and send "cypher" code to the server.
- There're several non official projects: py2neo and pypher that wraps "cypher" with something more python like.
- Bidirectional relationships must be inserted and modelled with two unidirectional relationships.

### (IT) Elastic by Examples. Attendee: keobox
I would say that this presentation lacks the examples, it was more an introduction to the elasticsearch stack, the interesting part was about use cases that elasticsearch can cope.
#### Takeaways
- There's new "Beats" data ingestor that is pluggable and lighter than logstash. Apart this I did not get the difference beetween the two.
- The ES-Hadoop connector is now open source.
- Official python clients to connect to an ES cluster are: elastic-search.py, elasticsearch-dsl, django-elastic-search-dsl.
#### Elastic search use cases.
- Web app search engine. This is the main purpose of ES.
- Security Forensic Analysis. Is possible to do this with the help of the "Alerting tool" in XPACK, the ES commercial stack or with some opensource projects like [elastalert](https://github.com/Yelp/elastalert) developed by Yelp. Another project is [VulnWhisperer](https://github.com/austin-taylor/VulnWhisperer), but it's Python 2.
- Graph visualization. This is XPACK only and is useful for "social" analysis.
- Centralized Log Analysis.
- GeoSearch and Security. This is in XPACK too.
- Automatic Performance Analysis or APM. This is released for open source and supports Django, Flask and Node in GA release and Java as Beta release. Beta... ah ah!

### (IT) Introduzione a Zerynth: Python per microcontrollori e applicazioni IoT. Attendee: keobox.
This was a presentation about [Zerynth](https://www.zerynth.com/) an IoT platform that consists of an embeddable Python VM, like MicroPython, and a complete toolchain with SDK.

### (IT) Monitora le performance della tua applicazione Python Flask con ElasticSearch e Kibana. Attendee: keobox
This was an introduction, with code examples, about how to use the APM cababilities of the ES stack, given you have an ES cluster.
#### Takeways
- There's an APM server is an opensource project written in Go, this converts the performance information collected by APM agents into data to send to an ES cluster.
- The APM agents, are open source too, these are libraries written in different languages used to send performance data to APM servers. These agents are available for Django, Flask and NodeJs. Java support is Beta.
- For flask is possible to install with pip the elastic-apm-flask package.
