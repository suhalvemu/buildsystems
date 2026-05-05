# Build Systems — One Stop Resource

A comprehensive, opinionated reference for understanding, choosing, and using build systems — from Make to Bazel. Built by a practitioner, not a doc scraper.

> If you're migrating to Bazel, evaluating build systems for a monorepo, or just trying to understand the landscape — this is for you.

---

## What's Inside

| Section | What you'll find |
|---|---|
| [Fundamentals](./fundamentals/) | What build systems are, core concepts, how to choose |
| [Make](./make/) | Classic rule-based builds for C/C++ and scripting |
| [CMake](./cmake/) | Cross-platform build configuration |
| [Maven](./maven/) | Convention-based Java builds |
| [Gradle](./gradle/) | Modern JVM builds and Android |
| [Bazel](./bazel/) | Large-scale monorepos, reproducible builds, CI/CD |
| [Buck2](./buck2/) | Meta's open-source build system |
| [Pants](./pants/) | Python monorepo builds |
| [Turborepo](./turborepo/) | JavaScript/TypeScript monorepos |
| [Nx](./nx/) | Full-stack monorepo tooling |

---

## Quick Comparison

| Build System | Language Ecosystem | Monorepo | Remote Cache | Learning Curve | Best For |
|---|---|---|---|---|---|
| **Make** | C/C++, Any | No | No | Low | Small native projects |
| **CMake** | C/C++ | No | No | Medium | Cross-platform C/C++ |
| **Maven** | Java | Partial | No | Medium | Java enterprise |
| **Gradle** | JVM, Android | Partial | Yes | Medium | Modern JVM, Android |
| **Bazel** | Multi-language | Yes | Yes | High | Large monorepos, CI at scale |
| **Buck2** | Multi-language | Yes | Yes | High | Meta-scale monorepos |
| **Pants** | Python, Java, Go | Yes | Yes | Medium | Python monorepos |
| **Turborepo** | JS/TS | Yes | Yes | Low | JS/TS monorepos |
| **Nx** | JS/TS, Any | Yes | Yes | Medium | Full-stack monorepos |

---

## How to Choose

```
Is your codebase large (50+ engineers or multiple languages)?
├── Yes → Do you need strict reproducibility and remote caching?
│         ├── Yes → Bazel (or Buck2 if Meta ecosystem)
│         └── No  → Gradle (JVM) / Pants (Python) / Turborepo (JS)
└── No  → What's your primary language?
          ├── C/C++  → Make or CMake
          ├── Java   → Maven or Gradle
          ├── JS/TS  → Turborepo or Nx
          └── Python → Pants or just Make
```

---

## Who This Is For

- Engineers evaluating build systems for a growing codebase
- Teams planning a Bazel migration
- Engineers new to monorepos
- Anyone who wants to understand what's under the hood of their CI

---

## Contributions

Found something wrong or missing? PRs welcome.
Each build system section follows the same structure:
- Overview & when to use
- Core concepts
- Working examples
- Curated resources

---

## Author

Built by [Suhal Vemu](https://www.linkedin.com/in/suhalvemu) — Senior Software Engineer specializing in Build Infrastructure and Engineering Productivity.

- GitHub: [suhalvemu](https://github.com/suhalvemu)
- Bazel OSS contributor: [rules_oci#893](https://github.com/bazel-contrib/rules_oci/pull/893)
