<!--
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements. See the [NOTICE](NOTICE) file
distributed with this work for additional information
regarding copyright ownership. The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# Apache Commons RDF

This fork of [Commons RDF](https://commons.apache.org/proper/commons-rdf/) aims to provide a common
library for [RDF 1.2](http://www.w3.org/TR/rdf12-concepts/) with implementations
for common Java RDF frameworks like [RDF4J](http://rdf4j.org/) and [Apache
Jena](http://jena.apache.org/).

The main motivation behind this simple library is to revise an historical
incompatibility issue between these toolkits. This library does not pretend to
be a generic API wrapping those libraries, but is a set of common Java interfaces
for the RDF 1.2 concepts, e.g. `IRI`, `BlankNode`, `TripleTerm`, `Graph`,
accompanied with unit test cases for their expected behavior, and a `simple`
implementation, which main purpose is to clarify the tests and interfaces.

In particular, Commons RDF aims to provide a type-safe, non-general API that
covers RDF 1.2. 

A diagram of the interfaces included in Commons RDF:

<a href="src/site/resources/images/class-diagram.png"><img height="400" src="src/site/resources/images/class-diagram.png" alt="Class diagram" /></a>

## Building

Building has been tested with [Apache Maven 3](http://maven.apache.org/download.cgi) and [Java 11 and up](https://github.com/apache/commons-rdf/blob/master/.github/workflows/maven.yml).

    $ mvn
    [INFO] Scanning for projects...
    [INFO] ------------------------------------------------------------------------
    [INFO] Reactor Build Order:
    [INFO] 
    [INFO] Commons RDF
    [INFO] Commons RDF: API
    [INFO] Commons RDF: Simple impl
    [INFO] 
    [INFO] Using the builder org.apache.maven.lifecycle.internal.builder.singlethreaded.SingleThreadedBuilder with a thread count of 1
    [INFO]                                                                         
    [INFO] ------------------------------------------------------------------------
    [INFO] Building Commons RDF 0.5.0
        ....
    [INFO] Installing /home/johndoe/src/commons-rdf/commons-rdf-api/target/commons-rdf-api-0.5.0-javadoc.jar to /home/johndoe/.m2/repository/org/apache/commons/commons-rdf/commons-rdf-api/0.5.0/commons-rdf-api-0.5.0-javadoc.jar
    [INFO] ------------------------------------------------------------------------
    [INFO] Reactor Summary:
    [INFO] 
    [INFO] Commons RDF ........................................ SUCCESS [  0.404 s]
    [INFO] Commons RDF: API ................................... SUCCESS [  0.031 s]
    [INFO] Commons RDF: Simple Implementation ................. SUCCESS [  0.010 s]
    [INFO] Commons RDF: Integration: RDF4j .................... SUCCESS [  0.012 s]
    [INFO] Commons RDF: Integration: Apache Jena .............. SUCCESS [  0.011 s]
    [INFO] Commons RDF: Integration: JSON-LD Java ............. SUCCESS [  0.009 s]
    [INFO] Commons RDF: Integration tests ..................... SUCCESS [  0.005 s]
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESS
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time: 7.718 s
    [INFO] Finished at: 2015-01-26T02:09:10+00:00
    [INFO] Final Memory: 22M/309M
    [INFO] ------------------------------------------------------------------------


To then use this build from your project, add to Maven (update `<version>` to match the Maven output):

    <dependency>
        <groupId>org.metalynq.commons</groupId>
        <artifactId>commons-rdf-api</artifactId>
        <version>0.6.0</version>
    </dependency>

.. and an equivalent `<dependency>` for the implementation you would like, e.g. `commons-rdf-simple`
or `commons-rdf-jena`.



