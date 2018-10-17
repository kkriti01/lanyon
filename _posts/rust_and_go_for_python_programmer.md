---
layout: post
title: Go and rust for python programmer
---

# Go and rust for python programmer

As many of us attended Pycon india in Hyderabad and I guess we all were little confused after keynote speech by Armin Ronacher that whether Rust is really better than python.

I have worked on python2/python3 for most of my backend project.From Django/Flask application to admin scripting or machine learning , I have used python only.But there were lots of things that I didn't find right in python like:

### Concurrency and Parellelism in python: We can't implement concurrency and parallelism in python because of GIL which is not possible with multiple core cpu also, this hugely impact the performance.
### Static and strong typing: Python doesn't provide static and strong type checking, whereas it's a strongly dynamic type.
### PEP-8 enforcing: We do get PEP-8 warning but it doesn't enforce using PEP-8, like you get error in GO and rust if you don't follow the naming convention.

So I started to check why rust is better than Python.I started reading from rust website https://doc.rust-lang.org/book/2018-edition/ch00-00-introduction.html and documentation is just awesome.There are few selling points of rust:

### rust is system level language (low level language), developer can get familiar with system programming language.
### Variables are immutable by default.
### Concurrency support.
### Memory safe by design, no garbage collector.
### No null value allowed but an option value.
### No exception but result type. (compile time checking)
### rust compiler plays gatekeeper role by refusing to compile code with elusive bug including concurrency bugs ,which most language caught by extensive testing.

## These are the improvement that we need in python:
### Typing: Static and strongly type checking like rust.
### Typescript for python: Although Python's type annotations are better than Typescript's types because they're not erased at run time, though they're slated to exist in a degenerated form in the future which is still more useful than not existing at all.
### py-modules and package.json: To install and maintain packages like npm.
### Non-indexable utf-8 string.
### Load wasm (Web assembly modules): https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WebAssembly/Module.
### Multi version import system: Import module version wise.
### Simplify object model.
### Cross compile to wasm (Web assembly modules).
### Distribution order eco system.
### Multi threading (Fix for GIL to handle concurrency)
### Enforce naming convention PEP-8.
