# The L++ Programming Language (lpp)

L++ is a compiled, statically-typed systems programming language targeting the same performance envelope as C++—including operating systems, drivers, game engines, and real-time runtimes. It introduces a modern approach to systems development via an assisted ownership memory model, a module system with no preprocessor, and a native, compile-time visual styling layer driven by CSS.

---

## Project Status: Active Design (Pre-Alpha)

**Notice:** This repository is currently in its initial pre-alpha stage. 

* **Syntax and Specifications:** Language grammar rules, syntax boundaries, and semantic constraints are under active development and contain unresolved structural conflicts.
* **Compiler Status:** A working implementation of the compiler toolchain (`lppc`) is not yet available in this repository. The current code and documentation are not ready for evaluation, testing, or deployment.
* **Current Objective:** This repository is presently being utilized to centralize language specifications, organize design documentation, and establish datasets for machine learning/LLM training pipelines.

---

## Core Architectural Pillars

1. **Uncompromised Performance:** L++ is architected to compile directly to native machine code via an LLVM backend. It features no hidden allocations and no mandatory garbage collection mechanism.
2. **Assisted Memory Safety:** The language implements an explicit `own`, `ref`, `ref mut`, and `weak` pointer model. It provides compiler-checked lifetime validation where provable, falling back to deterministic runtime traps in debug configurations.
3. **Native Visual Layer Integration:** Through the `hook visual` directive, the compiler parses standard CSS files at compile time, compiling them into flat Style Tables and injecting properties directly into struct layouts as primitive fields for zero-cost UI data representation.
4. **Machine-Oriented Syntax Design:** By enforcing explicit syntax boundaries (such as mandatory `return` statements, uniform `.` member access, and strict `ref mut T*` spelling), the language grammar is uniquely optimized for precise parsing by data pipelines and Large Language Models.

---

## Repository Architecture

This project is organized as a unified monorepo to maintain strict atomic synchronization between language specifications, test cases, and upcoming toolchain code:

```text
lpp/
├── README.md                 # Project overview and development warnings
├── LICENSE                   # Apache 2.0 License
├── docs/                     # Language specifications and grammar references
│   ├── documentation.md      # Architecture philosophy and safety design
│   ├── language-spec.md      # Reference for keywords, types, and CSS layouts
│   └── llm.txt               # Machine-readable syntax rules for AI training
├── examples/                 # Reference sample files written in L++ (.lpp)
└── compiler/                 # Future directory for the C++ compiler source code
```

---

## Licensing

This project is licensed under the **Apache License 2.0**. For full legal text, please refer to the accompanying [LICENSE](LICENSE) file. The permissive nature of the Apache 2.0 license ensures developers can construct commercial, closed-source software and platforms using L++ without encountering viral open-source licensing mandates.
