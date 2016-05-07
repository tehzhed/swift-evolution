# Shorthand syntax for variable initalization from subscriptable type

* Proposal: [SE-NNNN](https://github.com/apple/swift-evolution/blob/master/proposals/NNNN-name.md)
* Author(s): [Daniele Riccardelli](https://github.com/tehzhed)
* Status: **[Awaiting review](#rationale)**
* Review manager: TBD

## Introduction

A great feature of the Python programming language that aims to conciseness and simplicity of the code is the possibility to unpack subscriptable types.

Swift is missing such an elegant feature, but, in a similar fashion, allows to initialize variables from tuples like this:
```swift
let (name, surname, nickname) = ("Daniele", "Riccardelli", "tehzhed")
```

## Motivation

Nonetheless, this syntax is counterintuitive: the left-hand side in fact doesn't initialize a tuple, but 3 distinct variables. 
What is also counterintuitive is that, differently from Python, in Swift there is no way of unpacking from types other than tuples.

The idea is to simplify the syntax and allow it to be used, similarly to Python, on all subscriptable types to unpack values.

Swift-evolution thread: [link to the discussion thread for that proposal](https://lists.swift.org/pipermail/swift-evolution)

## Proposed solution

Describe your solution to the problem. Provide examples and describe
how they work. Show how your solution is better than current
workarounds: is it cleaner, safer, or more efficient?

## Detailed design

The idea is to slightly change and generalize the unpacking syntax in the following way:
```swift
let name, surname, nickname = ("Daniele", "Riccardelli", "tehzhed")
```
In a fashion similar to the one found in Python (where this idea originates from).
[Swift is a powerful and **intuitive** programming language](https://github.com/apple/swift-evolution/blob/master/process.md), and it is indeed intuitive to consider every subscriptable type to allow unpacking values.

Therefore, this would be allowed:
```swift
let name, surname, nickname = ["Daniele", "Riccardelli", "tehzhed"]
```
Similarly would happen with non constants ```var```s.

## Impact on existing code

This proposal suggests a new shorthand syntax that doesn't break compatibility with existing code.

## Alternatives considered

One alternative could be to use the syntax currently used to unpack tuples into variables for all subscriptable types:

```swift
let (name, surname, nickname) = ["Daniele", "Riccardelli", "tehzhed"]
```

While this would still allow more concise and readable code, would still be less intuitive and slightly more verbose than the approach suggested above.

-------------------------------------------------------------------------------

# Rationale

On [Date], the core team decided to **(TBD)** this proposal.
When the core team makes a decision regarding this proposal,
their rationale for the decision will be written here.
