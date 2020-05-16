<!--bl
(filemeta
    (title "Creating Meaning")
)
/bl-->

An expression in any programming language can be thought of as an executable composition of logical parts which return a value. In a literary context, however, we can nudge the meaning in a different, but equally powerful way. An expression in your source documents is a composition of atomic units to create a meaningful linguistic whole. Though the first definition is interesting in a technical context, the second meaning of expression is what we will explore.

Humans very rarely think, or speak with logical correctness, and they never feel that way. It is important to understand that any written communication will convey more than the simple meaning as written on the page. It is most common that intonation and nuance will accompany the words. The same can be said for source documents. This means, other developers will actually have a feeling, or sense about your source, given its structure and composition.

This source composition is what makes the written expression so important.

If variable names and values are the atomic parts of our code, the most fundamental aspect of communication with people is the expression. Expressions both hold logical value for the software being authored and the people who will, ultimately read the document.

Thinking about expressions, it can be said that some values and variables are, in fact, expressions. This is reflected in natural language as well. In English we say things like "oh," and "yes" as complete expressions of thought. In the same way, some of the smallest expressions we can work with are single-name behaviors.

We see expressions in code which look like "updateRecord()" or "moveServo()." These are single-name, atomic expressions. Every other expression will be either a combination on non-expression names and values, or combinations of complete expressions.

#### Descrete Expressions ####

No matter the complexity of any given collection of source, or the logic which lays within, all logic will be composed of single, discrete expressions. In order to understand, and craft, meaningful expressions, it is best to understand first how they deliver information, then how they compose into a greater whole.

**Prefer names over values**

Any value may represent a complete logical expression, but it is unlikely to provide deeper insight into the program as a whole. By naming a value, it conveys a certain context, even if the name is the same as the value.

*example*

`'modified';`

versus

`const modified = 'modified'; modified;`

The string `'modified'` tells us the state of something, but not the context. This could be a string fragment which will be used to convey meaning to the user, but not directly to the programmer. Equally, this string could actually represent the state of something within the software itself. By giving a variable the same name as a string, it becomes clear that `modified` is actually meaningful within the context of the source. Each of these will actually mean something different to the next reader.

**Prefer names to clauses**

It's common to see conditional clauses which are a rats nest of values and references, which make it hard to understand the meaning of the condition. Losing the meaning can mean losing the reader to another section of the code. This is especially dire when conditions are tricky or loaded with context. Ideally the reader will understand enough at first blush to feel confident in reading on.

*example*

```javascript
if(userData.data.name.last.slice(0, 1).toLowerCase() > 'm'){
    ...
```

versus

```javascript
const lastNameFallsAfterM = userData.data.name.last.slice(0, 1).toLowerCase() > 'm';

if(lastNameFallsAfterM){
    ...
```

Though some may find this example outrageous, this is actually well within the typical day for a developer reading source code. By simply capturing the single-meaning clause in a spoken language name, we can move from attempting to understand the meaning and context of the condition, to exploring what might need to be done when the last name does, in fact, fall after m.

It is worth noting, this expression of language assumes a certain shared language to begin with. If someone wasn't keen on what it would mean for a last name to fall after 'm,' this might not be enough of a context clue. I have found, however, people are generally comfortable accepting common linguistic idioms.

#### Composed Expressions ####
