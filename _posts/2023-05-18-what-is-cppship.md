---
title:  "What is Cppship, and why do I use it?"
date:   2023-05-18 00:45:00 -0500
sidebar:
  nav: "what_is_cppship"
header:
  teaser: /assets/images/Cppship.png
author_profile: false
categories: tools
tags: c++ cargo
---

## Introduction
As a computer programmer, I like to spend most of my time writing and developing code. The big issue I run into with C++ though, is having to spend lots of time learning how
to use cmake and properly utilize its syntax. Until one day I came across [Cppship](https://github.com/qqiangwu/cppship) while scrolling through GitHub. After a quick read of its 
documentation, I installed it and have been using it for my C++ projects ever since.

## Cppship
According to [qqiangwu](https://github.com/qqiangwu), the creator of cppship, cppship is a "Cargo-like build tool for modern cpp". If you aren't familiar with Cargo, 
it's a package manager that comes with the Rust programming language. Cargo manages your packages and builds your code. Just like Cargo, Cppship manages your packages and builds your C++ code.
This allows developers to spend less time configuring their compiler and packages, and spend that time developing their projects.

Currently, Cppship is supported on Linux and MacOS, and Windows support is still being implemented

## Why use Cppship
While I could give you reasons for why you should use it in my own words, I think reading the PR itself does a better job [here](https://github.com/qqiangwu/cppship).

## So why do I use Cppship
Even though Cppship isn't widely used yet, I still find having a Cargo-like build tool for C++ useful. I also enjoy how Cppship allows for easily including other cppship projects 
through the use of GitHub. With Cppship, all you have to do is upload your cppship project to a PR, then when you wish to include it in another project you can include that 
PR in your cppship.toml file.

Example:
```toml
[package]
name = "test"
version = "0.0.1"
authors = []
std = 17
[depencies]
#include apexcore(a cppship project) through its PR
apexcore = {git = "https://github.com/Bjathneas/ApexCore.git", commit = "8732e53"}
```
# Conclusion
Cppship is Cargo but for C++, and allows a C++ dev to easily create a new project, build, run, test, bench, format, and lint it. I use Cppship its simple, easy to use, and
allows me to spend more time writing my C++ projects, instead of slamming my head into my desk because Cmake chose not to like me.
