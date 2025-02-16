---
in_progress: yes
all_docs_url: -
---

Oil Documentation
=================

The Oil project aims to transform Unix shell into a better programming
language.  It's **our upgrade path from bash**.

<div id="toc">
</div>

## Preliminaries

- [Why Use Oil?](/why.html)  This document is on the home page.
- [INSTALL](INSTALL.html). How do I install Oil?  This text file is also in the
  tarball.

<!-- TODO: split up help into 12 docs? -->

## OSH is a Compatible Shell

- [OSH User Manual](osh-manual.html). How do I use OSH as my shell?
- [Shell Language Idioms](shell-idioms.html).
- [Known Differences](known-differences.html) is trivia for advanced users.
  It lists differences between OSH and other shells.
- [Quirks](quirks.html) for compatibility.
- [Error Handling with `errexit`](errexit.html)

Reference:

- [OSH Help Topics](osh-help-topics.html) (incomplete).  This document
  underlies the `help` builtin.

## Oil is a New Shell Language

- [A Tour of the Oil Language](oil-language-tour.html)  A tour of Oil.
- [Oil Language Idioms](idioms.html).  A list of idioms you may want to use.
- [Shell Language Deprecations](deprecations.html).  When you turn on Oil,
  there are some shell constructs you can no longer use.  We try to minimize
  the length of this list.
- [Oil Language FAQ](oil-language-faq.html).  Common questions about the
  language.

Reference:

- [Oil Help Topics](oil-help-topics.html) (incomplete).  This document
  underlies the `help` builtin.

### Notes on Language Design

- [A Feel For Oil's Syntax](syntax-feelings.html)
- [Language Influences](language-influences.html)
- [Syntactic Concepts](syntactic-concepts.html)
  - [Command vs. Expression Mode](command-vs-expression-mode.html).

### The Command Sublanguage

**Commands** are made of words, and run builtins, user-defined functions, and
external processes.

- Command Language: Simple commands, redirects, control flow, etc.
  - [Oil Keywords](oil-keywords.html). New keywords for assignment, etc.
- Pipeline Idioms.  An essential part of shell that deserves its own document.
- [Procs, Funcs, and Blocks](oil-proc-func-block.html)
- [Modules](modules.html).  Separting programs into files.

### The Word Sublanguage

**Words** are expressions for strings.

- [Word Language](oil-word-language.html).  Substitution, splicing, globbing,
  brace expansion.
- [Strings: Quotes, Interpolation, Escaping, and Buffers](strings.html)
  - [Unicode](unicode.html).  Oil supports and prefers UTF-8.
- [Special Variables](oil-special-vars.html).  Registers?
- [Simple Word Evaluation](simple-word-eval.html).  Written for shell experts.

### The Expression Sublanguage

Oil has typed **expressions**, like Python and JavaScript.

- [Oil Expressions](oil-expressions.html) are similar to Python and JavaScript.
  - [Oil vs. Python](oil-vs-python.html)
- [Egg Expressions](eggex.html).  A new regex syntax, abbreviated *eggex*.

## The Oil Runtime

- [Options](oil-options.html).  Parsing and runtime options turn OSH into Oil.
- [Process Model](process-model.html).  The shell language is a thin layer over
  the Unix kernel.
- [Interpreter State](interpreter-state.html).  What's inside a shell
  interpreteR?
- [Variable Declaration, Mutation, and Scope](variables.html)
- [Oil Builtins](oil-builtins.html) (Shell builtins aren't discussed.)
  - [IO Builtins](io-builtins.html)
- [Tracing Execution](xtrace.html).  Oil enhances shell's `set -x`.
- [Headless Mode](headless.html).  For alternative UIs on top of Oil.
- Error Handling
  - [Error List](errors.html) 

### Interchange Formats

- [JSON](json.html): Currently supported only in the Python prototype of Oil.
- [QSN](qsn.html): Quoted String Notation.  A human- and machine-readable
  format for byte strings.
  - [Framing](framing.html)
- [QTSV](qtsv.html): An extension of TSV, built on top of QSN.

## Internal Details

- [Notes on Oil's Architecture](architecture-notes.html)
  - [Parser Architecture](parser-architecture.html)

## For Contributors

- [README.md](README.html).  If you want to modify Oil, start here.  We
  welcome contributions!
- [Toil](toil.html).  Continuous testing on many platforms.
- [Doc Toolchain](doc-toolchain.html) and [Doc Plugins](doc-plugins.html).
- [Github Wiki for oilshell/oil](https://github.com/oilshell/oil/wiki)

<!--

Discarded, maybe delete these

[What is Oil?](what-is-oil.html)  High-level descriptions of the project.

-->
