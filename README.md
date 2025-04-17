# Illeshian Suite
The Illeshian Suite is a collection of tools designed to streamline and enhance the compilation process for the Illeshian programming language. Tailored as a procedural programming, the suite offers a fast, powerful, and user-friendly environment with innovative features like a two-tier function system, advanced scoping mechanisms, and a state-machine-based data toolset. By integrating the Illeshian Driver, Illeshian Runtime Processor, Illeshian Compiler, and Seedling Assembler, the suite delivers efficient native code through a unique, one-to-one compilation and assembly process that enhances code clarity and execution speed.

The Illeshian Suite is easy to learn, introduces new keywords, and leverages a redesigned scoping and assembly structure to simplify development while maintaining high performance. Its modular design ensures seamless collaboration between programs, making it an ideal choice for developers seeking both accessibility and power.

### The Illeshian Suite Modules
- **[Illeshian Driver](https://github.com/ravenleeblack/Illeshian_Driver)**: Manages the compilation workflow and coordinates the Illeshain suite modules.
- **[Illeshian Runtime Processor](https://github.com/ravenleeblack/IRP)**: Manages runtime execution by preprocessing and optimizing.
- **[Illeshian Compiler](https://github.com/ravenleeblack/Illeshian)**: Translates Illeshian source code into Seedling source code.
- **[Seedling Assembler](https://github.com/ravenleeblack/Seedling)**: Converts Seedling source code into either nasm or Assembles into binary as output.
- **[Scope Table](https://github.com/ravenleeblack/Scope_Table)**: A collision-free symbol table library for inserting and searching both Illeshian and Seedling scopes..
- **[Syntax Formatters](https://github.com/ravenleeblack/Syntax_Formatters)**: VS Code extensions that allows syntax highlighting of .ill and .seed files.
  



## Why Illeshian?

Illeshian introduces a new structure for procedural languages by organizing logic into a 2-tier function system and leveraging a unique scoping system. It is specifically designed for tight control of scope and data structure, with clean, readable syntax and a native design for UI and system management.

---
## Function Tier System

Illeshian separates functions into two classes of heirachy:

- **First-Class Functions: Managers**
  - Managers are containers and act as global-level function definitions.
  - Example: `num create manager:` {   num window function:` { } pass_arg: 0`; } yield: 0`;
  - Access pattern: `call create.window:`

- **Second-Class Functions: Functions & Seedlings**
  - These are child functions and exist only within managers.
  - This encourages a modular, encasement but flat hierarchy, suitable for procedural design.
 
- **Functions have now have 3 parts**
  - Function header - function related information.
  - Function body - where all the work is done.
  - Function footer - uses pass_arg to return and yield to return from main.

---
## Scoping System

Illeshian uses a detailed scoping system to separate functional levels:

- **Universal Scope**: Code outside any manager
- **Global Scope**: Code inside a manager
- **Local Scope**: Code inside a child function (function or seedling)
- **Global Block Scope**: Inside a block within a manager
- **Local Block Scope**: Inside a block within a function or seedling

### Scope Table Structure

- Scope tables are array based.
- A unique naming scheme uses top-down, left-to-right indexing to avoid collisions. US_000000, GS_000000, GBS_000000, LS_000000, LBS_000000.
- 
---

## Native Seedling Integration

Seedling child functions, being inherently second-class, naturally fit into Illeshian’s function model. They are converted into local labels and integrated seamlessly into a managers body for assembly.

---

## New Tools in Development

### 1. **State Machine Tool**
- Derived from switch statements.
- Each `state` has:
  - A **state stack** for the state body
  - A **step stack** for its sub-steps
- Only two stacks should be open at any time.
- Functionality:
  - Uses `state`, `cycle`, `step`, and  `next` keywords
  - Supports return values via registers from step to state
  - Stack pointer resets for self-cleaning

### 2. **Cycle Keyword**
- Repeats a `step` until a condition is met
- Resets the stack pointer to base after each run
- Overwrites previous data to maintain clean state

---

## New Keyword: `tripare`

- Illeshian uses `pare` for booleans.
- `tripare` evaluates two `pare` values and returns a combined result.

---

## Keyword Style

Illeshian uses human-friendly keywords to encourage readable and understandable code:
- hold - `hold this`
- assign - `assign that`
- check - `check this`
- comapre - `compare that`

This reinforces the language’s approachability while retaining precision and control.

---

## Summary

Illeshian is a forward-thinking, procedural-first language designed with layered scopes, natural function separation, collision-safe naming, and advanced tools for system logic like state machines and scoped stacks. It is ideal for building operating systems, UI frameworks, and procedural applications with deterministic flow control and clean memory handling.




This repository serves as the central hub for the Illeshian Suite. Each module is actively developed in its own repository, linked above. Explore the suite, try it out, and feel free to contribute or share feedback to help shape the future of Illeshian!

