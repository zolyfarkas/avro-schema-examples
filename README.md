# avro-schema-examples

Showcase of using a maven repository as a Schema Repository.

Join the discussion on Gitter: [![Gitter chat](https://badges.gitter.im/zolyfarkas/spf4j-avro.png)](https://gitter.im/spf4j-avro/Lobby)

The examples here are built and published to:

  * schema parent: [ ![Download](https://api.bintray.com/packages/zolyfarkas/core/schema-parent-pom/images/download.svg) ](https://bintray.com/zolyfarkas/core/schema-parent-pom/_latestVersion)
  
  * test schema common: [ ![Download](https://api.bintray.com/packages/zolyfarkas/core/test-schema-common/images/download.svg) ](https://bintray.com/zolyfarkas/core/test-schema-common/_latestVersion)
  
  * test schema: [ ![Download](https://api.bintray.com/packages/zolyfarkas/core/test-schema/images/download.svg) ](https://bintray.com/zolyfarkas/core/test-schema/_latestVersion)  

Demonstrates:

  * Compose data models using maven dependency framework. Use the maven to re-use, version, release and publish avro data models. (test-schema -> test-schema-common)

  * Validate avro schemas ([extensile](http://www.spf4j.org/spf4j-avro-components/maven-avro-schema-plugin/avro-validate-mojo.html)). (documentation, compatibility with previously released versions...)

  * Add a unique ID to the schemas (mvnId = "group:artifact:version:id")

  * Generate and publish java classes. (publishing for other languages can se set up) (@Immmutable support, @Nullable/@Nonnull) [see](https://bintray.com/zolyfarkas/core/download_file?file_path=org%2Fspf4j%2Favro%2Fexamples%2Ftest-schema%2F1.1%2Ftest-schema-1.1.jar)

  * Generate package and publish the avro schemas, [see](https://bintray.com/zolyfarkas/core/download_file?file_path=org%2Fspf4j%2Favro%2Fexamples%2Ftest-schema%2F1.1%2Ftest-schema-1.1-avsc.jar).
  
  * Generate and publish avrodoc, [see](https://bintray.com/zolyfarkas/core/download_file?file_path=org%2Fspf4j%2Favro%2Fexamples%2Ftest-schema%2F1.1%2Ftest-schema-1.1-avrodoc.jar).
  

The pom file for a schema project is as simple as (see example from this repo for more detail):

    <?xml version="1.0" encoding="UTF-8"?>
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"       xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
      <modelVersion>4.0.0</modelVersion>
      <groupId>org.spf4j.avro.examples</groupId>
      <artifactId>test-schema</artifactId>
      <packaging>jar</packaging>
      <version>1.5-SNAPSHOT</version>
      <name>${project.artifactId}-${project.version}</name>
      <description>Avro schema example</description>
       <parent>
         <groupId>org.spf4j.avro</groupId>
         <artifactId>schema-parent-pom</artifactId>
         <version>LATEST</version>
       </parent>
      <properties>
            <avro.version>LATEST</avro.version> <!-- change to use your own fork or official -->
            <avro.allowUndefinedLogicalTypes>false</avro.allowUndefinedLogicalTypes>
      </properties>
      <dependencies>
        <dependency> <!-- this schema will re-use schema's from this dependency -->
            <groupId>org.spf4j.avro.examples</groupId>
            <artifactId>test-schema-common</artifactId>
            <version>LATEST</version>
        </dependency>
      </dependencies>
    </project>

The bulk of the functionality is implemented using:
 * [spf4j maven-avro-schema-plugin](http://www.spf4j.org/spf4j-avro-components/maven-avro-schema-plugin/index.html)
 * [avrodoc](https://github.com/ept/avrodoc) + [frontend-maven-plugin](https://github.com/eirslett/frontend-maven-plugin)
