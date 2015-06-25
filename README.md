# ECL 2 License for Maven License Plugin

This is a packaging of the ECL 2 license for the maven license plugin on codehaus. This allows projects to update
their licenses automatically as part of the build and not require each project to have it's own copy of the license.

http://www.mojohaus.org/license-maven-plugin

## Usage 

To use the maven license plugin with the ECL license add the following plugin to the `pom.xml`

```
<plugin>
  <groupId>org.codehaus.mojo</groupId>
  <artifactId>license-maven-plugin</artifactId>
  <version>1.8</version>
  <configuration>
      <licenseName>ecl_v2</licenseName>
      <licenseResolver>classpath://org/sakaiproject</licenseResolver>
  </configuration>
  <executions>
      <execution>
          <goals>
              <goal>update-file-header</goal>
          </goals>
          <phase>process-sources</phase>
      </execution>
  </executions>
  <dependencies>
      <dependency>
          <groupId>org.sakaiproject.license</groupId>
          <artifactId>ecl-license</artifactId>
          <version>1.0</version>
      </dependency>
  </dependencies>
</plugin>
```