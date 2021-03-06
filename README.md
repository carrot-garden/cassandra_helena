Helena
======
Helena is a simple restful interface to an [Apache Cassandra](http://cassandra.apache.org) database.

This project is at an extremely early development phase, reading the source is the best way to figure our what's going on.

Warnings
--------

- There is no build tool yet. I'm just running this in Eclipse at this point.
- There are no javadocs yet.
- The API is read-only right now, read/write will be forthcoming though.
- Dependency management is manual right now.  See below.
- HelenaDaemon.java is barely more than a template for cusomization at this point.

Dependencies
------------

- [Restlet 2.0](http://www.restlet.org)
- [Hector 0.8](https://github.com/rantav/hector)

In addition to the Hector jars required on the classpath, you'll need the core restlet jar (org.restlet.jar) and also the jars required to make the converter service work.  I've only tested this with the Jackson jars providing a conversion to json.  Theoretically, anything that you can configure through the restlet converter service to convert Java Maps into some other variant should work.

To get the jackson extension to work, you'll need the following on your classpath:

- org.json.jar
- org.restlet.ext.jackson.jar
- org.restlet.ext.json.jar
- org.codehaus.jackson.core.jar
- org.codehaus.jackson.mapper.jar

HATEOAS Note
------------
Treat the keys of the JSON maps as the resource links.  They are absolute directory paths that are urls for data in cassandra.

TODO
----

- Read/Write capability
- Add example Authenticator/Authorizer
- Test variants other than json.
- Add more runtime integration options.
- Add search capability.
- Finish row paging mechanism.
- Add support for OrderedPartitioner?



