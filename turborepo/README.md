# Turborepo

> High-performance build system for JavaScript and TypeScript monorepos.

---

## What is Turborepo?

Turborepo is a build system optimized for JavaScript/TypeScript monorepos. It understands the task graph of your packages, caches outputs locally and remotely, and runs tasks in parallel.

Acquired by Vercel in 2021. Now widely used in the JS ecosystem.

---

## When to Use Turborepo

Use Turborepo when:
- Your monorepo is JavaScript or TypeScript
- You use npm/yarn/pnpm workspaces
- You want fast CI with remote caching (Vercel Remote Cache)
- You don't need the complexity of Bazel for a JS project

---

## Core Concepts

### turbo.json
```json
{
  "pipeline": {
    "build": {
      "dependsOn": ["^build"],
      "outputs": ["dist/**"]
    },
    "test": {
      "dependsOn": ["build"]
    },
    "lint": {}
  }
}
```

### Remote Cache
```bash
npx turbo build --remote-cache-timeout=30
```

---

## Resources

- [Turborepo Docs](https://turbo.build/repo/docs)
- [Getting Started](https://turbo.build/repo/docs/getting-started/create-new)
- [Turborepo vs Nx](https://turbo.build/repo/docs/getting-started/existing-monorepo)
