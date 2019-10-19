# What this is
I watched [Logic for CS (lecture 1)](https://youtu.be/kCEAFjjTJyU), this is the note I took from it.


## About This Course
This is a course on logic, which is a mathematical foundation of Computer Science


## Goals - what we are looking for
1. Concrete skills for dealing with logics
2. Conceptual understanding of logic
3. Insights on things such as undecidability, [Gödel's theorem](https://en.wikipedia.org/wiki/Gödel%27s_incompleteness_theorems)


## What is logic?
Logic is not about figuring out what is true and what is false. It is about how to reliably get from assumptions to conclusions.

The most famous logical argument:
```
If all men are mortal,
and if Socrates is a man,
Socrates is mortal.
```

Once again, logic does not concern if some statements are true or not. It concerns how to draw conclusions from given assumptions.

Logic can be at first glance straight-forward, but it can be complicated. Examples:
* [Russell's Paradox](https://en.wikipedia.org/wiki/Russell%27s_paradox) - this called for a formal basis for mathematical logic.
* [Berry Paradox](https://en.wikipedia.org/wiki/Berry_paradox)

We need something better than our common sense when dealing with mathematical proofs, or when analyzing computer programs etc.


## Formal Languages for Logic

### Natural Languages are Fallible
```
Nothing is better than eternal happiness.
McDonald's hamburgers are better than nothing.
McDonald's hamburgers are better than eternal happiness.

McDonald's > nothing > eternal happiness
```

### Formal languages this course covers/uses/focuses on
* [Propositional Logic](https://en.wikipedia.org/wiki/Propositional_calculus) - simple language, makes you focus on what you're trying to do
* [First-order Logic](https://en.wikipedia.org/wiki/First-order_logic) - sometimes too technical
* [Temporal Logic](https://en.wikipedia.org/wiki/Temporal_logic) - very relevant to Computer Science


## Definition of Propositional Logic
Distinction between Syntax & Semantics becomes important when it comes to defining formal languages.

### Defining the Syntax
The set of all valid propositional statements is an infinite set, so how do we formally/precisely define an infinite set?
* Make a list of all members in the set - not possible with infinite sets.
* Define by a common characteristic shared between the members in the set (e.g. Numbers divisible by 2) - what if there are no such handy common properties?
* Define inductively

### Inductive Definitions of Sets
Start with a core set, next define the set of operations, then inductively obtain the set containing the core, closed under the operations.

Set of all blood relatives of mine can be obtained in this way, for example.
```
Core set: { me }
Operations: { son_of(), wife_of(), ... }
```

In a formalized way, we can say:

An inductive definition of a set consists of:
1. `X`, the universe set
2. ![A subset of or equal to X](http://latex.codecogs.com/svg.latex?A%20%5Csubseteq%20X), the core set
3. `P`, a finite set of operations, where an operation is a function from `X` (arity may vary) -> `X`

... and ![B subset of or equal to X](http://latex.codecogs.com/svg.latex?B%20%5Csubseteq%20A) is said to be closed under `P`, if for every ![b1 to br in B](http://latex.codecogs.com/svg.latex?b_{1},...,b_{r}%5Cin%20B) and ![f in P](http://latex.codecogs.com/svg.latex?f%20%5Cin%20P), ![f b1 to br is in B](http://latex.codecogs.com/svg.latex?f(b_%7B1%7D%2C...%2Cb_%7Br%7D)%20%5Cin%20B)

... and the set defined inductively from `X`, `A`, and `P`, denoted `I(A, P)`, is _the smallest subset of `X` that contains `A` and is closed under `P`_, or,

![Definition of I(A, P) using a set theoretical notation](http://latex.codecogs.com/svg.latex?I(A%2C%20P)%20%3A%3D%20%5Cbigcap%20(B%20%5Cin%20X%3B%20A%20%5Csubseteq%20B%2C%20B.is%5C_closed%5C_under(P)))

