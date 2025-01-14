---
layout: post
title: Day Seven - Ballet sequence generator
---

Remote RC was somewhat better today, though I also forgot that I had a dentist appointment. 

Today I did some work on my ballet sequence generator! This is a fun side project that I'm doing in Python to take a break from "serious" work. 

A ballet class follows a predictable set of rules but has some variation. I'm trying to build a program that will generate valid ballet class sequences. 

This could help ballet teachers brainstorm lessons when they're suffering from choreographer's block. It could also be a way for ballet students to practice dancing at home. 

## What I did today:
- Write PCFG (probabilistic context-free grammar) in a text file
  - Only for "plies" (the very first part of class) for now 
- Generate valid sequences from grammar using [this extension to NLTK's PCFG](https://github.com/thomasbreydo/pcfg) 


## What's next: 
- Need to make the generated sequence match the length of the music.
  - For now, assume that all music is in 4/4.
  - Pass in the length of the music ("count") as an int.
  - Each leaf node ("terminal" in CFG terminology) has a count associated with it (or multiple possibilities, if a move can be performed over 2 or 4 counts, for example).
  - The combined total of the counts at all the leaf nodes needs to match the length of the music.
    - This doesn't need to scale to arbitrary lengths of music.  It's okay to return an error on failure.
  - It should also be able to repeat parts of a sequence to "fill out" an extra-long count. 
    - This is starting to sound like regex or something else - there's no such thing as a repeater operator in the nltk cfg implementation. This makes me think that I need to further adapt the PCFG class, implement a version myself from scratch, or try a totally different kind of data structure. 
- Print the result out in a more readable format


  ## Future ideas (that I may not get to):
- Figure out how to extract count from actual audio file
  - Remember to handle the fact that many of these ballet tracks have an "intro" that shouldn't be counted
- Display text cues along with playing music
- Display some kind of graphics (maybe an image that fades in/out along with the music)
- Play audio cues
