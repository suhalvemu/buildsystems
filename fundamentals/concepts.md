# Core Build System Concepts

Understanding these concepts will help you reason about any build system, not just the one you use today.

---

## Target

A named unit of work — a library, binary, test, or any artifact.

```python
# Bazel example
cc_binary(
    name = "hello",
    srcs = ["hello.cc"],
)
```

Every build system has a concept of a target, even if named differently (Make calls them "rules", Maven calls them "goals").

---

## Dependency Graph

Build systems model your code as a directed acyclic graph (DAG). Each target declares what it depends on. The build system resolves the order automatically.

```
app → [lib_a, lib_b]
lib_a → [util]
lib_b → [util]
```

This means:
- `util` is built once, reused by both `lib_a` and `lib_b`
- `app` is built last
- Unchanged nodes are skipped (incremental builds)

---

## Hermeticity

A hermetic build produces the same output given the same inputs — always, on any machine.

**Non-hermetic (bad):**
- Reads from `/usr/local/lib` (varies by machine)
- Depends on env vars set manually
- Network access during build

**Hermetic (good):**
- All dependencies declared explicitly
- Sandboxed execution
- No implicit inputs

Bazel is the strictest about hermeticity. Make is the least strict.

---

## Incremental Builds

Only rebuild what changed. The build system tracks inputs and outputs — if nothing changed, the cached result is used.

```
First build:  compile A, B, C → 45 seconds
Change only A:  compile A → 3 seconds (B and C reused from cache)
```

Poor incremental build support = slow CI = unhappy engineers.

---

## Remote Caching

Extend the cache beyond your local machine. CI builds push results to a shared cache. Developer builds pull from it.

```
Engineer A builds target X → pushes to cache
Engineer B builds target X → cache hit, skips build entirely
```

Tools: BuildBuddy, EngFlow, self-hosted (Bazel Remote Cache API).

---

## Remote Execution

Instead of running builds locally, send build actions to a fleet of remote workers. Massive parallelism — thousands of actions simultaneously.

Only Bazel, Buck2, and Pants support this properly.

---

## Reproducibility

Given the same source code and dependencies, the build output is byte-for-byte identical. Essential for:
- Security (verifiable builds)
- Debugging ("works on my machine" problems)
- Compliance (SLSA, SBOM requirements)

---

## Sandboxing

Each build action runs in isolation — no access to the filesystem beyond declared inputs. Prevents hidden dependencies from sneaking in.

Bazel sandboxes by default on Linux/macOS.

---

## Artifact

The output of a build action — a binary, JAR, container image, test result, generated file.

---

## BUILD Files

Configuration files that define targets and their dependencies. Every build system has its own format:

| Build System | Config File |
|---|---|
| Make | `Makefile` |
| Maven | `pom.xml` |
| Gradle | `build.gradle` / `build.gradle.kts` |
| Bazel | `BUILD` / `BUILD.bazel` |
| Buck2 | `BUCK` |
| Pants | `BUILD` |

---

## Summary

| Concept | One-line definition |
|---|---|
| Target | A named buildable unit |
| Dependency graph | The DAG of what depends on what |
| Hermeticity | Same inputs → same outputs, always |
| Incremental builds | Only rebuild what changed |
| Remote cache | Share build results across machines |
| Remote execution | Run build actions on remote workers |
| Reproducibility | Byte-for-byte identical outputs |
| Sandboxing | Isolated execution per build action |
