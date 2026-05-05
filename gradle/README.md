# Gradle

> Fast, flexible build automation for JVM, Android, and beyond.

---

## What is Gradle?

Gradle is a modern build automation tool that combines the best of Maven (dependency management, conventions) with the flexibility of a full programming language (Groovy or Kotlin DSL). It is the official build tool for Android and widely used for JVM projects.

---

## When to Use Gradle

Use Gradle when:
- You're building Android apps
- You want faster builds than Maven with build caching
- You need custom build logic beyond what Maven conventions allow
- You're on the JVM ecosystem but want more flexibility

Don't use Gradle when:
- You have a truly large-scale monorepo (use Bazel)
- Your team is heavily invested in Maven conventions
- You need strict hermetic builds

---

## Core Concepts

### build.gradle.kts (Kotlin DSL)
```kotlin
plugins {
    kotlin("jvm") version "1.9.0"
}

dependencies {
    implementation("org.jetbrains.kotlinx:kotlinx-coroutines-core:1.7.0")
    testImplementation(kotlin("test"))
}

tasks.test {
    useJUnitPlatform()
}
```

### Build Cache
Gradle has a built-in build cache — outputs are cached locally and optionally remotely:
```bash
./gradlew build --build-cache
```

### Incremental Builds
Gradle tracks task inputs/outputs and skips tasks whose inputs haven't changed.

---

## Gradle vs Maven

| | Gradle | Maven |
|---|---|---|
| Config language | Groovy/Kotlin DSL | XML |
| Build speed | Faster (caching, incremental) | Slower |
| Flexibility | High | Low (convention-bound) |
| Android | Official tool | Not supported |
| Learning curve | Medium | Low |
| Ecosystem maturity | High | Very high |

---

## Resources

- [Gradle Official Docs](https://docs.gradle.org) — comprehensive
- [Gradle Build Cache](https://docs.gradle.org/current/userguide/build_cache.html)
- [Migrating from Maven to Gradle](https://docs.gradle.org/current/userguide/migrating_from_maven.html)
- [Gradle vs Bazel](https://bazel.build/migrate/gradle) — when to choose Bazel
