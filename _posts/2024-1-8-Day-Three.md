---
layout: post
title: Day Three - First steps in Rust
---

Today I was visited by the strange sensation that I had a boss looking over my shoulder, judging how I spent my time. I have to keep reminding myself that I'm the boss now, and that the goal isn't to maximize output/second. 

(In fact, optimizing for second-to-second productivity is probably counterproductive over the long term.)

The rest of today's post consists of notes I jotted down as I studied Rust today, especially things that surprised me coming from Python. These may seem obvious to some folks, but I didn't even know that many of these decisions were possible when designing a programming language! 

### Materials used: 
- [The Rust Book](https://rust-book.cs.brown.edu/experiment-intro.html) ch. 3-4
- [Rustlings](https://rustlings.cool/) exercises 00-03

### Major concepts: 
- Static typing
- The stack vs. the heap
- Use Box to put things in the heap 
- Ownership: variables own boxes

### Things that surprised me: 
- We have a char type that is Unicode! 
    - I think I was just excited because I want everything to be Unicode all the time
- We have to declare the type of every value in a tuple
- All values in an array have to be the same type
- Rust seems to care about single vs. double quotation marks
    - I later learned that this is for char vs. string data types
- We don't use explicit return statements (usually)
- Rust will not convert non-Boolean types to a Boolean when evaluating conditionals (Rust doesn't have "truthy" or "falsy" values)
    - I'm curious about why this is so! I use this in Python constantly. 

### Things that are cute/charming: 
- "Panicking"
- Type annotations are everywhere! 
- rust-analyzer automatically adds/changes annotations for the names of function parameters
- You can label loops and then use the break keyword with a label to specify which loop you're breaking out of! 

### Problems that I'm having: 
- rust-analyzer is extremely helpful for autocomplete, hints, etc., but it gets mad when I'm in my top "projects" directory because there's no cargo.toml there. This is annoying because I want to keep my top directory open in VSCode and work in project subdirectories, but rust-analyzer specifically looks at which directory is "open" in VSCode.
    - I briefly reviewed some solutions online but haven't tried any yet.
- It's hard to visually deal with the fact that whitespace is not meaningful when looking at things like nested loops