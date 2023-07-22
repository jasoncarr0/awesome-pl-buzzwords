| [Rationale](https://github.com/glyh/PL-features/blob/main/rationale.md) | [Convention](https://github.com/glyh/PL-features/blob/main/convention.md) | [Contributing](https://github.com/glyh/PL-features/blob/main/contributing.md) |

## By topic

- Caching: [Caching with Reactive Invalidation](#caching-with-reactive-invalidation) 

- Calculus: [Symmetric Interaction Calculus](#symmetric-interaction-calculus), [Term Rewriting](#term-rewriting), [Dot Calculus](#dot-calculus)

- Code Generation: [Hygienic Macros](#hygienic-macros), [Lisp Macros](#lisp-macros)

- Dependency: [Fragment Based Code Distribution](#fragment-based-code-distribution)

- Evaluation: [Compile-time Code Evaluation](#comptime), [Lazy Evaluation](#lazy-evaluation)

- Mutitasking: [Async/await](#asyncawait), [Coroutine](#coroutine), [Green Threads](#green-threads), [Symmetric Interaction Calculus](#symmetric-interaction-calculus) 

- Paradigm: [Functional Programming](#functional-programming), [Logic Programming](#logic-programming), [Message-Passing](#message-passing)

- Polymorphism: [Row Polymorphism](#row-polymorphism)

- Memory Management: [Garbage Collection](#garbage-collection), [Ownership](#ownership)

- Syntax Sugar: [Pattern matching](#pattern-matching), [Universal Function Call Syntax](#universal-function-call-syntax)

- Type: [Dependent Type](#dependent-type), [Effect System](#dependent-type), [Gradual Typing](#gradual-typing)

## List of features

#### Actor Model

#### Algebraic Data Type

#### [Async/await](https://en.wikipedia.org/wiki/Async/await)
  - Description: A syntax sugar for writing [asynchronous](https://en.wikipedia.org/wiki/Async/await) [concurrent](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) code that looks serial.
  - Implementation: [Javascript](https://www.javascript.com/) [async-await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
  - Pros: Readability
  - Cons: Uncontrolable
  - Topic: Multitasking
  - Videos: [Fireship: The Async Await Episode I Promised](https://www.youtube.com/watch?v=vn3tm0quoqE&t=344s)

#### Caching with Reactive Invalidation
  - Description: Caching the result of function, invalidating the data reactively when the cache are potentially outdated.
  - Implementation: [Skip](http://skiplang.com/docs/tutorial.html) [Caching with reactive invalidation](http://skiplang.com/)
  - Requires: an [effect system](https://github.com/glyh/PL-features#effect-system)
  - Pros:
    - User doesn't have to invalidate cache on their own
  - Topic: Caching

#### Compile-time Code Evaluation
  - Description: Evaluation of code at [compile time](https://en.wikipedia.org/wiki/Compile_time).
  - Implementation: [Zig](https://ziglang.org/) [comptime](https://ziglang.org/documentation/master/#comptime)
  - Pros: 
    - Provides generics: generics are just compile time evaluated function from types to types.(this requires a tailored type system)
  - Cons: Compilation speed
  - Topic: Evaluation

#### Coroutine 
  - Description: A syntax sugar for structuring [cooperative](https://en.wikipedia.org/wiki/Cooperative_multitasking) [concurrent](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) code modularly.
  - Implementation: [Lua](https://www.lua.org/) [coroutine](https://www.lua.org/pil/9.1.html)
  - Pros: Readablility
  - Topic: Multitasking

#### Datalog

#### Dependent Type

#### Dot Calculus
  - Articles: [Essense of Scala](https://www.scala-lang.org/blog/2016/02/03/essence-of-scala.html)

#### Effect System
  - Description: A system similar to type system, but tracks [side effects](https://en.wikipedia.org/wiki/Side_effect_(computer_science)) instead of type of the value.
  - Implementation: [Koka](https://koka-lang.github.io/koka/doc/index.html) [effect system](https://en.wikipedia.org/wiki/Effect_system)
  - Pros: Safety, Debuggablility
  - Cons: Verbosity
  - Topic: Type
  - Articles: [Stephen Diehl: Exotic Programming Ideas: Part 3 (Effect Systems)](https://www.stephendiehl.com/posts/exotic03.html)

#### Fragment-based Code Distribution
  - Description: A compiler infrastructure that identify codes fragment by its hash.
  - Implementaion: [Haskell](https://www.haskell.org/) [fragnix](https://github.com/fragnix/fragnix), [Unison](https://www.unison-lang.org/) [hash identified AST](https://www.unison-lang.org/learn/tour/_big-technical-idea/)
  - Pros: 
    - [No builds](https://www.unison-lang.org/learn/tour/_big-technical-idea/#no-builds)
    - [No dependency conflicts](https://www.unison-lang.org/learn/tour/_big-technical-idea/#no-dependency-conflicts)
    - [Typed, durable storage](https://www.unison-lang.org/learn/tour/_big-technical-idea/#typed-durable-storage)
  - Topic: Dependency
  - Articles: [Big Technical Idea on Unison](https://www.unison-lang.org/learn/tour/_big-technical-idea/)

#### Formal Methods
  - Description: A series of techiques that helps proving the behavior of the program
  - Implementation: [Coq](https://coq.inria.fr/) [proof assitant](https://en.wikipedia.org/wiki/Proof_assistant)
  - Pros: Safety, No runtime
  - Cons: Verbosity

#### Functional Programming

#### [Garbage Collection](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science))
  - Description: A system that free unused [heap-allocated](https://en.wikipedia.org/wiki/C_dynamic_memory_allocation) memory in [runtime](https://en.wikipedia.org/wiki/Runtime_system)
  - Implementation: [Common Lisp](https://lisp-lang.org/) garbage collector
  - Pros: Developer-friendliness
  - Cons: Performance
  - Topic: Memory Management

#### Generalized Algebraic Data Type

#### [Gradual Typing](https://en.wikipedia.org/wiki/Gradual_typing)
  - Description: A type system that checks some expresions/variables at compile time while leaving others to the runtime type checker.
  - Implementation: [Typescript](https://www.typescriptlang.org/)'s [type system](https://basarat.gitbook.io/typescript/type-system)
  - Pros: Flexibility
  - Cons: Safety
  - Topic: Type

#### [Green Threads](https://en.wikipedia.org/wiki/Green_thread)
  - Description: An abstraction that allow easily writing [preemptive](https://en.wikipedia.org/wiki/Preemption_(computing)) [concurrent](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) code, without actually using OS thread
  - Implementation: [Java](https://www.java.com/) green threads
  - Pros: 
    - potential performance boost by not wasting time on OS context switch.
  - Topic: Multitasking

#### Hygienic Macros
  - Description: Lisp macros that follows [lexical scope](https://en.wikipedia.org/wiki/Scope_(computer_science)#Lexical_scope).
  - Implementation: [Scheme](https://www.scheme.com/) [Hygienic macro](https://docs.scheme.org/guide/macros/)
  - Based-on: [Lisp Macros](https://github.com/glyh/PL-features#lisp-macros)
  - Pros: Debuggablility 
  - Topic: Code Generation

#### Lazy Evaluation
  - Description: Any portion of the code is evaluated only when needed.
  - Implementation: [Haskell](https://www.haskell.org/) [lazy evaluation](https://wiki.haskell.org/Lazy_evaluation)
  - Pros: 
    - Easy to implement infinite data structures
    - Potential performance boost by not evaluating unnecessary code
  - Cons: Undebuggable
  - Topic: Evaluation

#### Lisp Macros
  - Description: [Compile-time](https://en.wikipedia.org/wiki/Compile_time) [AST](https://en.wikipedia.org/wiki/Abstract_syntax_tree)-based code generation in a [homoiconic](https://en.wikipedia.org/wiki/Homoiconicity) and [dynamically-typed](https://en.wikipedia.org/wiki/Type_system#Dynamic_type_checking_and_runtime_type_information) language.
  - Implementation: [Common Lisp](https://lisp-lang.org/) [macros](https://lispcookbook.github.io/cl-cookbook/macros.html)
  - Pros: DRY, Productibility
  - Cons: Debuggablility, Readablility, Performance Predictablity
  - Topic: Code Generation

#### Logic Programming

#### Message Passing

#### Ownership
  - Description: A system that helps compiler decide when to free [heap-allocated memory](https://en.wikipedia.org/wiki/C_dynamic_memory_allocation) statically.
  - Implementation: [Rust](https://www.rust-lang.org/) [Ownership](https://doc.rust-lang.org/book/ch04-00-understanding-ownership.html)
  - Pros: Performance
  - Cons: Readablility, Developer-friendliness 
  - Topic: Memory Management

#### Pattern matching 
  - Description: A structural way for obtain data from complicated [data structures](https://en.wikipedia.org/wiki/Data_structure).
  - Implementation: [Haskell](https://www.haskell.org/) [pattern matching](https://www.haskell.org/tutorial/patterns.html)
  - Pros: Readablility, Optimizabililty
  - Topic: Syntax Sugar

#### Row Polymorphism
  - Description: A polymorphism that dispatch on concerned record fields and their type.
  - Implementation: [OCaml](https://ocaml.org/) [row polymorphism](https://www.cl.cam.ac.uk/teaching/1415/L28/rows.pdf)
  - Pros: 
    - Flexibility compared to subtyping
  - Topic: Polymorphism
  - Articles: 
    - [Jadon Fowler: Row Polymorphism without the Jargon](https://jadon.io/blog/row-polymorphism/)
    - [Stackoverflow: What are row types? Are they algebraic data types?](https://stackoverflow.com/questions/48092739/what-are-row-types-are-they-algebraic-data-types)
  - Paper: [Objective ML: An effective object-oriented extension to ML](https://caml.inria.fr/pub/papers/remy_vouillon-objective_ml-tapos98.pdf)

#### Symmetric Interaction Calculus
  - Description: A calculus similar to [Lambda Calculus](https://en.wikipedia.org/wiki/Lambda_calculus), that can be implement concurrently due to its support for projection and duplication.
  - Implementation: [HVM](https://github.com/HigherOrderCO/HVM)
  - Pros: Parallization for free
  - Topic: Multitasking, Calculus
  - Articles: 
    - [Victor Maia: The Symmetric Interaction Calculus](https://medium.com/@maiavictor/the-abstract-calculus-fe8c46bcf39c)
    - [XXIIVV: interaction nets](https://wiki.xxiivv.com/site/interaction_nets.html)
    - [Zicklag: Interaction Nets, Combinators, and Calculus](https://zicklag.github.io/blog/interaction-nets-combinators-calculus/)
  - Papers:
    - [Interaction nets](https://dl.acm.org/doi/10.1145/96709.96718)

#### Term Rewriting

#### [Universal Function Call Syntax](https://en.wikipedia.org/wiki/Uniform_Function_Call_Syntax)
  - Description: A syntax sugar for function call that makes chaining function calls easy.
  - Implementation: [Nim](https://nim-lang.org/) [UFCS](https://narimiran.github.io/nim-basics/#_calling_the_procedures), [Elixir](https://elixir-lang.org/) [pipe operator](https://elixir-lang.org/getting-started/enumerables-and-streams.html#the-pipe-operator), [Clojure](https://clojure.org/) [threading macro](https://clojure.org/guides/threading_macros)
  - Pros: Readablility
  - Topic: Syntax Sugar
