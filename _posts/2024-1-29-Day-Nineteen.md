---
layout: post
title: Day Eighteen - Build your own shell in Rust
---

I've been doing the [Build Your Own Shell](https://app.codecrafters.io/courses/shell/overview) challenge on Codecrafters to get more proficient in Rust. 

I've just finished the "base stage", and I have a minimally working shell in which I can use the following commands: 
- echo
- type
- exit 0
- Look for arbitrary executables in PATH, run them, and capture their output

Here's my code so far: [Build your own shell - base stages](https://gist.github.com/esokada/da2fea3c33eaa2bc84393905a3f4f1ca)
At risk of being cheesy, part of building my own shell is breaking out of my shell, so I'm setting an intention for myself to:
- Ask for a code review of this from my peers
- Pair with someone on a new step of the project

Most of the problems I've worked on so far are the "medium" difficulty, which feels about right for my skill level. The problem descriptions are underspecified and require some research, both into Rust language features and how the shell works. Sometimes I feel that they should be more explicit about what the expected results of the tests are. Overall, I enjoy the structured format of the learning, the hints left by other users, and the immediate test results after `git push`.

## Things I've learned so far
- .collect() to put results of an iterator into a vector
- All arms of a match have to return the same type
- std::process::Command to send commands to the system (like subprocess)
- pathsearch::find_executable_in_path (nice self-explanatory name)
- I've gotten more comfortable matching with Some or None. 
- If you match a value x with itself, you can't also have a _ (all other cases) arm (oops).
- You need to do this to convert stdout to a string because it is in bytes: 
  - `let stdout = String::from_utf8(output.stdout).unwrap()`
  - This is the type of thing I was made aware of at some previous stage of life and then immediately forgot.

## Lingering questions
- I still have a lot of .unwrap() in my code. This is supposed to be bad, and Rust did in fact panic several times while I was debugging, which is a sign that I haven't handled cases that I should have anticipated. I think the recommended alternative is to match, but... that sounds like a lot of matching. Need to find and get comfortable with alternative solutions. 
- Are nested matches a good way to handle complex conditions? 
