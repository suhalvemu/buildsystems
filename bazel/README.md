# Bazel

> The build system for large-scale, multi-language monorepos. Fast, correct, and reproducible.

---

## What is Bazel?

Bazel is an open-source build and test tool developed by Google (originally called Blaze). It is designed for large codebases that need:

- Fast incremental builds
- Strict reproducibility
- Multi-language support (Go, Python, Java, C++, containers, and more)
- Remote caching and remote execution

---

## When to Use Bazel

Use Bazel when:
- Your repo has 20+ engineers or multiple languages
- CI is slow and you need incremental builds
- You need reproducible, hermetic builds (compliance, security)
- You're building container images at scale
- You want remote caching across your team

Don't use Bazel when:
- You have a small, single-language project
- Your team isn't ready for the learning curve
- You don't have someone to own the build infrastructure

---

## Contents

| Doc | What it covers |
|---|---|
| [Core Concepts](./concepts.md) | Targets, rules, BUILD files, WORKSPACE, bzlmod |
| [Getting Started](./getting-started.md) | Install, first BUILD file, first build |
| [Monorepo Guide](./monorepo.md) | Structuring a multi-language monorepo |
| [Remote Caching](./remote-caching.md) | Setup with BuildBuddy, EngFlow, self-hosted |
| [bzlmod](./bzlmod.md) | Modern dependency management (WORKSPACE replacement) |
| [Container Images](./containers.md) | Building OCI images with rules_oci |
| [CI/CD Integration](./ci-cd.md) | GitHub Actions, Jenkins, CI best practices |
| [Migration Guide](./migration-guide.md) | Migrating from Make/Maven/Gradle to Bazel |
| [Resources](./resources.md) | Best external learning resources |

---

## Companies Using Bazel

| Company | Scale |
|---|---|
| Google | Entire company codebase |
| Uber | Multi-language monorepo |
| Spotify | Backend services |
| Stripe | Payments infrastructure |
| Twitter/X | Core platform |
| Dropbox | Python + Go monorepo |
| LinkedIn | Java monorepo |
| Netskope | CI/CD, container images |
