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
  - [Primitives](#primitives)
  - [Stack and Heap Memories & Variables & No Garbage Collector](#stack-and-heap-memories--variables--no-garbage-collector)
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

- [Rust Cookbook](https://rust-lang-nursery.github.io/rust-cookbook/)
- [Rustlings Repo](https://github.com/SSaquif/rustlings)
- [Baisc Tutorial Videos Playlist](https://www.youtube.com/watch?v=Az3jBd4xdF4&list=PLLqEtX6ql2EyPAZ1M2_C0GgVd4A-_L4_5&index=1)

## Primitives

## Stack and Heap Memories & Variables & No Garbage Collector

Basic review of Heap & Stack

- [First part of this video](https://www.youtube.com/watch?v=lQ7XF-6HYGc)

1. `Primitive types` stored in the `Stack Memory`

   1. Hence they have `fixed size`
   2. Stored in `LIFO` order, one after another
   3. Removed from Stack when out of Scope & Memory `automatically` recaptured by program
   4. Fast creation & retrieval, all about the speed

2. `Reference types` stored in `Heap Memory`
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
