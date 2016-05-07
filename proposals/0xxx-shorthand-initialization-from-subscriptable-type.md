# Shorthand syntax for variable initalization from subscriptable type

* Proposal: [SE-NNNN](https://github.com/apple/swift-evolution/blob/master/proposals/NNNN-name.md)
* Author(s): [Daniele Riccardelli](https://github.com/tehzhed)
* Status: **[Awaiting review](#rationale)**
* Review manager: TBD

## Introduction

Using Python's terminology, as of today Swift allows us to unpack tuples:
```swift
let (name, surname, nickname) = ("Daniele", "Riccardelli", "tehzhed")
```

But this syntax is counterintuitive: the left-hand side in fact doesn't initialize a tuple, but 3 distinct variables.
The idea is to simplify the syntax in the following way:
```swift
let name, surname, nickname = ("Daniele", "Riccardelli", "tehzhed")
```
In a fashion similar to the one found in Python (where this idea originates from).
Swift is a language designed for simplicity and intuitiveness of syntax, and therefore, it is natural to consider every subscriptable type to allow unpacking values.

Therefore, this would be allowed:
```swift
let, name, surname, nickname = ["Daniele", "Riccardelli", "tehzhed"]
```
Similarly would happen with non constants ```var```s.

Swift-evolution thread: [link to the discussion thread for that proposal](https://lists.swift.org/pipermail/swift-evolution)

## Motivation

Describe the problems that this proposal seeks to address. If the
problem is that some common pattern is currently hard to express, show
how one can currently get a similar effect and describe its
drawbacks. If it's completely new functionality that cannot be
emulated, motivate why this new functionality would help Swift
developers create better Swift code.

## Proposed solution

Describe your solution to the problem. Provide examples and describe
how they work. Show how your solution is better than current
workarounds: is it cleaner, safer, or more efficient?

## Detailed design

Describe the design of the solution in detail. If it involves new
syntax in the language, show the additions and changes to the Swift
grammar. If it's a new API, show the full API and its documentation
comments detailing what it does. The detail in this section should be
sufficient for someone who is *not* one of the authors to be able to
reasonably implement the feature.

## Impact on existing code

Describe the impact that this change will have on existing code. Will some
Swift applications stop compiling due to this change? Will applications still
compile but produce different behavior than they used to? Is it
possible to migrate existing Swift code to use a new feature or API
automatically?

## Alternatives considered

Describe alternative approaches to addressing the same problem, and
why you chose this approach instead.

-------------------------------------------------------------------------------

# Rationale

On [Date], the core team decided to **(TBD)** this proposal.
When the core team makes a decision regarding this proposal,
their rationale for the decision will be written here.
