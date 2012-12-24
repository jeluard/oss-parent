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
    <version>2</version>
  </parent>

  <scm>
    <connection>scm:git:git@github.com:jeluard/....git</connection>
    <developerConnection>scm:git:git@github.com:jeluard/....git</developerConnection>
    <url>git@github.com:jeluard/....git</url>
  </scm>

  <build>
    <plugins>
      <!--
        Add this to check no wrong JDK API (i.e. from more recent version) is used.
        This is not necessary when using the right rt.jar as bootstrap classpath but this is a pain in practise.
        See:
          * https://blogs.oracle.com/darcy/entry/how_to_cross_compile_for
          * https://blogs.oracle.com/darcy/entry/bootclasspath_older_source
      -->
      <plugin>
        <groupId>org.codehaus.mojo</groupId>
        <artifactId>animal-sniffer-maven-plugin</artifactId>
      </plugin>
    </plugins>
  </build>

</project>
```
