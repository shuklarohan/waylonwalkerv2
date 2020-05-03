---
templateKey: blog-post
related_post_label: Check out this related post
tags: []
twitter_announcement: I just dropped a new post check it out.
path: js-explicit-vs implicit-return
title: Explicit vs Implicit Returns in Javascript
date: 2020-05-03T11:55:00Z
status: published
description: ''
related_post_body: ''
related_post: []
cover: "/static/explicit-vs-implicit-returns-in-javascript.png"
twitter_cover: "/static/explicit-vs-implicit-returns-in-javascript.png"
twitter_week_1: ''
twitter_week_2: ''
twitter_month_1: ''
twitter_month_3: ''
short_url: ''
devto-url: ''
devto-id: ''

---

Often when reading through javascript examples you will find some arrow functions
use parentheses `()` while others use braces `{}`.  This key difference is that 
parentheses will implicitly return the last statement while braces require an
explicit return statement.  It is important to understand the difference between
them because it is likely that you will find code examples of both and trying
to edit code written differently than you're used to may have unintended consequences.

## Arrow functions

Arrow functions are one-liner functions in javascript that have two main syntactical ways to create the code block.  with parentheses and braces.  Let's take a look at both ways of creating arrow functions so that when we come accross them in the wild it will all make sense.

## implicit returns

Here is an example of an arrow function that will implicitly return the last
statement without the return keyword.  I believe that these are a bit more restricted
in that you cannot set variables inside  them.  They are a little bit more concise
and great for **one-liners.**

``` javascript
const implicit = thing => (thing)
undefined
implicit('hi')
"hi"
```

**Note** that the parentheses are not required for this example and not having 
parstheses or braces are implicitly returned as well.

``` javascript
// same as above
const implicit = thing => thing
undefined
implicit('hi')
"hi"
```

## explicit returns

In the following example the curly braces create an arrow function that must 
explicitly return anythinig that you want to return from the function. Since the
return keyword is never used the function returns `undefined` by default.


``` javascript
// missing return statement
const explicit = thing => {thing}
undefined
explicit('hi')
undefined
```

In this example using the return keyword will cause the function to return `thing`
and behave similarly to our implicit return.

``` javascript
// same as original
const explicit_return = thing => {return thing}
undefined
explicit_return('hi')
"hi"
```

## Multiline arrow functions

Until writing this article I was unaware that you could not have a mutiline arrow
function with an implicit return statement.  I tried myself and ran into some issues.
I also tried to find examples online and could not find one.  If it is possible to
write something like below, let me know.

``` javascript
// more complex example
// only possible with an explicit return
const sayHello = who => {
    const greeting = 'Hello '
    const message = greeting + who
    return message
    }
undefined
sayHello('Waylon')
"Hello Waylon"
```