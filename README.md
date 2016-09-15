trang-maven-plugin
=

[![Build Status](https://travis-ci.org/schrepfler/trang-maven-plugin.svg?branch=master)](https://travis-ci.org/schrepfler/trang-maven-plugin)

This simple plugin invokes the Trang library on a set of xml schema input files to
    and produces a translated schema as output.  For more information about Trang, see
    http://www.thaiopensource.com/relaxng/trang.html.

Usage
--

You should specify the version in your project's plugin configuration:

```xml
<project>
  ...
  <build>
    <!-- To use the plugin goals in your POM or parent POM -->
    <plugins>
        <plugin>
          <groupId>net.sigmalab.trang</groupId>
          <artifactId>trang-maven-plugin</artifactId>
          <version>1.2</version>
        </plugin>
      ...
    </plugins>
  </build>
  ...
</project>
```


Trang goal

This example will convert src/main/rnc/schema.rnc to XSD format and place the output in target/trang/schema.xsd.

```xml
<project>
  ...
  <build>
    <plugins>
      <plugin>
        <groupId>net.sigmalab.trang</groupId>
        <artifactId>trang-maven-plugin</artifactId>
        <version>1.2</version>
        <executions>
          <execution>
            <id>trang-convert</id>
            <phase>generate-sources</phase>
            <goals>
              <goal>trang</goal>
            </goals>
          </execution>
        </executions>
        <configuration>
          <inputFiles>
            <inputFile>src/main/rnc/schema.rnc</inputFile>
          </inputFiles>
          <outputFileName>schema.xsd</outputFileName>
        </configuration>
      </plugin>
    </plugins>
  </build>
   ...
</project>
```