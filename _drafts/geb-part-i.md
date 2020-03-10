---
layout: post
title: 'GEB: Part I'
---

### Propositional Calculus

### TNT

### Godel Numbering

===========
Notes
Consistency: The property of a system, where "everything produced by the system is true."
Completeness: "Every true statement (that can be expressed in the notation of the system) is produced by the system."

"What if G is the only sentence of this form?" G is a reflexive sentence. Why do we worry about non-reflexive sentences?

What's still not clear to me, and maybe will become clearer as I read more of the book, is why the discover of ONE reflexive troublesome sentence is enough to make us worried about our system? It's true that there is no longer the guarantee that this system contains all true theorems, because Godel has found one counterexample, but what if it's the case that our system is powerful enough to capture all true theorems except these annoying reflexive ones? I suppose there's no way to formally state that. Any attempt to do so will be similar to Russells' Principia Mathematica project, an attempt to ban all relfexive statements, to derive alll of mathematics from logic, without bringing in contradictions!

From SEP, Godel writes about his discovery: If there were no undecidable propositions, all (and only) true propositions would be provable within the system. But then we would have a contradiction. Gödel then noticed that such paradoxes would not necessarily arise if truth were replaced by provability. But this means that arithmetic truth and arithmetic provability are not co-extensive — whence the First Incompleteness Theorem.

This is super helpful, from SEP:

One of the main technical tools used in the proof is Gödel numbering, a mechanism which assigns natural numbers to terms and formulas of our formal theory P.
There are different ways of doing this.
The most common is based on the unique representation of natural numbers as products of powers of primes.
Each symbol s of number theory is assigned a positive natural number #(s) in a fixed but arbitrary way, e.g.

```
#(0) = 1	#(=) = 5	#(¬) = 9
#(1) = 2	#( ( ) = 6	#(∀) = 10
#(+) = 3	#( ) ) = 7	#(vi) = 11 + i
#(×) = 4	#(∧) = 8
```
The natural number corresponding to a sequence w = < w0,…, wk > of symbols is

⌈w⌉ = 2#(w0) · 3#(w1) · … · pk#(wk),
where pk is the k+1st prime. It is called its Gödel number and denoted by ⌈w⌉. In this way we can assign Gödel numbers to formulas, sequences of formulas (once a method for distinguishing when one formula ends and another begins has been adopted), and most notably, proofs.

An essential point here is that when a formula is construed as a natural number, then the numeral corresponding to that natural number can occur as the argument of a formula, thus enabling the syntax to “refer” to itself, so to speak (i.e., when a numeral is substituted into a formula the Gödel number of which the numeral represents). This will eventually allow Gödel to formalize the Liar paradox (with “provability” in place of “truth”) by substituting into the formula which says, ‘the formula, whose code is x, is unprovable,’ its own natural number code (or more precisely the corresponding numeral).
