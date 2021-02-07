# Maven Sample Project

maven SCM demo project.

## Usage

- Given an exmaple of `pom.xml` below:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project>
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.packt</groupId>
  <artifactId>jose</artifactId>
  <version>1.0.0</version>

  <scm>
    <connection>
      scm:git:https://github.com/ring2003/maven-sample.git
    </connection>
    <developerConnection>
      scm:git:https://github.com/ring2003/maven-sample.git
    </developerConnection>
    <url>
      https://github.com/ring2003/maven-sample.git
    </url>
  </scm>

  <dependencies>
    <dependency>
      <groupId>com.nimbusds</groupId>
      <artifactId>nimbus-jose-jwt</artifactId>
      <version>2.26</version>
    </dependency>
  </dependencies>

  <build>
    <outputDirectory>${basedir}/target/classes</outputDirectory>
    <sourceDirectory>${basedir}/target/checkout/src</sourceDirectory>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-scm-plugin</artifactId>
        <version>1.11.2</version>
      </plugin>
    </plugins>
  </build>
</project>
```

- Then run command:

```bash
mvn scm:checkout compile
java -cp ${basedir}/target/classes org.exmaple.App
```