---
layout: post
title: "Generating random Strings in Scala"
date: 2013-02-07 21:20
comments: true
categories: 
- CompSci
- Scala
---
Hopefully this is just the first of many posts about Scala.

``` scala Generate a String with 5 random alphanumeric characters
Random.alphanumeric.take(5).mkString
```
<!-- more -->
<code>Random.alphanumeric</code> produces a stream of type [<code>Stream[Char]</code>][1]. It's interesting that Streams are "immutable" even though they're lazy (elements are only evaluated when they are needed). This is because the "elements" of the stream are immutable (even though some haven't been realised yet). If we keep a reference to the stream, we can confirm that it always produces the same output.

``` scala Streams are immutable
val charStream = Random.alphanumeric
assert(charStream.take(100) == charStream.take(100))
```
The Stream stores computed values, so Streams can be used to memoize algorithms. This also means we have to be wary of the memory usage when consuming the Stream.

The scala doc for <code>Stream</code> has this neat (and rather mind-bending) example:
``` scala Recursive Fibonacci numbers using Streams
val fibs: Stream[BigInt] = BigInt(0) #:: BigInt(1) #:: fibs.zip(fibs.tail).map { n => n._1 + n._2 }
```
Once I wrapped my head around what <code>zip</code> does with Streams, I was still surprised by the way <code>map</code> is applied "just in time" to generate the next element of the tail. My functional programming chops are still not that juicy, but I get a sense of something quite powerful here.

[1]: http://www.scala-lang.org/api/current/index.html#scala.collection.immutable.Stream
