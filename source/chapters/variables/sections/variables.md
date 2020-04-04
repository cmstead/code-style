<!--bl
(filemeta
    (title "Variables")
)
/bl-->

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

