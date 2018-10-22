# Array Concept Review

## Introduction

Much of _life_ is understood by grouping things together based on
a common characteristic. For instance, here are some groups you might have
heard of:

- Family last name (The Bradys)
- Hogwarts House (Slytherins)
- Band name (e.g. The Beatles)
- Grocery list

In most programming languages, the thing for storing a collection is called an
"array". Arrays, as we'll learn, can also be used to order the things in the
collection ("get the youngest Brady" or "most senior Slytherin").

Working with collections is one of the most important tools to master in your
programming career.

## Learning Goals

1. Recognize array as a core programming tool
2. Recognize array vocabulary word: Element
3. Recognize array vocabulary word: Index
4. Recognize array core property: Ordering
5. View an `Array` in Ruby
6. Access Array Elements Through Bracket-Notation in Ruby
7. Create Arrays in Ruby

## Recognize Array As a Core Programming Tool

The bulk of **_all_** programming work is taking a inputs, doing some change to
them (combining them, filtering them, mushing them together, etc.), and
producing a new output.

The data needed as input for a process **or** made as output by running a
process needs a place to live. An array allows programmers to create those
places **and** say to each other "there are a bunch of individuals here, but,
together, they make up something else, a _collection_, and knowing that fact is
important."

When programmers wish to communicate that the _collection_ is important they
use a _data structure_: a thing that structures data based on rules. The array
is one of the most common and most essential data structures. It allows
programmers to create a group and assign it to a variable name. But, like all
_data structures_, it has rules and we'll explore them in this lesson.

### Example Data

<iframe width="560" height="315" src="https://www.youtube.com/embed/FX20kcp7j5c" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Let's establish an example for the rest of this lesson: the Shark Family as
ordered by age, youngest to oldest. To keep things simple, we'll express this
list in English not in any programming language.

1.  "Baby Shark"
2.  "Mama Shark"
3.  "Papa Shark"
4.  "Grandma Shark"
5.  "Grandpa Shark"

## Recognize Array Vocabulary Word: Element

An individual member of an array is called an _element_. In our example, "Baby
Shark" is an _element_. "Grandma Shark" is also an element. All arrays are
collections of _elements_.

## Recognize Array Vocabulary Word: Index

Earlier we mentioned that _data structures_ have rules. **The main rule of the
array data structure is that the individual _elements_ in an array can be
"pointed to" by providing a number (Integer) and the name of the array.**

In our example, we might say that in the lowest index (`1`) of the "Shark
Family" array, we have "Baby Shark." In the highest index (`6`) of the "Shark
Family" array, we have "Grandpa Shark."

Some programming languages start counting the first element at `1`. Most start
counting the first element at `0`. Ruby, JavaScript, Python and Java all index
arrays starting at `0`. Lua, Smalltalk and Fortran start indexing at `1`.
Languages that start array indexing with `0` are called "zero-indexed."
Languages that start array indexing with `1` are called "one-indexed."

Some languages (like Ruby) will let you use a negative index to go "from the
last position" other languages (like JavaScript) will not let you do this!

> **Aside**: Some people will tell you that languages that start arrays at `1`
> are "stupid." Some very bright people have done amazing things with "1-index"
> languages (like putting mankind on the moon or building the Boeing 747).

## Recognize Array Core Property: Ordering

Because arrays' _elements_ are _indexed_ by numbers that increase from a
starting number by whole numbers, arrays can be used to keep _elements_ in
order.

Arrays can hold elements that aren't sorted (like "The Beatles" above), but
programmers use the ordering property of the indexes to keep the collection in
order. If the Shark family had a *new* baby shark we would put her in index 1
and move all the other sharks up one. You'll have chance to work with the
ordering property hands-on shortly.

Let's look at our Shark family in the language of code.

## View an `Array` in Ruby

In this example, imagine that the constant `SHARK_FAMILY` points to an `Array`
and has already been defined for us (we'll learn to define `Array`s in a
moment).

In Ruby, we can print out an Array's contents with `p` and the name of the
`Array`. Here, in IRB, we are printing out `SHARK_FAMILY`:

```ruby
2.3.3 :003 > p SHARK_FAMILY
["Baby Shark", "Mama Shark", "Papa Shark", "Grandma Shark", "Grandpa Shark"]
 => ["Baby Shark", "Mama Shark", "Papa Shark", "Grandma Shark", "Grandpa Shark"]
```

Ruby prints out the `Array` by putting square-brackets (`[]`) at the beginning
and end of the `Array`. Between the brackets it lists each of the elements,
separated by commas (`,`). It _does not_ show the indexes of each of the
elements.

Looking at this output, we can see that there are 5 shark family members. At
the lowest index, or "index 0" of `SHARK_FAMILY`, is "Baby Shark." At the
largest index, or "index 4" of `SHARK_FAMILY`, is "Grandpa Shark."

## Access Array Elements Through Bracket-Notation in Ruby

We can get a single element by use of _bracket notation_. Programmers use
_bracket notation_ instead of saying something like "index 2 of
`SHARK_FAMILY`." The general form is: `Array_Name[index]`.

```ruby
SHARK_FAMILY[0] #=> "Baby Shark"
SHARK_FAMILY[2] #=> "Papa Shark"
SHARK_FAMILY[-1] #=> "Grandpa Shark"
```

> **TYPOGRAPHICAL NOTE** When you see `#=>` it means "this is what the
> programming language returns. It's a common syntax for helping programmers
> who are reading documentation understand how something works. You'll see it a
> lot in technical documentation.

## Create Arrays in Ruby

OK, now that we've learned to work with Ruby `Arrays` that are created for us,
by printing them out and accessing their elements, let's make our own `Array`.

Ruby has two ways to create `Array`s from scratch:

- Array literal syntax
- `Array.new`

### Array Literal Syntax

Because reading arrays as lists of elements separated by `,` and enclosed by
`[]` is so intuitive, Ruby added the ability to _create_ an `Array` by entering
the output, like you saw above, _in_ literally. An `Array` [Literal][literal] is
a list of elements, separated by `,` and, you guessed it, enclosed by `[]`.

The following code creates an `Array` and assigns it to the variable name
`shark_family_by_age`.

**_This is the most common way to create `Array`s from scratch._**

```ruby
shark_family_by_age = [ "Baby Shark", "Mama Shark", "Papa Shark", "Grandma Shark", "Grandpa Shark" ]
```

Ruby doesn't care if you put the code all on one line or separate it prettily:

```ruby
shark_family_by_age = [
  Baby Shark,
  Mama Shark,
  Papa Shark,
  Grandma Shark,
  Grandpa Shark ]
```

Programmers sometimes write their `Array` literals to communicate something to
other programmers reading the code:

```ruby
# Generations per row
shark_family_by_age = [
  Baby Shark,
  Mama Shark, Papa Shark,
  Grandma Shark, Grandpa Shark
]
```

### Array.new Syntax

Consulting the [`Array` documentation][array doc] for `new` we see that we can
create `Array`s using a constructor method called `Array.new`. To keep things
simple, we'll not go into using this method other than to say:

1. It exists and you might encounter it
2. It's very useful for when you want to create an `Array` with a specific
   number of elements and, optionally, want to set them all to a value

As an example, you can make the 1960's vintage "Batman" TV show [theme][batman]
song using the `Array` constructor method.

```ruby
batman_song = Array.new(16, "na-")
p batman_song #=> ["na-", "na-", "na-", "na-", "na-", "na-", "na-", "na-", "na-", "na-", "na-", "na-", "na-", "na-", "na-", "na-"]
p "Batman!" #=> "Batman!"
```

In all seriousness, most `Array`s are created from some data source (read from
a database, read from a file, retrieved off of the internet). When typed in
manually, `Array`s tend to loaded as `Array` literals.

## Conclusion

In this lesson, we learned about the data structure `Array`. From iPhone to
Java to Python, nearly every programming language has something like an
`Array`.  Arrays are composed of _elements_ which are accessed by an _index_.
Indexes move upward from `0` in Ruby and JavaScript. Arrays are often displayed
in programming documentation in _array literal syntax_ which is brackets (`[]`)
filled with _elements_ separated by `,`s. Array [literal][] syntax can also be
used to create Arrays. A lesser-used, but very useful, tool for creating
`Array`s is the `Array.new` method of Ruby.

## Resources

- [Arrays][]
- [Literals][]

[array doc]: http://ruby-doc.org/core-2.3.4/Array.html#method-c-new
[Arrays]: http://ruby-doc.org/core-2.3.4/Array.html
[literals]: https://docs.ruby-lang.org/en/2.0.0/syntax/literals_rdoc.html
[literal]: https://docs.ruby-lang.org/en/2.0.0/syntax/literals_rdoc.html
[batman]: https://www.youtube.com/watch?v=VSaDPc1Cs5U
