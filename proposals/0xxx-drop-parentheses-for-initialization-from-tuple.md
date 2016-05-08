# Drop parentheses for initalization from	tuple

* Proposal: [SE-NNNN](https://github.com/apple/swift-evolution/blob/master/proposals/NNNN-name.md)
* Author(s): [Daniele Riccardelli](https://github.com/tehzhed)
* Status: **[Awaiting review](#rationale)**
* Review manager: TBD

## Introduction

The syntax for initialization from tuple is a bit more
verbose than needed, i.e. why not simply drop the tuple parentheses and go
from this :
```swift
let (name, surname) =  ("John", "Doe")
```

to this:
```swift
let name, surname =  ("John", "Doe")
```

similarly to what Python does with "unpackable" types:
name, surname = ("John", "Doe")


## Motivation

This is not a revolution, but if the concern is the trade-off between conciseness and readability, I think this way we are being more concise while not losing points in readability.

Swift-evolution thread: [link to the discussion thread for that proposal](https://lists.swift.org/pipermail/swift-evolution/Week-of-Mon-20160502/016804.html)

## Proposed solution

My suggestion is simply to go from this syntax:
```swift
let (name, surname) = ("John", "Doe")
```

to this:
```swift
let name, surname = ("John", "Doe")
```

Of course, using constants here as an example, but the same syntax would be used to initialize non constants ```var```s.

## Impact on existing code

This proposal suggests a syntax change that would break compatibility with existing code. Nonetheless, accounting for this syntax update is straightforward and simply consists of getting rid of opening and closing parentheses when unpacking a tuple. Therefore this line:
```swift
let (name, surname) = ("John", "Doe")
```
would have to be replaced with this one:
```swift
let name, surname = ("John", "Doe")
```

-------------------------------------------------------------------------------
