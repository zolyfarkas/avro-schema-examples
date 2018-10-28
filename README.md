# avro-schema-examples

Showcase of using a maven repository as a Schema Repository.

Show cases:

  * Compose data models using maven dependency framework. Use the maven release process to release and version avro data models. (test-schema -> test-schema-common)

  * Validate avro schemas ([extensile](http://www.spf4j.org/spf4j-avro-components/maven-avro-schema-plugin/avro-validate-mojo.html)). (documentation, compatibility with previously released versions)

  * Add a unique ID to the schemas (mvnId = "group:artifact:version:id")

  * Generate and publish java classes. (@Immmutable support, @Nullable/@Nonnull) [see](https://bintray.com/zolyfarkas/core/download_file?file_path=org%2Fspf4j%2Favro%2Fexamples%2Ftest-schema%2F1.1%2Ftest-schema-1.1.jar)

  * Generate package and publish the avro schemas, [see](https://bintray.com/zolyfarkas/core/download_file?file_path=org%2Fspf4j%2Favro%2Fexamples%2Ftest-schema%2F1.1%2Ftest-schema-1.1-avsc.jar).
  
  * Generate and publish avrodoc, [see](https://bintray.com/zolyfarkas/core/download_file?file_path=org%2Fspf4j%2Favro%2Fexamples%2Ftest-schema%2F1.1%2Ftest-schema-1.1-avrodoc.jar).
  
The examples here are built and published to: [ ![Download](https://api.bintray.com/packages/zolyfarkas/core/avro-schema-parent/images/download.svg) ](https://bintray.com/zolyfarkas/core/avro-schema-parent/_latestVersion)
