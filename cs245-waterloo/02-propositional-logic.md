# A Formal Definition of the Language of Propositional Logic
This is a note I took watching CS245 [Lecture 2](https://youtu.be/4qilWJz_D-M)

## Inductive Definitions of Sets
For the domain X, the core set A, a finite set of operations P, let `I(A, P)` the minimal subset of X that contains A and is closed under P. We want to show that such a set always exists.

### Some Background in Set Theory
We know what ![A \cup B](https://latex.codecogs.com/svg.latex?A%20%5Ccup%20B), ![A \cap B](https://latex.codecogs.com/svg.latex?A%20%5Ccap%20B) are. We want to extend these operations, and have similar operations for collections of sets.

![\bigcap W := {x | x \in B, B \in W}](https://latex.codecogs.com/svg.latex?%5Cbigcap%20W%20:=%20%5Cleft%20%5C{x%20|%20x%20%5Cin%20B,%20B%20%5Cin%20W%20%5Cright%20%5C})

Examples:
* ![example of \bigcap](https://latex.codecogs.com/svg.latex?W%20=%20%5Cleft%20%5C{%20%5Cleft%20%5C{a%20%5Cright%20%5C},%20%5Cleft%20%5C{a,b,c%20%5Cright%20%5C},%20%5Cleft%20%5C{a,b%20%5Cright%20%5C}%20%5Cright%20%5C},%20%5Cbigcap%20W%20=%20%5Cleft%20%5C{%20a%20%5Cright%20%5C})
* ![example of \bigcap](https://latex.codecogs.com/svg.latex?W%20=%20%5Cleft%20%5C{(-r,%20+r)%20|%20r%20%5Cin%20R,%20r%20>%200%20%5Cright%20%5C},%20%5Cbigcap%20W%20=%20%5Cleft%20%5C{0%20%5Cright%20%5C})
* ![example of \bigcap](https://latex.codecogs.com/svg.latex?W%20=%20%5Cleft%20%5C{(0,%20r)%20|%20r%20%5Cin%20R,%20r%20>%200%20%5Cright%20%5C},%20%5Cbigcap%20W%20=%20%5Co)

Similary, ![\bigcup W := set of all x's such that there exists some B \in W, x \in B](https://latex.codecogs.com/svg.latex?%5Cbigcup%20W%20:=%20%5Cleft%20%5C{%20x|%20%5Cexists%20B%20%5Cin%20W,%20x%20%5Cin%20B%20%5Cright%20%5C})

Examples:
* ![example of \bigcup](https://latex.codecogs.com/svg.latex?W%20=%20%5Cleft%20%5C{(-r,%20+r)%20|%20r%20%5Cin%20R,%20r%20>%200%20%5Cright%20%5C},%20%5Cbigcup%20W%20=%20%5Cmathbb{R})

Claim: For every collection W and every set ![B \in W](https://latex.codecogs.com/svg.latex?B%20%5Cin%20W), following are true
1. ![\bigcap W \subseteq B](https://latex.codecogs.com/svg.latex?%5Cbigcap%20W%20%5Csubseteq%20B)
2. ![B \subseteq \bigcup W](https://latex.codecogs.com/svg.latex?B%20%5Csubseteq%20%5Cbigcup%20W)

Proof: For all ![x \in \bigcap W](https://latex.codecogs.com/svg.latex?x%20%5Cin%20%5Cbigcap%20W), since ![x \in \bigcap W](https://latex.codecogs.com/svg.latex?x%20%5Cin%20%5Cbigcap%20W), ![x \in B](https://latex.codecogs.com/svg.latex?x%20%5Cin%20B), for every ![B \subset W](https://latex.codecogs.com/svg.latex?B%20%5Csubset%20W).

### Does `I(A, P)` Always Exist?
We now say ![I(A, P) := \bigcap W](https://latex.codecogs.com/svg.latex?I(A,%20P)%20:=%20%5Cbigcap%20W), where ![W = {B | A \subseteq B, B is closed under P}](https://latex.codecogs.com/svg.latex?W%20=%20%5Cleft%20%5C{B%20|%20A%20%5Csubseteq%20B,%20B.is%5C_closed%5C_under(P)%20%5Cright%20%5C}), and such `I(A, P)` always exists because,
1. ![A \subseteq \bigcap W](https://latex.codecogs.com/svg.latex?A%20%5Csubseteq%20%5Cbigcap%20W),
2. ![\bigcap W is closed under P](https://latex.codecogs.com/svg.latex?(%5Cbigcap%20W).is%5C_closed%5C_under(P)),
3. ![\bigcap W](https://latex.codecogs.com/svg.latex?%5Cbigcap%20W) is the minimal set satisfying `i)` and `ii)`,
4. no set other than ![\bigcap W](https://latex.codecogs.com/svg.latex?%5Cbigcap%20W) satisfies `i)`, `ii)`, and `iii)`.

Proof:
1. W is defined as the collection of sets, each of which ![\supseteq A](https://latex.codecogs.com/svg.latex?%5Csupseteq%20A), and it follows that ![A \subseteq \bigcap W](https://latex.codecogs.com/svg.latex?A%20%5Csubseteq%20%5Cbigcap%20W).
2. for some ![b1 to br in bigcap W](https://latex.codecogs.com/svg.latex?b_{1},%20...,%20b_{r}%20%5Cin%20%5Cbigcap%20W), and for some ![f \in P](https://latex.codecogs.com/svg.latex?f%20%5Cin%20P), ![f(b_{1}, ..., b_{r}) \in P](https://latex.codecogs.com/svg.latex?f(b_{1},%20...,%20b_{r})%20%5Cin%20P), because if ![b_{1}, ..., b_{r} \in \bigcap W](https://latex.codecogs.com/svg.latex?b_{1},%20...,%20b_{r}%20%5Cin%20%5Cbigcap%20W), ![b_{1}, ..., b_{r} \in B](https://latex.codecogs.com/svg.latex?b_{1},%20...,%20b_{r}%20%5Cin%20B) for all ![B \in W](https://latex.codecogs.com/svg.latex?B%20%5Cin%20W), and B is required to be closed under P for all ![B \in W](https://latex.codecogs.com/svg.latex?B%20%5Cin%20W).
3. If some set X satisfies `i)` and `ii)`, that is if ![A \subseteq X](https://latex.codecogs.com/svg.latex?A%20%5Csubseteq%20X) and X is closed under P, ![X \in W](https://latex.codecogs.com/svg.latex?X%20%5Cin%20W) by definition, and it follows that ![\bigcap W \subseteq X](https://latex.codecogs.com/svg.latex?%5Cbigcap%20W%20%5Csubseteq%20X).
4. ![\bigcap W](https://latex.codecogs.com/svg.latex?%5Cbigcap%20W) uniquely satisfies `i)`, `ii)`, and `iii)`, because if some other set X also satisfies `i)`, `ii)`, and `iii)`, then by `iii)`, ![X \subseteq \bigcap W](https://latex.codecogs.com/svg.latex?X%20%5Csubseteq%20%5Cbigcap%20W), also ![\bigcap W \subseteq X](https://latex.codecogs.com/svg.latex?%5Cbigcap%20W%20%5Csubseteq%20X), thus ![X = \bigcap W](https://latex.codecogs.com/svg.latex?X%20%3D%20%5Cbigcap%20W).

Thus we know this is a valid way of defining sets, because `I(A, P)` always exists, and is uniquely defined.

## Defining the Language of Propositional Calculus
1. Set of symbols ("characters"): `(`, `)`, `*`, `v`, `->`, `~`, `p`, `q`, ...
2. Set of expressions (finite sequences of symbols): `p v q`, `(((***`
3. Set of legal propositions ("words")

Now we will use our tool `I(A, P)` for defining what legal propositions are.
1. Let X := the set of all expressions
2. Let A := {p_{1}, p_{2}, ..., p_{n}, ...}
3. Let P := { `a, b / a * b`, `a, b / a v b`, `a, b / a -> b`, `a / ~a` }
4. Then "words" can be defined as `I(A, P)`

There is no "meaning" (semantics) attached to "words" at this point.
* `P_{1} * ~P_{1}` is only legal. We don't know what a contradiction is.
* We can't say `P_{1} v P_{2}` is equal to `P_{2} v P_{1}`. They look different and don't mean anything yet.

### Showing something is syntactically legal in some language
Example: is `(~((p v q) -> (~(p * q))))` legal?

A construction sequence for an expression \alpha, is a finite sequence \alpha_{1}, \alpha_{2}, ..., such that for all integer i, \alpha_{i} is either a member of the core set A, or it is the result of applying some f \in P to \alpha_{j}, ... \alpha_{k}, where j, k < i.

Mathematical proofs are also like this; come up with a sequence of arguments, such that each of them either is an axiom, or follows from previous arguments.

Claim: For every X, A, and P, and for an expression \alpha, \alpha \in I(A, P), iif there exists a construction sequence for \alpha. -> proof is an assignment for you.

### Showing something is NOT legal in a language
This is more difficult: is `p((->` a proposition or not? This is how we'll show: Come up with a property that is shared between all the members of the set, but not the expression in question. Matched brackets can be one of those properties.

How to show some property T is satisfied by all members of `I(A, P)`:
1. Show all members of `A` has property T.
2. Show if \alpha_{1}, \alpha_{2}, ... has property T, for all f in P, f(\alpha_{1}, ...) has property T.

