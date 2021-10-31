# Rust

🦀 🦀 🦀 🦀 🦀 🦀

## Contents

<!-- toc -->

- [Rust](#rust)
  - [Contents](#contents)
  - [Housekeeping](#housekeeping)
    - [Installation](#installation)
    - [Starting a Project](#starting-a-project)
    - [Build & Run](#build--run)
    - [Cargo and Cargo.toml](#cargo-and-cargotoml)
    - [Running Single files](#running-single-files)
    - [Crates & Cargo Commands](#crates--cargo-commands)
    - [Helpful Links](#helpful-links)
      - [Rust](#rust-1)
      - [Other Topics](#other-topics)
  - [Primitives](#primitives)
    - [A Note on Floats vs Decimals](#a-note-on-floats-vs-decimals)
  - [String vs Str (String Slices)](#string-vs-str-string-slices)
  - [Stack, Heap & No Garbage Collector](#stack-heap--no-garbage-collector)
  - [Ownership & Borrowing](#ownership--borrowing)
  - [Rust Life Times](#rust-life-times)

<!-- tocstop -->

## Housekeeping

### Installation

See `The Book`

- [The Book](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)

### Starting a Project

```bash
# boilerplate project
cargo new hello_cargo
cd hello_cargo
```

### Build & Run

```bash
cargo build
cargo run
```

If we change the file we don't have to run build again, rebuilds automatically

### Cargo and Cargo.toml

`Cargo` = package manager basically

`Cargo.toml` = setup file like `pakage.json`

### Running Single files

Install `cargo-single` (think it installs globally)

Beware that it creates the compiled folder in `/src` folder (remember to do that )

Read [Documentation Repo](https://crates.io/crates/cargo-single) on how to work with single file with dependancices

```bash
cargo install cargo-single # install

cargo single run main.rs # build and run
```

### Crates & Cargo Commands

Basically packages, get them from the Rust community crate registry

```bash
cargo install <crate-name> # install crate
```

- [Crates.io](https://crates.io/)

### Helpful Links

#### Rust

- [Rust Cookbook](https://rust-lang-nursery.github.io/rust-cookbook/)
- [Rustlings Repo](https://github.com/SSaquif/rustlings)
- [Baisc Tutorial Videos Playlist](https://www.youtube.com/watch?v=Az3jBd4xdF4&list=PLLqEtX6ql2EyPAZ1M2_C0GgVd4A-_L4_5&index=1)

#### Other Topics

- [floats Cheatsheet](https://floating-point-gui.de/)

## Primitives

> Make sure your variable type is large enough to handle the data
> If you are not sure go for the larger number

Primitive types basically have a fixed size, the number in the type specifies the number of bits

1. Boolean (bool)

   1. 1 bit

2. Integers (`Deafult` is `i32`)

   1. Signed (+/-): i8 i16,i32,i64,i128
   2. UnSigned: u8 u16,u32,u64,u128
   3. Architeture Dependent: `isize` & `usize`

      ```rust
      let
      ```

   4. Default i32 is (+/-) 2 billion approximately

3. Floats (`Deafult` is `f64`)

   1. f32, f64

4. Chars (see `strings` as well)
   1. 4 bytes/32 bits
   2. For characters(any language) and emojis

### A Note on Floats vs Decimals

General rule in programming, Floats are estimations where as Decimals are meant to be exact. I am pretty sure for most cases we just use floats for decimals. But and Interesting Topic & here is an usefull link

- [floats Cheatsheet](https://floating-point-gui.de/)
- [floats in Rust](https://floating-point-gui.de/languages/rust/)

## String vs Str (String Slices)

In rust `Strings` are not easy to work with because they are not treated as `primitive` types. Unlike in most language where the are used like `primitives` even though under the hood the are not

> Rust keeps the above distinction alive. This is Difference is a `Memory Tradeoff` rust has made

## Stack, Heap & No Garbage Collector

Basic review of Heap & Stack (Similar to most if not all languages)

- [First part of this video](https://www.youtube.com/watch?v=lQ7XF-6HYGc)

> Rust calls varaibles `Scalar` & `Compound` types instead of `Primitive` & `Reference Types`

1. `Primitive (Scalar) types` stored in the `Stack Memory`

   1. Hence they have `fixed size`
   2. Stored in `LIFO` order, one after another
   3. Removed from Stack when out of Scope & Memory `automatically` recaptured by program
   4. Fast creation & retrieval, all about the speed

2. `Reference (Compound) types` stored in `Heap Memory`
   1. Heap provides Flexibility
   2. Memory that can grow in size (String, Vector, HashMap etc)
   3. There's a Runtime Performance Cost (Slower)
   4. Heap Memory (for a variable) can live beyond the scope that created it
   5. `Rust Specific:` Memory is automatically recaptured when the last owner goes out of scope

> Above is the reason why RUST has NO Garbage Collector, & why rust is rust

## Ownership & Borrowing

```rust
// Creating a Variable Stored in Heap Memory
let heap_i8: Box<i8> = Box:new(30)

// Transferring Ownership of heap_i8:
let heap_i8_2 = heap_i8
```

## Rust Life Times
