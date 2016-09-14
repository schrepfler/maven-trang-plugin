This simple plugin invokes Trang on a set of input files to
    produce an output file.  For more information about Trang, see
    http://www.thaiopensource.com/relaxng/trang.html.

Usage

You should specify the version in your project's plugin configuration:

<project>
  ...
  <build>
    <!-- To define the plugin version in your parent POM -->
    <pluginManagement>
      <plugins>
        <plugin>
          <groupId>com.williamhill.trafalgar</groupId>
          <artifactId>maven-trang-plugin</artifactId>
          <version>1.0-SNAPSHOT</version>
        </plugin>
        ...
      </plugins>
    </pluginManagement>
    <!-- To use the plugin goals in your POM or parent POM -->
    <plugins>
        <plugin>
          <groupId>com.williamhill.trafalgar</groupId>
          <artifactId>maven-trang-plugin</artifactId>
          <version>1.0-SNAPSHOT</version>
        </plugin>
      ...
    </plugins>
  </build>
  ...
</project>


Trang goal

This example will convert src/main/rnc/schema.rnc to XSD format and place the output in target/trang/schema.xsd.

<project>
  ...
  <build>
    <plugins>
      <plugin>
        <groupId>com.williamhill.trafalgar</groupId>
        <artifactId>maven-trang-plugin</artifactId>
        <version>1.0</version>
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

