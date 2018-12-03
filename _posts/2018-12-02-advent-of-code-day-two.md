---
layout: post
title: Advent of Code
---

# Advent of Code Day 2

Date: 12/02/2018

I love to simplicity of the Advent of Code challenges and the variety of possible answers.  Over on [Reddit](https://www.reddit.com/r/adventofcode/), there are some pretty cool solutions.  Being able to compare what I've done with others is a real gold mine of information.  Some people have some pretty elegant solutions over there and there are elaborate ones including visualizations too.  

One of the first mental tensions you run into coding is the trade-off between the time you have (or want to spend) to complete something and doing it well.  It's the classic "You can get it fast, cheap, or good - pick any two."  I was feeling that today because my solutions are certainly not elegant and have a lot of room for improvement but I have other things I want to do (like finish watching Fast.AI and the second chapter of Head First Design Patterns).  I plan to read through the solutions on Reddit (although it might be January) later to see how other people did it.  Even today's coding session built on what I learned yesterday so having a glance through now will be valuable.

Here are a few things I learned today:

* The Python docs are not easy to search and are not beginner friendly.  Try looking up something like, "zip" or "filter" and see if you can (1) find what you're looking for and (2) have an intuitive sense of how to understand it.  After using Microsoft docs a lot lately, I have an even greater appreciation for how they're laid out.  I can definitely see why the internet has so many tutorials on how to do basic/common things in coding languages.
* Having seen a solution in the past can be helpful and shortcut your development time.  I'd seen the Python dictionary `setdefault` method once a long time ago, so I used that today.  I've also read about `zip` and `filter` so I considered using them as options although I've never used them before.  One value from reading the Reddit solutions is that it starts teaching you possibilities that are available which you've never seen before to dig in deeper.
* I actually used the sample input today to test my code instead of intellectually reading it and thinking, "Okay that makes sense."  Especially when I got to part two, I had to make a change.  At first, I was using the input as a hardcoded string in my code but when I did the solution I was reading input from a text file.  Somewhere between making that transition, I hit a bug.  I had to step away from the keyboard and realize I needed to use the sample input in the same way I was using the real input - namely, in a file.  After doing that it was easy enough to troubleshoot what was happening.  I had code like this:
    ``` 
        with open('input.txt') as firstPass:
            with open('input.txt') as secondPass:
                for line in firstPass:
                #do stuff
    ```

    but what would happen is my file would only get iterated over once because the secondPass   would complete and close the whole program.  Changing the code to:

    ```
        with open('input.txt') as firstPass:
            for line in firstPass:
                with open('input.txt) as secondPass:
    ```
    solved the problem.  I can assume this is because of some type of scoping but it's a    worthwhile thing to note because it could really get you hung up.

## Current Works in Progress

Consecutive blogging days: 3

Consecutive coding days: 2

### Software Engineering

[Head First Design Patterns](https://www.amazon.com/Head-First-Design-Patterns-Brain-Friendly/dp/0596007124) - Beginning Chapter 2, will publish notes from Ch1

[Advent of Code](https://adventofcode.com/) - Day 2


### Machine Learning

[Fast.AI](https://www.fast.ai) - Halfway through Lesson 3

[Kaggle Humpback Whale Identification](https://www.kaggle.com/c/humpback-whale-identification) - Not started

### Business Thinking

[25iq](https://25iq.com/chronological-index/) - Chronological order read starting today 