# Pants

> Fast, scalable build system for Python, Go, Java, and Scala monorepos.

---

## What is Pants?

Pants (v2) is an open-source build system designed for monorepos, with especially strong Python support. It features fine-grained invalidation, dependency inference, and built-in support for formatters, linters, and test runners.

---

## When to Use Pants

Use Pants when:
- Your monorepo is primarily Python
- You want automatic dependency inference (no manual BUILD file maintenance)
- You need fast, incremental test runs at scale

---

## Key Feature: Dependency Inference

Unlike Bazel, Pants can infer dependencies automatically from import statements:

```python
# Pants reads this import and adds the dependency automatically
from mycompany.utils import helper
```

No need to manually maintain BUILD files for every import.

---

## Resources

- [Pants Official Docs](https://www.pantsbuild.org/)
- [Pants vs Bazel](https://www.pantsbuild.org/docs/bazel)
- [Pants GitHub](https://github.com/pantsbuild/pants)
- [Why Pants](https://www.pantsbuild.org/docs/why-pants)
