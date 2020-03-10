---
layout: post
title: 'GEB: Intro'
---

### Reader Background

One goal I have during my 3 weeks of funemployment is to read `Godel, Escher, Bach` (GEB).

I first tried to read this book in college, right after I took a `Computability` class on the very same topic of Godel's incompleteness theorem, but before I had really learned how to code. Even though I did well in the class, I found the book too dense and I didn't make it past Chapter 1 with the introduction of the MU-puzzle. In class, I would follow along with the textbook and the lessons in the most mechanical manner (just manipulations of symbols according to some rules). But even my understanding formal proofs was shaky -- I could hold the whole proof in my mind for maybe a few hours while I'm doing my homework, but after the homework is done, the memory of the proof is never recalled again and fades away quickly. Plus, I never fully understood the larger picture implications -- a house built on shaky foundation. I knew vaguely that Godel was trying to describe certain properties of complex formal systems, and his work shows that we're doomed to have 'incomplete' systems where certain truths are not derivable from the given axioms and rules. I knew that there was some connection to the Halting Problem, but I definitely can't elaborate about that connection.

So reading this book, and writing about it, is a way for me to re-learn what I sort of learned previously. Re-reading it a second time has been a much more enjoyable and easy experience compared to the first time. It's been a while since I've looked at or written any formal proofs, but I write code daily and as a result, am more than familiar with the type of 'formal reasoning' that is prevalent throughout the book.

But GEB is meant for for an audience unfamiliar with formal systems of math and logic. I think Hofstadter does a good job of helping the reader build an intuition around these abstract topics using more concrete examples in music and art, and through silly dialogues between fictional characters. Skimming these 'creative anecdotes' is fine if you already have a good sense of the point Hofstadter is trying to make, but I found these snippets pretty playful/funny, and you can learn a fair bit of Bach & Escher trivia in the process.

### Book Intro

The whole book is written to help you understand Godel's Incompleteness Theorem, how it was derived (the 'proof'), and the implications of this discovery.

So here is Godel's Incompleteness Theorem, paraphrased in English:

> All consistent axiomatic formulations of number theory include undecidable propositions.

This is the 'conclusion', a meta-claim about a property of all 'consistent, axiomatic formulations of number theory'. Put another way:

> There are true statements of number theory which its methods of proof are too weak to demonstrate.

What this means is that, 'no fixed system, no matter how complicated, could represent the [entire] complexity of whole numbers: 0, 1, 2, 3...' So Godel is pointing out an inherent shortcoming in all formal systems (that are consistent and axiomatizable). These systems are 'incomplete' because you can't derive all the true statements of the system from its axioms and rules.

How did Godel manage to do this? *Godel's discovery involves the translation of an ancient paradox in philosophy into mathematical terms. That paradox is the so-called Epimenides paradox, or liar paradox.*

A paraphrase of the ancient liar paradox:

> This statement is false.

If this statement is true, then it is false. If the statement is false, then it is true. This is unacceptable -- in formal systems, as is with common sense, we don't allow for something to be true and false at the same time.

Godel managed to translate the liar paradox into mathematical terms -- into a string that we shall call 'G'. String 'G' talks about itself:

> G is not a theorem of [some formal, consistent, and axiomatizable system].

Assuming that all theorems of the formal system are true ('consistency'), if G is a theorem, then it contains a truth about itself, namely, that it is NOT a theorem. But then we have a situation where G is a theorem and not a theorem at the same time. We could avoid this contradiction by concluding that G is not a theorem. However, we've then uncovered a true statement which is not a theorem of the formal system. Systems that produce all true statements (that can be expressed in the notation of the system) are called 'complete'. Systems that don't guarantee this are 'incomplete'. By concluding that G is indeed not a theorem, we know that G is true, but unprovable within the system.

Why is it important that Godel was able to translate the liar paradox into mathematical terms? To show that there are inherent limitations to what can be achieved with formal systems. Godel shows that you can use the system's own rules and axioms on itself, to demonstrate its own 'incompleteness'. Any system that is powerful enough to express the sentence G is incomplete. And as it turns out, most systems we're interested in, systems that are powerful enough to capture many true statements about numbers, are also powerful enough to generate the sentence G, thereby proving its own incompleteness.

von Neuman's take on what the Godel's Incompleteness Theorem means:
```
I think that [the Incompleteness Theorem] has solved negatively the foundational question: There is no rigorous justification for classical mathematics.
```

Why should you care? It's kind of a fun puzzle to understand how Godel managed to construct a meta-statement within a formal mathematical system -- a statement of number theory that is also about number theory. It's an interesting rumination on what it means to be self-reflexive (our thinking, after all, is infinitely reflexive: "I think X", "I am thinking about the statement, 'I think X'", etc.)
