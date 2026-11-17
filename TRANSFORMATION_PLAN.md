# The Rust Bible: Transformation Plan

## Vision

Transform the current collection from biblical parody into a genuine Rust programming guide that uses biblical structure (books, chapters, numbered verses) as its organizing metaphor. The format is the vehicle; the content is real Rust education.

**Not religious. Not a cult. Not parody.** A programmer's guide to Rust, written in the cadence and structure of scripture so the lessons stick.

---

## Guiding Principles

1. **Every verse teaches something.** Each numbered line is a concept, rule, or code example — not narrative filler.
2. **Code is scripture.** Real, compilable Rust appears in verses, formatted as code blocks or inline.
3. **The verse format aids memory.** Short, numbered, declarative lines make concepts easy to scan and recall — like `cargo check` output, but readable.
4. **Progressive disclosure.** Old Testament = foundations. New Testament = advanced and applied. Within each book, chapters build on each other.
5. **No "Compiler said unto..." framing.** The Compiler is not a character. Rust is the subject. The tone is instructive, direct, and occasionally oracular for flavor — but never fictional.
6. **Biblical names stay.** Book names (Genesis, Exodus, Romans, etc.) are kept for structure and recognition, but their content maps to Rust topics, not Bible stories.

---

## Format Specification

### File naming

Books live in `The-Book-of-Rust/Books/{Old Testament,New Testament}/` as `<number>. <Name>.md`.

```
Books/Old Testament/1.0 Genesis.md
Books/Old Testament/2.0 Exodus.md
Books/New Testament/1.0 Matthew.md
```

The number prefix controls ordering on the website. The `1.0` vs `1.1` distinction in the current files should be dropped — use a single sequential number per testament.

### Book structure

```markdown
# Book of Genesis

*Rust topic: Variables, Types, and Mutability*

## Chapter 1: In the Beginning Was the Let Binding

1 First, install Rust with `rustup` and verify with `rustc --version`.

2 Every Rust program begins with `fn main() {}` — the entry point the runtime calls.

3 Declare a variable with `let`. By default, it is immutable:
   ```rust
   let x = 5;
   ```

4 To make a variable mutable, use `mut`:
   ```rust
   let mut y = 10;
   y = 20; // allowed
   ```

5 Rust is statically typed. The compiler infers types where it can, but you may annotate:
   ```rust
   let z: i32 = 42;
   ```

6 Shadowing lets you reuse a name with a new value and type:
   ```rust
   let spaces = "   ";
   let spaces = spaces.len(); // now a usize
   ```

7 Constants use `const`, must be annotated, and are evaluated at compile time:
   ```rust
   const MAX_POINTS: u32 = 100_000;
   ```

## Chapter 2: Primitive Types

1 Integer types: `i8`, `i16`, `i32`, `i64`, `i128`, `isize` (signed) and `u8`...`usize` (unsigned).

2 Default integer type is `i32`. Choose based on range needs.

3 Floating-point types: `f32` and `f64`. Default is `f64`.

4 The boolean type is `bool` with values `true` and `false`.

5 Character type is `char`, four bytes, representing a Unicode scalar value:
   ```rust
   let heart = '❤';
   ```

6 Tuples group multiple types:
   ```rust
   let tup: (i32, f64, char) = (500, 6.4, 'x');
   ```

7 Arrays have fixed length, known at compile time:
   ```rust
   let arr: [i32; 5] = [1, 2, 3, 4, 5];
   ```

8 Slices are views into arrays or vectors: `&arr[1..3]`.

## Chapter 3: Functions

1 Define functions with `fn`. Parameters must be typed:
   ```rust
   fn add(a: i32, b: i32) -> i32 {
       a + b
   }
   ```

2 The return value is the final expression — no `return` keyword needed.

3 Statements end with semicolons. Expressions do not and produce values.

4 Early returns use `return`:
   ```rust
   fn check(x: i32) -> bool {
       if x < 0 { return false; }
       x > 0
   }
   ```

5 Functions are expressions. You can assign them and pass them around via function pointers:
   ```rust
   let f: fn(i32) -> i32 = add;
   ```

6 Use `_` to discard an unused parameter name and silence warnings.
```

### Verse rules

- Each verse begins with a number, period, space: `1 `, `2 `, etc.
- Verses are concise — one concept or one short code block per verse.
- Code blocks are fenced with `rust` and are counted as part of their verse.
- Verses that introduce a code block state the concept in prose first, then show the code.
- Chapter headings use `## Chapter N: Title`.
- Each book begins with `# Book of <Name>` and an italic topic line: `*Rust topic: ...*`.

---

## Old Testament: Foundations (39 Books)

The Old Testament covers everything a new Rust programmer needs, from first principles to confident daily work. Chapters build on each other.

| # | Book | Rust Topic | Chapters |
|---|------|-----------|----------|
| 1 | Genesis | Variables, types, mutability, functions | 4 |
| 2 | Exodus | Ownership, borrowing, references, lifetimes | 5 |
| 3 | Leviticus | Structs, enums, pattern matching, methods | 5 |
| 4 | Numbers | Collections: Vec, String, HashMap, HashSet | 4 |
| 5 | Deuteronomy | Error handling: Result, Option, `?`, panic | 4 |
| 6 | Joshua | Traits, generics, trait bounds, impl blocks | 5 |
| 7 | Judges | Closures, iterators, functional patterns | 4 |
| 8 | Ruth | Modules, packages, crates, use paths | 3 |
| 9 | 1 Samuel | Testing: unit, integration, doc tests, `cargo test` | 4 |
| 10 | 2 Samuel | Cargo, dependencies, Cargo.toml, crates.io | 3 |
| 11 | 1 Kings | Documentation: doc comments, `cargo doc`, examples | 3 |
| 12 | 2 Kings | Project structure, workspaces, binaries vs libraries | 3 |
| 13 | 1 Chronicles | Smart pointers: Box, Rc, Arc, RefCell | 4 |
| 14 | 2 Chronicles | Interior mutability: Cell, RefCell, Mutex patterns | 3 |
| 15 | Ezra | Strings deep dive: String vs &str, UTF-8, formatting | 4 |
| 16 | Nehemiah | Concurrency foundations: threads, Send, Sync | 4 |
| 17 | Esther | Async foundations: futures, async/await, tokio | 4 |
| 18 | Job | Generics deep dive: type parameters, where clauses | 3 |
| 19 | Psalms | Common patterns: builder, newtype, state machine | 4 |
| 20 | Proverbs | Best practices: naming, API design, idiomatic Rust | 4 |
| 21 | Ecclesiastes | Performance: zero-cost abstractions, optimization, profiling | 3 |
| 22 | Song of Solomon | Macros: `macro_rules!`, declarative macros | 3 |
| 23 | Isaiah | Unsafe Rust: raw pointers, unsafe fn, calling C | 4 |
| 24 | Jeremiah | FFI: extern "C", bindgen, safe wrappers | 3 |
| 25 | Lamentations | Common errors and how to fix them | 3 |
| 26 | Ezekiel | Advanced trait patterns: associated types, GATs | 3 |
| 27 | Daniel | Advanced types: enums with data, recursive types | 3 |
| 28 | Hosea | Lifetimes advanced: lifetime elision, 'static, variance | 3 |
| 29 | Joel | Iterators advanced: adapters, consumers, lazy evaluation | 3 |
| 30 | Amos | Error handling advanced: custom errors, thiserror | 3 |
| 31 | Obadiah | Serialization: serde, JSON, formats | 3 |
| 32 | Jonah | CLI tools: clap, stdin/stdout, exit codes | 3 |
| 33 | Micah | File I/O and networking basics: std::fs, std::net | 3 |
| 34 | Nahum | Pattern matching advanced: matches!, if let, let-else | 2 |
| 35 | Habakkuk | Type system deep dive: traits vs enums, trait objects | 3 |
| 36 | Zephaniah | Collections advanced: custom iterators, IntoIterator | 3 |
| 37 | Haggai | Testing advanced: mocking, fixtures, property testing | 3 |
| 38 | Zechariah | Benchmarking: criterion, `cargo bench`, flamegraphs | 3 |
| 39 | Malachi | Capstone: build a complete CLI tool from scratch | 4 |

---

## New Testament: Advanced & Applied (27 Books)

The New Testament covers real-world application: web, systems, data, concurrency at scale, and architectural patterns. Each book is a domain.

| # | Book | Rust Topic | Chapters |
|---|------|-----------|----------|
| 1 | Matthew | Web servers: axum, routing, handlers, middleware | 5 |
| 2 | Mark | Web clients: reqwest, HTTP, JSON APIs | 3 |
| 3 | Luke | Databases: sqlx, diesel, connection pooling | 4 |
| 4 | John | Data serialization: serde advanced, custom formats | 4 |
| 5 | Acts | Building real applications: architecture, layering | 4 |
| 6 | Romans | Systems programming: no_std, embedded, kernels | 4 |
| 7 | 1 Corinthians | Concurrency at scale: channels, actors, lock-free | 5 |
| 8 | 2 Corinthians | Async runtime internals: tokio, futures, executors | 4 |
| 9 | Galatians | GUI and frontend: egui, Tauri, WASM | 3 |
| 10 | Ephesians | CLI tools in depth: interactive, piping, scripting | 3 |
| 11 | Philippians | Game development: Bevy, ECS, game loops | 4 |
| 12 | Colossians | Networking: TCP, UDP, custom protocols | 3 |
| 13 | 1 Thessalonians | Cryptography and security: ring, secrecy | 3 |
| 14 | 2 Thessalonians | Machine learning and data: ndarray, data pipelines | 3 |
| 15 | 1 Timothy | Cross-platform: cfg, target-specific code | 3 |
| 16 | 2 Timothy | Packaging and distribution: cross-compilation, releases | 3 |
| 17 | Titus | Code review and collaboration: lints, CI, fmt | 3 |
| 18 | Philemon | Contributing to open source: crates, docs, semver | 3 |
| 19 | Hebrews | Design patterns in Rust: idioms vs antipatterns | 4 |
| 20 | James | Architecture: hexagonal, event-driven, DDD in Rust | 4 |
| 21 | 1 Peter | Observability: logging, tracing, metrics | 3 |
| 22 | 2 Peter | Deployment: Docker, cloud, edge | 3 |
| 23 | 1 John | Rust in the large: monorepos, workspaces, teams | 3 |
| 24 | 2 John | Migration strategies: rewriting, strangler fig, ABI | 3 |
| 25 | 3 John | Advanced FFI: callbacks, complex types, safety | 3 |
| 26 | Jude | Rust internals: compiler, MIR, borrow checker | 3 |
| 27 | Revelation | The future: where Rust is headed, how to keep learning | 4 |

---

## Sunday School Lessons

The existing Sunday School section should be updated to complement the books — hands-on exercises that correspond to each Old Testament book. Each lesson has 3-5 sections with progressively harder exercises.

Lesson topics to write (one per OT book, starting with the first 10):

1. Your First Rust Program
2. Ownership Playground
3. Structs and Enums Workshop
4. Collections in Practice
5. Error Handling Drills
6. Traits and Generics Lab
7. Iterators and Closures
8. Modules and Crates
9. Testing Your Code
10. Cargo and Dependencies

---

## Website Changes Needed

1. **Copy books to `public/Books/`.** The website reads from `public/Books/`, not the Obsidian vault. Add a sync step or move content there.
2. **Update homepage copy.** Replace "Sacred writings for the Rustacean faith" and "Rustacean faith" language with guide-oriented copy: "A programmer's guide to Rust, in biblical form" etc.
3. **Update README.** Remove "parody" language. Describe it as a Rust guide with biblical structure.
4. **BookViewer rendering.** Verify code blocks render correctly with syntax highlighting. Add a syntax highlighter (e.g., `react-syntax-highlighter` or `shiki`) if not present.
5. **Verse of the Day.** Keep, but pull from the new educational verses.
6. **Search index.** Regenerate after content is rewritten.
7. **Navigation.** The existing chapter extraction (`## ` headings) works with the new format. Book ordering via filename prefixes works as-is.

---

## Execution Order

### Phase 1: Foundation (Books 1-5, Old Testament)
Rewrite Genesis, Exodus, Leviticus, Numbers, Deuteronomy. These cover the absolute basics and set the tone for everything else.

### Phase 2: Core Language (Books 6-12, OT)
Traits, closures, modules, testing, cargo, docs, project structure.

### Phase 3: Intermediate (Books 13-27, OT)
Smart pointers, concurrency, async, generics, patterns, best practices.

### Phase 4: Advanced OT (Books 28-39, OT)
Lifetimes, iterators, errors, serde, unsafe, FFI, macros, capstone.

### Phase 5: New Testament (All 27 books)
Domain-specific books. Can be written in parallel or sequentially.

### Phase 6: Sunday School Lessons
Hands-on exercises matching the books.

### Phase 7: Website updates
Copy sync, homepage copy, README, rendering improvements.

---

## What Stays

- Biblical book names (Genesis, Exodus, etc.)
- Testament structure (Old/New)
- Numbered verse format
- Chapter structure (`## Chapter N: Title`)
- Website architecture and design system
- The amber/brown theme

## What Goes

- "And the Compiler said unto..." narrative framing
- Fictional characters (Abraham, Isaac, Jacob as Rust programmers)
- Parody Bible stories with Rust words swapped in
- "Sacred writings" / "faith" / "Rustacean faith" language
- Empty book files
- The `zz_` duplicate file