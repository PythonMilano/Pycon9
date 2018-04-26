# Pycon 9 recap.
Ok, it was great. The skype call to the Concordia Antartic Base last Sunday was simply wonderful!

## Friday

### (EN) Scaling your Data Infrastructure. Attendee: keobox.
This was a collection of practices about Data Science projects.
This was one of the few talks I followed in the Pydata Track, and to say the truth it was not so easy for me to follow, since I'm not in the field, unfortunately.
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

### (EN) Python and the automatic astromical photografy. Attendee: keobox
We already seen this in PyMi in November 2017, but it was a pleasure to listen this again during the PyBeer!
Showing this during the PyBeer was necessary since we need the dark, since this talk was again a big demo of AstroScheduler, the Python application that Nicola wrote to make his own astronomical observatoty automatic: this means the observatory is able to take pictures of Galaxies and other astronomical objects "alone", drive by a script. Great talk. The only issue was that the venue was too noisy and not all attendands were able to listen well.
#### Takeaways
- Everything is possible!

## Saturday

### (EN) Python, Gravitational Waves and the Dawn of Multimessenger Astrophysics. Attendee: keobox
In this keynote we were updated about the state of the art in the gravitational waves detectors field: these are now the existent detectors LIGO, Extended LIGO and VIRGO.
VIRGO is the european community detector.
After a description about the detector charateristics, like laser power beetween the arms of the interferometer: 200 W (Wow!) we saw how Python is used in the project. I would say it's used a lot, and it was very interesting to listen.
Then we arrive at the core of the keynote: VIRGO is now part of a network of "instruments" able to see and correlate big astrophysical events like gravitational waves or gamma ray bursts because now these events are seen by multiple detectors, so they can be used to enforce the validation of such events.

### (EN) Testing Thousand of Python Projects Every Day. Attendee: keobox
This keynote was about Openstack development process and tools used during the development.
Openstack project is actually a collection of interrelated projects: Nova, Neutron etc. All these pieces have to work together.
After a entertaining description about the Openstack community "federated" development process, the keynote drifted to describe [Zull](https://docs.openstack.org/infra/zuul/) a continuos intergration tool specifically designed to manage a project composed of many interrelated projects like Openstack is.
#### Takeaways
- I Learned something about Project "Gating".
- Zull uses ansible for job configuration... Wow!

### (EN) How to use Web Sockets in Python. Attendee: keobox
This talk was about web sockets and how to deal with them w/ Python.
#### Takeaways
- Web Sockets are native Javascript stuff, use different protocol over port 80. No JS libraries are involved in this.
- Web Sockets have their own use cases like multiplayer games, tracking systems or chats, are not intended like a HTTP replacement.
- Web Sockets have cons: no caching possible, different error handling respect to HTTP, no HTTP states.
In backend Python side Web Sockets are implemented by:
- Twisted
- tornado.websockets
- Django channels: ASGI Asyncronous Server Gateway Interface, is a superset of WSGI.
Some code examples were shared with the audience.

### (EN) Writing and deploying serverless application w/ Python. Attendee: keobox.
An introduction to AWS Lambdas with a (slide) walkthrough about how to put in place a Python Lambda.
Then a brief introduction about [Zappa](https://www.zappa.io/).
#### Takeaways
- AWS Lambda now supports both Python 2 and Python 3.

### (IT) GraphQL in Python. Attendee: keobox
GraphQL is a Facebook's [specification](http://facebook.github.io/graphql/October2016/) that aims to resolve some issues using REST APIs.
These issues are:
- Avoid N+1 query problem when not all data of an endpoint are needed.
- Avoid the existence of sligthly different REST APIs to request sligthly different things.
- Often REST APIs return too much data respect what the client needs, is difficult to filter information.
#### Takeaways
- W/ GraphQL is easier to ask just what is needed.
- Is an alternative to REST.
- There's type enforcing.
- The operation are: "query", "mutation" and "subscription".
- Is possible to use Web Sockets as transport.
- The "mutation" operation use a sigle POST /graphql endpoint, and this is not cache friendly.
- Python is used in backend, the SW packages are graphene, graphene-django.
#### GraphQL cons
- Authentication is not in the specification.
- Authorization and Permissions, the same.
- Is possible to create inefficient queries on purpose, that take a lot of time to execute, as a DOS attacks.
- Is not easy to put in place a transparent cache system with GraphQL, but is possible to have in application caching using Data Loaders.
Some generic advices to overcome the Cons were provided during the talk, but I have an advice in this case.
Look at this [talk](https://www.youtube.com/watch?v=Q8Fhyd6EQYY) I saw at codemotion Milan, 2017.
This is a guy who works at Yelp and he shares advices about some solutions to GraphQL Cons, the slide are [here](https://www.slideshare.net/Codemotion/tomer-elmalem-graphql-apis-rest-in-peace-codemotion-milan-2017).
As a final comment, what in the slides is called Spectre, now is called [Casper](https://github.com/Yelp/casper) and is the caching system used by Yelp.