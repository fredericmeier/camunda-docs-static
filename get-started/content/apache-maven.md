---

title: 'Apache Maven Coodinates'
weight: 60

menu:
  main:
    name: "Apache Maven"
    identifier: "get-started-maven"
    pre: "The most commonly used Apache Maven Coordinates for Camunda."

---

This page lists the most commonly used Apache Maven Coordinates for Camunda.

Most Camunda artifacts are pushed to [maven central](http://search.maven.org/#browse%7C-1675593179).


# Camunda Bom (Bill of Materials)

## Community Edition:

```xml
<dependency>
  <groupId>org.camunda.bpm</groupId>
  <artifactId>camunda-bom</artifactId>
  <version>7.4.0</version>
  <scope>import</scope>
  <type>pom</type>
</dependency>
```

## Enterprise Edition:

```xml
<dependency>
  <groupId>org.camunda.bpm</groupId>
  <artifactId>camunda-bom</artifactId>
  <version>7.4.0-ee</version>
  <scope>import</scope>
  <type>pom</type>
</dependency>
```

{{< note title="Use the BOM!" class="info" >}}
  Please import the Camunda BOM if you use multiple Camunda projects. The BOM defines versions for all Camunda projects. This way it is ensured that no incompatible versions are imported.
{{< /note >}}


# Camunda Engine

```xml
<dependency>
  <groupId>org.camunda.bpm</groupId>
  <artifactId>camunda-engine</artifactId>
</dependency>
```


# Camunda Engine Spring Integration

```xml
<dependency>
  <groupId>org.camunda.bpm</groupId>
  <artifactId>camunda-engine-spring</artifactId>
</dependency>
```


# Camunda Engine CDI Integration

```xml
<dependency>
  <groupId>org.camunda.bpm</groupId>
  <artifactId>camunda-engine-cdi</artifactId>
</dependency>
```


# Process Application Ejb Client

```xml
<dependency>
  <groupId>org.camunda.bpm.javaee</groupId>
  <artifactId>camunda-ejb-client</artifactId>
</dependency>
```


# Camunda Nexus

## Community Edition:

```xml
<repositories>
  <repository>
    <id>camunda-bpm-nexus</id>
    <name>camunda-bpm-nexus</name>
    <url>
      https://app.camunda.com/nexus/content/groups/public
    </url>
  </repository>
</repositories>
```

## Enterprise Edition:

```xml
<repositories>
  <repository>
    <id>camunda-bpm-nexus</id>
    <name>camunda-bpm-nexus</name>
    <url>
      https://app.camunda.com/nexus/content/repositories/camunda-bpm-ee
    </url>
  </repository>
</repositories>
```


# Other Camunda Modules:

* [DMN Engine](/manual/latest/user-guide/dmn-engine/embed/#maven-coordinates)
* [Camunda Spin](/manual/latest/reference/spin)
* [Camunda Connect](/manual/latest/reference/connect/#maven-coordinates)
* [Templating Engines](/manual/latest/user-guide/process-engine/templating/#install-a-template-engine-for-an-embedded-process-engine)
