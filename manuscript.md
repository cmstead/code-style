
<!-- GENERATED DOCUMENT! DO NOT EDIT! -->
# The Discipline of Authoring Code #


## Table Of Contents ##

- [Chapter 1: Authoring Code](#user-content-authoring-code)
- [Chapter 2: Variables, Parameters, and Constants](#user-content-variables,-parameters,-and-constants)
- [Chapter 3: Expressions](#user-content-expressions)

## Authoring Code ##


### Finding New Joy ###

I have a project I have an on-again, off-again relationship with, that I started work on about 4 years ago. It's open source and I believe there are probably many people out there cursing my name because there are bugs I haven't had time to fix.

This project started as a way to prove that my favorite editor could be extended to support code refactoring. At the time I knew next to nothing about actually writing software which could interpret and modify code.

I made a mess.

Nothing was tested. It seemed an impossible task to attempt to get tests around the code at all. Without tests, I was afraid to make changes to the code, so everything turned into a giant mess of spaghetti.

But, it worked.

Since the code was hard to work on, and hard to manage, I fell out of love with the project pretty quickly. A few short months and it felt like I was quickly sinking into the quicksand of a project that is destined to fail.

Then I started creating other tools. I learned better ways to break up the code so I could test it. I created a run-time type system I could use to guarantee that function contracts were respected.

As I started working on reassembling my project with these new tools, something happened. I found myself excited about the project again. It wasn't because I got to use new tools. It was actually because I found, once the code actually captured and held context, I could quickly dive into and understand the code, even if I had spend months away from it.

This revelation sent me on a multi-year path which has culminated in the writing of this book.
    

### Software Is Alive ###

All software in a state of active development can be considered a living thing. Active development constantly changes and evolves the internals of our software. This means, no matter how hard we try, things will change beneath us.

Even as things change, it should be a reasonable assumption that we can do things to create a space where we can stand. A raft atop the rising tide, so to speak.

If we don't create safe places to stand as we work, we are liable to sink into the depths of our own code, never to emerge again.

The fact that software is alive is also a boon. This means many mistakes can actually be repaired or improved. Nothing is required to be permanent, and we have the ability to capture what we learn in the code we write.


    

### The Takeaway ###

If there is one thing I would like my readers to take away from this book, it would be the notion that the source code we write is actually a document for humans. This is not a new idea, and it can be seen written on the face of everything we do.

Grace Hopper, noted as the inventor of the compiler, created a compiler for hand-written documents because she believed that source code can be written in such a way that people can understand it without needing to decipher binary streams.

Robert "Uncle Bob" Martin wrote an entire book about creating source code for people instead of machines.

These two people are not alone in this world. There are millions of programmers in the world today, and of those millions, I feel safe to guess there are thousands actively advocating for better source documents.

I had no desire to sit down and write "Clean Code Part Two." That book exists and it has a lot of valuable information in it. Instead, I want this book to be something each software developer can keep close at hand and use it as a way to guide their hand when they aren't sure what to do next.

There is an old joke, "there are two hard things in computer science: naming, cache invalidation, and off-by-one errors."

I hope to offer some answers for the naming concern. The other two are left as an exercise for the reader.

    
    

## Variables, Parameters, and Constants ##


### Variables ###

#### Prefer Read-Only ####

When creating variables, prefer to create them once, read them often, and edit them infrequently. The closer your variables are to being local constants, the more understandable your intent will be.

#### Describe the Meaning of the Stored Value ####

Each value in your software exists for a reason. Values are rooted in solving a problem for people. This means each value has an intended purpose. Opt to capture the purpose of the value in the variable name.

#### Use Affirmative or Negative Language for Booleans ####

Boolean values are always true or false. This means they are the answer to a question. When creating variables which store boolean values, name them in the affirmative form `theLightBulbIsNew`, or the negative form `theLightBulbIsNotNew`.

#### Prefer Affirmative Definitions ####

If at all possible, instead of simply negating an affirmative variable name, opt for capturing the meaning of the negation. Instead of writing `const theLightBulbIsNotNew`, prefer `const theLightBulbIsUsed` or `const theLightBulbIsOld`.

#### Prefer Active Voice ####

When creating a variable name for a boolean value, the active voice will convey a stronger sense of the intent of your variable. Consider the following:

`const theFireHasBeenLit = true;`

Versus:

`const theFireIsLit = true;`

Better yet:

`const theFireIsBurning = true;`

Each of these forms reduces the noise in your code, and amplifies the meaning of the variable in question.

#### Prefer Full-Word Names ####

At one point, languages like C had a variable name character limit of 31. Such constraints are not common in modern languages. When creating variable names, prefer using full words instead of abbreviations or acronyms.

Instead of

`const maxNumBytes = 30`
`const minUmbrlsStock = 5`

Use full words to communicate your meaning.

`const maximumNumberOfBytes = 30`
`const minimumUmbrellasStocked = 5`

#### Use Acronyms When They Are More Common Than The Full Name ####

Some acronyms are actually more common than their full-word name. Instead of typing out all of the words, prefer the acronym as it will provide more clarity to the reader.

Instead of

`let selfContainedUnderwaterBreathingApparatusAirTanksCount = 10`

prefer

`let scubaAirTanksCount = 10`

#### Avoid Single-Letter Variable Names ####

Rather than using variable names such as `r`, `s`, or `g`, prefer to declare what the value actually is. This kind of variable naming has become common in lambda expressions and often suppresses understanding and context building.

Instead, opt for words to describe what is being acted upon.

```javascript
records.map(record => record.id);
songs.filter(song => song.name.length < 15);
const gongStriker = gong => gong.strike();
```

#### When Using Single-Letter Names, Follow Common Convention ####


    

### Events, Actions, and Behaviors ###

#### Use Past Tense for Completed State ####

#### Use Present Tense, Active Language, For Transitioning State ####

#### Use Future Test For Unexecuted State Transition ####


    
    

## Expressions ##

(subsection "./sections/creating-meaning.md")
    

<!-- GENERATED DOCUMENT! DO NOT EDIT! -->
    