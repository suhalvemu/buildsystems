# Maven

> Convention-over-configuration build tool for the Java ecosystem.

---

## What is Maven?

Maven is a build automation and project management tool primarily for Java projects. It uses a `pom.xml` (Project Object Model) file to describe the project, its dependencies, and build lifecycle.

Created in 2004 as an improvement over Ant. Still the dominant build tool in Java enterprise environments.

---

## When to Use Maven

Use Maven when:
- You're in the Java/JVM ecosystem
- You want strong conventions and a standard project structure
- You need a mature, stable dependency management system
- Your team is familiar with Java enterprise standards

Don't use Maven when:
- You need flexible, custom build logic (use Gradle)
- You have a large monorepo (use Bazel)
- Build speed is critical (Maven is slow vs Gradle/Bazel)

---

## Core Concepts

### Standard Directory Layout
```
my-project/
├── pom.xml
└── src/
    ├── main/
    │   └── java/
    └── test/
        └── java/
```

### Build Lifecycle
```
validate → compile → test → package → verify → install → deploy
```

### Example pom.xml
```xml
<project>
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.example</groupId>
  <artifactId>my-app</artifactId>
  <version>1.0</version>

  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.13</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
</project>
```

---

## Resources

- [Maven Official Docs](https://maven.apache.org/guides/) — official guide
- [Maven in 5 Minutes](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html) — quickstart
- [Maven Repository](https://mvnrepository.com) — find dependencies
- [Maven vs Gradle](https://gradle.org/maven-vs-gradle/) — honest comparison
