# Common Collections

Rust’s standard library includes a number of very useful data structures called
_collections_. Most other data types represent one specific value, but
collections can contain multiple values. Unlike the built-in array and tuple
types, the data that these collections point to is stored on the heap, which
means the amount of data does not need to be known at compile time and can grow
or shrink as the program runs. Each kind of collection has different
capabilities and costs, and choosing an appropriate one for your current
situation is a skill you’ll develop over time. In this chapter, we’ll discuss
three collections that are used very often in Rust programs:

- A _vector_ allows you to store a variable number of values next to each other.
- A _string_ is a collection of characters. We’ve mentioned the `String` type
  previously, but in this chapter we’ll talk about it in depth.
- A _hash map_ allows you to associate a value with a specific key. It’s a
  particular implementation of the more general data structure called a _map_.

To learn about the other kinds of collections provided by the standard library,
see [the documentation][collections].

We’ll discuss how to create and update vectors, strings, and hash maps, as well
as what makes each special.

[collections]: https://doc.rust-lang.org/std/collections/index.html
