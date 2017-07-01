# Scoring of paradigm support
 
## Notes
 
By no means is this a perfect list; I don't think a perfect list could ever exist.
 
If you have suggestions for improvements, open an issue and/or pull request.
 
If you submit a pull request, feel free to add yourself to the credits section at the bottom.
 
You may not agree with the placement of languages in this list.
This is because "pure" single-paradigm languages basically don't exist;
most languages have elements of multiple paradigms.
There is always more than one way to solve a problem.  
<sub>And I basically just added whatever languages I felt like</sub>
 
## Purpose
 
Often times, because all languages are awful and why can't they change this it would be so much better (\*ahem\*)  
Often times, people are interested in creating small DSLs (domain specific languages) for tasks,
for educational purposes, self gratification, or because of an actual use case.
 
Paradigms listed come from resources listed in the Credits and my own experience.
This compilation aims to place a "score" on paradigm support to facilitate the comparison
of DSL utility, and potentially for use in [competition](https://codereview.meta.stackexchange.com/a/7311/100439).
 
You can claim points from multiple categories.
They are not supposed to be mutually exclusive (example: most Structured Programming is also Imperative).
Note that individual points may be mutually exclusive, however.
 
## General (3 points)
 
This is just a few score-worthy additions which don't fit into a paradigm.
 
- Arrays. Fixed-sized ordered collections of elements. Code can extract individual elements or operate on the full thing. (1 point)
- REPL. "Read Eval Print Loop". Provide a simple REPL environment for running snippets of code. (1 point)
- Try it Online! Provide a way to run your code online. ([Dennis](https://stackexchange.com/users/918086/dennis) and [TIO](https://tio.run/#) may be willing to help.) (1 point)
 
## Imperative (4 points)
 
Probably the simplest and most obvious paradigm. (Also called Procedural.)
 
A source file consists of a series of instructions, which are executed in order.
A `goto` statement allows execution to jump forward or back within the list of instructions.
 
Note that source order does not have to be top-to-bottom, it could be 2D!
 
### Languages:
 
- assembly
- [><>](https://esolangs.org/wiki/Fish)
 
### Scoring:
 
- Allow the execution of multiple instructions in source order. (1 point)
- Allow the use of a `goto` statement to jump forward/back in execution order. (1 point)
- Allow the use of a command to change source execution direction. (1 point)
- Allow the conditional application of the two above. (You can claim this with only one of the two.) (1 point)
 
## Structured (5 points)
 
[`goto` Considered Harmful.](http://david.tribble.com/text/goto.html)
 
Structured programming is about the use of clear constructs to describe control flow in a program.
 
Value bindings are also commonly limited to the scope which they appear in.
 
### Languages
 
- [C](https://en.wikipedia.org/wiki/C_(programming_language))
- [Chef](https://esolangs.org/wiki/Chef)
 
### Scoring:
 
- Allow the use of a `if` statement to conditionally execute a block of code. (1 point)
- Allow the use of a `for` statement to execute a block of code over a series of values. (1 point)
- Allow the use of a `while` loop to execute a block of code multiple times while a condition is true. (1 point)
- Allow the use of `break`/`continue` to exit a loop or advance to the next iteration early respectively. (1 point)
- Lexically scope value bindings to the block which they appear in. (1 point)
 
## Typed (4 points)
 
A typed language is one where data has an intrinsic meaning to it.
Note that this does not specify whether a language is statically or dynamically typed.
Data has a tag associated with it, put there by the language, that says what kind of data it is.
 
For the purpose of this document, all data is a number. If you enforce further information
about the format of that number other than sign-magnitude or two's-complement, it is typed.
 
Thus, if you have a `Character` which associates numbers with the [ASCII table](http://www.asciitable.com/),
this says "this number is a character from this table" and is thus a distinct type.
 
A type may consist of a single primitive value or multiple.
A type with multiple primitive values associated is a compound type.
 
### Scoring:
 
- Associate data with a type. This type must be discoverable by user code to allow decisions. (1 point)
- Statically (before execution) enforce correct typing. (1 point)
- Allow compound types. User code must be able to work with the compound type and extract the components. (1 point)
- Allow user defined types. (1 point)
 
## Function Oriented (10 points)
 
Function Oriented languages focus on the use of functions to model data.
 
A function is a named block of code that optionally takes parameters
and optionally returns a value when called.
 
Functional languages often encourage the use of function composition rather than
procedural lists of commands and value bindings. See also Tacit / Point-Free.
 
### Languages
 
- [Haskell]
 
### Scoring
 
- Allow the definition and calling of subroutines (0-argument no-return functions). (1 point)
- Allow the definition and calling of functions (0-argument with optional return). (1 point)
- Allow the definition and calling of functions (n-argument with optional return). (1 point)
- Allow functions to be recursive (call themselves). (1 point)
- Implement the [tail call](https://en.wikipedia.org/wiki/Tail_call) optimization for recursion. (2 points)
- Allow functions to take functions as arguments. (1 point)
- Implement a [`map`](http://www.globalnerdy.com/2016/06/23/map-filter-and-reduce-explained-using-emoji/) opration. (1 point)
- Implement a [`filter`](http://www.globalnerdy.com/2016/06/23/map-filter-and-reduce-explained-using-emoji/) operation. (1 point)
- Implement a [`reduce`](http://www.globalnerdy.com/2016/06/23/map-filter-and-reduce-explained-using-emoji/) operation. (1 point)
 
## Object Oriented (6 points)
 
Object Oriented programming is about Objects.
 
<dl>
<dt>Object
<dd>A bundle of data and operations that can be applied to that data
<dt>Method
<dd>An Object associated function that operates on a value of that type
</dl>
 
Object Oriented programming is also about Inheritance and Specialization.
 
<dl>
<dt>Inheritance
<dd>Given two different Object types, one Object can be a subset of another, acting as the second with added functionality
<dt>Specialization
<dd>Given a child Object, it can redefine parts of teh parent's contract to behave in a more specialized manner
</dl>
 
### Languages
 
- [Java](https://www.java.com/en/)
- [C#](https://docs.microsoft.com/en-us/dotnet/csharp/csharp)
 
### Scoring
 
- Allow definition of Objects (associated data and functionality). (1 point)
- Allow method call syntax (find a function on this object and run it with this object). (1 point)
- Allow single inheritance (Objects may have one and only one parent). (1 point)
- Allow multiple inheritance (Objects may have multiple parents). (1 point)
- Allow Object Specialization. (1 point)
- Allow dynamic method dispatch (given a value of parent type, call the appropriate child-defined function based on runtime type). (1 point)
 
Note that to implement methods you need to implement functions from the Function Oriented section.
 
## Protocol Oriented (4 points)
 
A term pioneered by Apple with Swift, protocol-oriented code allows the definition of "interfaces" which an object can adhere to.
A value binding can then be declared to be of that interface type, and can be set to any object which fulfils the interface.
 
The key part of protocol oriented code is that functions can and should be defined to take interfaces rather than concrete objects.
 
### Lanugages
 
- [Swift](https://swift.org/)
 
### Scoring
 
- Allow a type to implement at least one interface. (0 points, required)
- Allow an interface to promise methods from implementing types, which must be present. (1 point)
- Allow a type to implement an arbitrary number of interfaces. (1 point)
- Allow value bindings to be of a protocol type and dynamically dispatch function calls to the correct function. (1 point)
- Allow methods to be defined on the protocol itself, and overridden in implementing types. (1 point)
 
## Tacit / Point-Free (2 points)
 
Tacit programming or point-free style based on function composition without naming arguments/points of operation.
 
The key requirement for programming in a point-free style is function bindings and partial application.
 
<dl>
<dt>Function Composition
<dd>Given some <code>f(x)</code> and some <code>g(x)</code>,
the composition of <code>f</code> and <code>g</code> is <code>f(g(x))</code>.
<dt>Partial Application
<dd>Application of some but not all function arguments, leaving the rest to be specified with use of the binding
</dl>
 
### Scoring
 
- Allow function composition in a point-free style. (e.g. instead of `fg(x) = f(g(x))`, `fg = f . g`.) (1 point)
- Allow partial application of a function. (e.g. `g = f(5)` results in `g(y) = f(5,y)`.) (1 point)
 
## Literate (1 point)
 
Literate programming allows the insertion of arbitrary text marked by some marker token.
The arbitrary text is ignored when running the program.
 
Thus, program authors may explain their code in-line with the code itself.
 
Common literate targets include compiling the code snippets in a markdown document
or rendering documentation comments from the source as a separate document.
 
### Scoring
 
- Allow blocks of arbitrary text in your source files. (1 point)
 
## Embedded rich data
 
Instead of just plain text, you also can have images, mathematical notation, charts, etc.
 
There isn't really a point value I can put on this.
Without [JetBrains MPS](https://www.jetbrains.com/mps/) or a similar tool, it's probably way too impractical.
And this is a field not explored much.
 
## Credits
 
- [LMU Computer Science notes on programming paradigms](http://cs.lmu.edu/~ray/notes/paradigms/)
- [Yevgeniy Brikman -- Six programming paradigms that will change how you think about coding](http://www.ybrikman.com/writing/2014/04/09/six-programming-paradigms-that-will/)
- [Esolang wiki](https://esolangs.org/)
- [Wikipedia - Programming Paradigm](https://en.wikipedia.org/wiki/Programming_paradigm)
- @CAD97
 
