A parent POM for my Github based projects.

# Usage

Use following snippet as a basis for a new project:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <artifactId>...</artifactId>
  <version>1.0-SNAPSHOT</version>

  <name>...</name>
  <description>...</description>

  <parent>
    <groupId>com.github.jeluard</groupId>
    <artifactId>oss-parent</artifactId>
    <version>6</version>
  </parent>

  <scm>
    <connection>scm:git:git@github.com:jeluard/....git</connection>
    <developerConnection>scm:git:git@github.com:jeluard/....git</developerConnection>
    <url>git@github.com:jeluard/....git</url>
  </scm>

</project>
```

# Release

To do a complete release:

```
mvn clean install
mvn release:prepare
mvn release:perform
mvn nexus-staging:release
```

You might want to run following before:

```
mvn animal-sniffer:check
mvn license:check //mvn license:format to apply proper license
```
