---
title: API Reference

language_tabs:
  - purescript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

PureScript is a small strongly typed programming language that compiles to JavaScript.

PureScript’s expressive type system and lightweight syntax make it simple to define domain-specific languages, which can be used to solve problems like templating the DOM. Bindings also exist for libraries such as React and Angular.js.

# Syntax Basics

Much of PureScript's core syntax should be familiar to anyone who has ever used a typed language like Haskell, F# or Elm. However, there are some distinct differences between PureScript and other languages. The examples in this document give an overview of the most important language constructs and their respective syntax.

## Simple Primitives

Primitive | Example
--------- | ------- |
Boolean | true
String | "Hello World"
Char | 'a'
Int | 42
Number | 42.0
Array Int | [1, 2, 3]
Record  | { pure: "script" }


Operation | Example
--------- | ------- |
Equality | a == b
String Concatenation | "Hello, " <> "World"
Accessing a Record Field | author.name

## Defining your own Types

PureScript allows you to define your own Types. To do that, you use the `data` keyword followed by the name of the Type. Let's go ahead and define us an `Address` Type.

```purescript
data Address = Address
  { street :: String
  , city :: String,
  , zip :: String
  }
```

How do you read this now? Well, we've just defined how an `Address` should look like. Means, since it is a Record, it (always) has the following fields: `street`, `city` and `zip`. All three fields require to be of type `String` as well.

> Notice that you're not creating an instance of this type! All you did is that you _defined_ how an `Address` should look like.

So far so good! We've now defined ourselfs an Address Type.
Now, let's create an instance off of it:

```purescript
let address = Address { street: "1337 Purescript Ave", city: "Purewood", zip: "1337" }
```

Awesome, we now have an instance of type `Address` which we can use to do a lot of great stuff, like... uhm... you know... sending it to a server or whatever pleases you.

Dont belive me? Let's see what the PureScript REPL says:

```shell
$ :type address
Address
```
