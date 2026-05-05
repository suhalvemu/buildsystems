# Make

> The original build system. Simple, universal, and still widely used after 50 years.

---

## What is Make?

Make is a build automation tool that determines which parts of a program need to be recompiled and issues commands to recompile them. It reads a file called `Makefile` that describes the relationships between files.

Originally created in 1976. Still the most common build tool for C/C++ projects and shell-based automation.

---

## When to Use Make

Use Make when:
- You have a small-to-medium C/C++ project
- You need simple, scriptable build automation
- You want zero tooling dependencies
- You're writing shell-based task runners (lint, test, deploy)

Don't use Make when:
- Your project has multiple languages
- You need dependency management
- You have a large team that needs reproducible builds
- You're building a monorepo

---

## Core Concepts

### Rule
```makefile
target: dependencies
    command
```

### Example
```makefile
hello: main.o utils.o
    gcc -o hello main.o utils.o

main.o: main.c
    gcc -c main.c

utils.o: utils.c
    gcc -c utils.c

clean:
    rm -f *.o hello
```

### Phony Targets
Targets that don't produce files:
```makefile
.PHONY: clean test lint

test:
    go test ./...

lint:
    golangci-lint run
```

---

## Resources

- [GNU Make Manual](https://www.gnu.org/software/make/manual/) — official, comprehensive
- [Makefile Tutorial](https://makefiletutorial.com) — best beginner-friendly guide, covers everything from basics to advanced patterns
- [Your Makefiles are Wrong](https://tech.davis-hansson.com/p/make/) — common mistakes every Make user makes
