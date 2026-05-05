# Monorepos vs Polyrepos

One of the most debated architectural decisions in software engineering. Here's an honest breakdown.

---

## What is a Monorepo?

All your code — every service, library, tool — lives in a single repository.

```
company/
├── services/
│   ├── auth/
│   ├── payments/
│   └── notifications/
├── libraries/
│   ├── common/
│   └── utils/
└── tools/
    └── ci/
```

Used by: Google, Meta, Twitter, Uber, Spotify, Stripe.

---

## What is a Polyrepo?

Each service or library has its own repository.

```
github.com/company/auth-service
github.com/company/payments-service
github.com/company/common-lib
```

Used by: Most small-to-medium companies, most open-source projects.

---

## Tradeoffs

| | Monorepo | Polyrepo |
|---|---|---|
| **Code sharing** | Easy — just import | Requires publishing packages |
| **Atomic changes** | One PR touches everything | Cross-repo PRs are painful |
| **CI speed** | Needs smart build tools (Bazel) | Each repo CI is independent |
| **Tooling complexity** | High — needs Bazel/Pants/Nx | Low — standard tools work |
| **Discoverability** | Everything in one place | Scattered across repos |
| **Access control** | Harder to restrict per team | Easy — per-repo permissions |
| **Onboarding** | One clone, full picture | Multiple repos to find/clone |
| **Dependency hell** | Eliminated internally | Version conflicts common |

---

## The Catch With Monorepos

A monorepo without the right build tooling is a nightmare:
- `git clone` takes forever
- CI rebuilds everything on every change
- IDEs struggle with scale

**This is why Bazel exists.** Google invented it specifically because their monorepo outgrew every other build tool.

---

## When to Use a Monorepo

- Multiple teams sharing libraries or types
- You want atomic cross-service changes
- You're willing to invest in build tooling (Bazel, Pants, Nx, Turborepo)
- You value a single source of truth

## When to Use a Polyrepo

- Independent services with clear ownership
- Different release cycles per service
- Small team, low coupling between services
- You want simplicity over coordination

---

## Real-World Examples

| Company | Approach | Build Tool |
|---|---|---|
| Google | Monorepo (entire company) | Bazel (Blaze) |
| Meta | Monorepo | Buck2 |
| Twitter/X | Monorepo | Bazel |
| Uber | Monorepo | Bazel |
| Spotify | Monorepo (partial) | Bazel |
| Netflix | Polyrepo | Gradle |
| Amazon | Polyrepo (mostly) | Various |

---

## Bottom Line

Monorepo is not inherently better than polyrepo — it's a tooling investment decision. If your team isn't ready to adopt Bazel or Pants, a monorepo will slow you down, not speed you up.
