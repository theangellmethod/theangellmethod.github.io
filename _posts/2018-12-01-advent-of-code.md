---
layout: post
title: Advent of Code
---

# Advent of Code and 100 days of blogging

Date: 12/01/2018

I've seen a lot of people doing 100 days of code.  I've also been encouraged to blog for 100 days.  So here we go.

I started the [Advent of Code](https://adventofcode.com/) today using Python 3.7.  You can checkout the code on my [github repo](https://github.com/theangellmethod/adventofcode2018)  The challenge was seemingly easy - but I learned/was reminded of several interesting things.  My brain is still converting back into coder mode after a long hiatus so some of these things seem obvious in retrospect but here's the key - if I had never done the work, none of this would have stuck out (and hopefully, stick).  I am developing a deep belief in the value of learning through doing as has been recommended to me repeatedly by people who are way better at this than I am.  Here is what I learned doing the first day's exercise:

* I knew to use `with open` as a wrapper for interacting with files but I didn't realize that readline() would only execute once - I thought it would execute throughout the file.  Learning 1: You still have to add the code to read all of the lines after:
    ```
    with open('file.txt') as f:
        for line in f.readline():
    ```
* The second part of the challenge threw a curve ball, and it seems like from reddit other people missed it as well.  I made an assumption that the list of values they gave as input would only be used once, but it turns out there was a line that said "Note that your device might need to repeat its list of frequency changes many times before a duplicate frequency is found" which I, and others, had completely glossed over.  For some reason since I was using the list as a data structure in my code, I didn't connect this to mean the list of values in the input file I was using so I had to go back and account for needing to iterate through the file multiple times. Lesson 2: Read the requirements.
* The next part was - after that was solved I still didn't seem to be getting a result.  When I looked on Reddit, I saw someone was using a set so I thought to try that instead of a list, which worked.  I went on to look and see what iteration happened for the desired value to be found (139,822 iterations).  I went back to trying the list data structure to see if this was something I was doing incorrectly with the list data structure or something different.  It turns out that I could get the same result for the list data structure at the 139,822nd iteration.  So what was going on?  It wasn't that I *wasn't* getting a result from using a list, it would've worked, but it was taking so long compared to the answer I received from the first part of the challenge that I thought my code must be hanging somewhere.  Now I started to wonder - why are these two data structures taking such different amounts of time to run?
* `python -m cProfiler main.py` this was the money maker today.  It takes 0.171s to use a set and 126.109s to use the list.  That's a huge difference (100x)!  Why would it be so different?  Because set lookup and additions are O(1) and lists are O(n).  Wow - I have only recently heard one person talk about algorithmic complexity and this only appeared in one section of a book in my first programming class in college.  After that, it only appeared in interviews.  The only reason I knew to look for a way of measuring the time it takes to execute a program is because frequently in data science intro classes they talk about using the timeit module in jupyter notebooks.  The advice on stackoverflow was to use cProfiler for programs, and timeit for modules and that's how I got my results.  Learn more about [cprofile](https://docs.python.org/3/library/profile.html?highlight=cprofiler)   Lesson 3: Know the advantages/disadvantages of data structures. Compare/contrast them to see how they perform and when it's appropriate to use one over the other.

## Current Works in Progress

Consecutive blogging days: 2

Consecutive coding days: 1 (starts today)

### Software Engineering

[Head First Design Patterns](https://www.amazon.com/Head-First-Design-Patterns-Brain-Friendly/dp/0596007124) - Beginning Chapter 2, will publish notes from Ch1

[Advent of Code](https://adventofcode.com/) - Day 1


### Machine Learning

[Fast.AI](https://www.fast.ai) - Halfway through Lesson 3

[Kaggle Humpback Whale Identification](https://www.kaggle.com/c/humpback-whale-identification) - Not started

### Business Thinking

[25iq](https://25iq.com/chronological-index/) - Chronological order read starting today 