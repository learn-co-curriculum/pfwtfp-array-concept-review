# Array Concept Review

## Introduction

Much of _life_ is understood by grouping things together, in an order, based on
a common characteristic:

- Family last name (The Bradys)
- Hogwarts House ("Slytherins")
- Band name (e.g. The Beatles).
- A book as made up of a collection of chapters

In Ruby, the thing for storing an ordered collection is called an "array". It
is one of the most important tools to master in your programming career. In
this lesson, we'll master the cosmic truths of the array.

## Learning Goals

1.  Recognize array as a core tool in Ruby
2.  Recognize array vocabulary word: Element
3.  Recognize that arrays are ordered by index
4.  Recognize `[]` as used for presenting `Array`s
5.  Recognize that array elements can be accessed through bracket-notation
6.  Demonstrate array creation in Ruby

## Recognize Array As a Core Tool in Ruby

The bulk of **_all_** programming work is taking a series of inputs, doing some
change to them (combining them, filtering them, mushing them together, etc.),
and producing a new output. The data needed for input or made into output needs
a place to live. We call those places _data structures_. The array is one of
the most common and most essential data structures. Nearly all programming
languages have something like an _array_. Programmers work with arrays
literally every day.

It is **_vital_** that you be skilled with arrays.

Let's establish an example for the rest of this lesson: the Shark Family as
ordered by age, youngest to oldest.

1.  "Baby Shark"
2.  "Mama Shark"
3.  "Papa Shark"
4.  "Grandma Shark"
5.  "Grandpa Shark"

## Recognize Array Vocabulary Word: Element

The individual members of an array are called _elements_. In our example, "Baby
Shark" is an _element_. "Grandma Shark" is also an element.

## Recognize That Arrays Are Ordered By Index

Within an array, **_elements are ordered_**. The elements each have an _index_
which stores their position in the array. "Baby Shark" is the first _element_.
"Grandpa Shark" is the last _element_.

Some programming languages start counting the first element at `1`. Most start
counting the first element at `0`.

We will show how to access elements in an array a little later in this lesson.

## Recognize `[]` as Used for Presenting Arrays

In Ruby, we display an `Array`'s contents by using square-brackets(`[]`).

As an example, we might want to show an `Array` of the Shark Family as ordered
by age from youngest to oldest:

> **TYPOGRAPHICAL NOTE** When you see a bit of text `Like This` it means we're
> talking about a Ruby class. An "array" is a concept, but _in Ruby_ that concept
> is used by working with the `Array` class.

```ruby
[ "Baby Shark", "Mama Shark", "Papa Shark", "Grandma Shark", "Grandpa Shark" ]
```

## Recognize That Array Elements Can Be Accessed Through Bracket-Notation

Given an `Array` like:

```ruby
shark_family = [ "Baby Shark", "Mama Shark", "Papa Shark", "Grandma Shark", "Grandpa Shark" ]
```

We can get a single element by use of _bracket notation_.

```ruby
shark_family[0] #=> "Baby Shark"
shark_family[2] #=> "Papa Shark"
shark_family[-1] #=> "Grandpa Shark"
```

> **TYPOGRAPHICAL NOTE** When you see `#=>` it means "this is what the
> programming language returns. It's a common syntax for helping programmers
> who are reading documentation understand how something works.

## Recognize Array Creation

Ruby has two primary paths for creating `Array`s from scratch:

- Array literal syntax
- `Array.new`

### Array Literal Syntax

Because showing arrays with brackets is so handy, Ruby added the ability to
_create_ arrays by simply typing this naturally-readable display content.
"Literal" here means "readable" like the word "literature" or "literacy." It's
creating an `Array` by "reading it in."

The following code creates an `Array` and is the most common way to create
`Array`s from scratch.

```ruby
shark_family = [ "Baby Shark", "Mama Shark", "Papa Shark", "Grandma Shark", "Grandpa Shark" ]
```

Ruby doesn't care if you put the code all on one line or separate it prettily:

```ruby
shark_family = [
  Baby Shark,
  Mama Shark,
  Papa Shark,
  Grandma Shark,
  Grandpa Shark ]
```

Programmers sometimes write their array literals to communicate something to
other programmers reading the code:

```ruby
# Generations per row
shark_family = [
  Baby Shark,
  Mama Shark, Papa Shark,
  Grandma Shark, Grandpa Shark
]
```

### Array.new Syntax

Consulting the [`Array` documentation][array doc] for `new` we see that we can
create an `Array` 3 ways:

| documentation                  | example                                | result                     |
| ------------------------------ | -------------------------------------- | -------------------------- |
| `new(size=0, default=nil)`     | `Array.new(3, "Bark")`                 | `["Bark", "Bark", "Bark"]` |
| `new(array)`                   | `Array.new([1,2,3])`                   | `[1,2,3]`                  |
| `new(size) {\|index\| block }` | `Array.new(3){ \|index\| index ** 2 }` | `[0,2,4]`                  |

These are, honestly, not that useful day-to-day. Sometimes you might need to
initialize an `Array` with 16 copies of some name in it like:

```ruby
batman_song = Array.new(16, "na-")
p batman_song
puts "Batman!"
```

Most `Array`s are created from some data source (read from a database, read
from a file, retrieved off of the internet). When typed in manually, they tend
to loaded as `Array` literals. Nevertheless, you need `Array.new` in your
toolbox.

## Conclusion

In this lesson, we learned about the data structure `Array`. From iPhone to Java
to Python, nearly every programming language has something like an `Array`.
Arrays are composed of _elements_ which are accessed by an _index_. Indexes
move upward from 0. Arrays are often displayed in programming documentation in
_array literal syntax_ which is brackets (`[]`) filled with _elements_
separated by `,`s. Array literal syntax can also be used to create Arrays. A
lesser-used, but very useful, tool for creating `Array`s is the `Array.new`
method of Ruby.

[array doc]: http://ruby-doc.org/core-2.3.4/Array.html#method-c-new
