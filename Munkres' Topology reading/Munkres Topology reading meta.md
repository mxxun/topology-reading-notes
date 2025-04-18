# Munkres' Topology reading meta

1. [The book](<../../../../_resources/Topology (Munkres).pdf>)

## Plan 2 (2021)
1. I observe being bored about compact spaces and fiddly details
    1. ...ok, maybe now that I know Alexandroff, I can have fun reframing everything through my view?
    1. also, hausdorff compactifications are somewhat interesting
1. But maybe it's time to skip to algebraic topology or something

## Plan (2019??)
1. Atm I want to do:
2. ~~1.2 (topspaces and continuity)~~, 
3. 1.3 (connectedness and compactness)
    1. in particular, 26–29 (compactness); ~~maybe~~ relevant exercises
4. 1.5.38 (Stone-Cech)
    1. probably good to at least skim 37 (tychonoff) because stone-cech relies on it?

5. fragments of 2 (algebraic topology)
6. 2.9 fundamental group to understand basics of algebraic topology
7. maybe more 2.
    1. 2.11 (Seifert-van Kampen) looks like an answer to a question we asked quite some time before (how to compute homotopy groups of glued spaces)
    2. 2.12 classification of surfaces we wanted to understand 
    3. 2.14 apllications to group theory might be interesting but on reflection I'm not entirely sure & it needs 2.13 prereq

# Things we have not done
## And are up next
1. take another look at 55–57
2. review 58–60
3. Continue from there

## And could come back for
1. Continuous functions: Exercises 7, 9, 13;
2. Metric topology: metrize R^\omega, check/redo 4 (cubes are slightly wrong conception), 5, 6b, 7, 8b+
3. .....maybe revisit Metric topology II for another attempt
4. Quotient topology
    1. Ex. 6
5. Topological groups?
---
1. (23) Connected spaces: Ex. 12
2. (25) components and local connectedness: Example 3 onwards
3. Continue from: (26) Compact spaces: Exercise 4', 5+
4. (27): from after Extreme value theorem

## And likely won't
1. Set theory:
    1. LUB exists iff GLB exists, $\R$ has LUB, skim Maximum principle; 
    2. maybe re-skim latter couple sections regarding Choice and Zorn and etc, these might actually be interesting in a less underslept state.
2. Hausdorff spaces:
    1. Ex 21 (Kuratowski): proof that distinct Cl Int Cl Int is impossible

# Logs of Plan (2019)
## [[1.1. Runthrough of set theory]] (Ch. 1)
1. Order theory parts were in fact fresh
    1. Dictionary order in particular
    2. other nonstandard orders also
    3. connection between orders and Choice also

## 1.2. Spaces and continuity
### [[1.2.1 — 1.2.2_ Spaces, Bases]]
1. Bases are fresh!
2. Practice dealing w/ them and wrangling the definition of topology is good.

### [[1.2.3_ Order topology]]

### [1.2.4 — 1.2.5: Product topology; Subspace topology]

### [[1.2.6_ Closed sets and limits]]
1. Closed sets
2. Interior and closure
3. Limits
4. Hausdroff
    1. are T_1 and limits enough for Haus? no
5. (Boundary)
2. [[1.2.6 exercises]]
    1. Kuratowski

### [[1.2.7_ Continuous functions]]
1. on basis
2. equivalents: closeds, closure before is inside closure after, any neighbourhood has a covering preimage neighbourhood
3. homeos, embeddings
4. continuity on a collection of sources -> continuity on their union
5. pasting of 2 functions agreeing on the intersection
6. products being products

### [[1.2.8_ Product topology]]
1. Box vs product; actually not new

### [[1.2.9_ Metric topology]]
1. [[Metric topology I rerun]]
1. [[Metric topology I exercises]]

### [[1.2.10_ Metric topology II]]

### [[1.2.11_ Quotient topology]]
1. [[1.2.11- Quotient topology (2023 rerun)]]

## Connectedness and compactness

### [[23_ connected spaces]]
1. [[connected-spaces-rerun]]

### [[24_ connected subspaces of the real line]]
1. [[connected-subspaces-of-the-real-line-rerun]]

### [[25-components-and-local-connectedness]]

### [[26-compact-spaces]]

## Variety:
1. [[Verbitskiy-compactness-problems-1]]

## [[27-compact-subspaces-of-real-line]]

# AlgTop, aka: Logs of Plan 2 (2021)
## Motivation!
1. so, we can show isomorphism by demonstration, but non-isomorphism is harder in principle.
2. we can do that by observing some topological invariant to be different.
    1. [0, 1] is compact and (0, 1) is not; ℝ is 2-countable and The Long Line isn't; ℝ has a [cut point](https://en.wikipedia.org/wiki/Cut_point) and ℝ² doesn't.
3. on the other hand, we don't have simple invariants that'd distinguish ℝ² and ℝ³, or S², T, or T # T.
4. so: new invariants! a space will be called _simply connected_ if any loop in it can be continuously shurnk to a point. then ℝ²-sans-point is not simply connected, but ℝ³-sans-point is; S² is, and T isn't, but T # T also isn't.
5. _but_ we can go further! we can _quantify_ not-simple-connectedness by defining the fundamental group (of loops up to homotopy). then T has ℤ², but T # T has, uh, an anabelian one.
    1. %%is it by any chance the free product ℤ² ⊔ ℤ². I just fucking bet it is.%%
    2. yeah! [wiki](https://en.wikipedia.org/wiki/Free_product) says that van Kampen says that π of wedge product (i.e. #) is a free product of πs, given some conditions.
    3. ....I _think_ it actually says that π(U₁ ∪ U₂) is a pushout on π(U₁ ∩ U₂) → π(U₁,₂), and ofc if the first is trivial pushout is the free product. Cool!!!
6. also: _this is used to prove fundamental theorem of algebra???_ Fuck Yes
7. prereqs:
    1. quotient topology (yeah freshly reviewed)
    2. local connectedness (eesh, ok)
    3. ...honestly wherever *#* is defined. ....ah, it's probably defined below. ok fine.

## [[51- Homotopy of Paths]]
1. [[51- Homotopy of Paths (rerun)]]

3. [x] ~~TODO: practice their style of proofs actually; we're here to learn, not just to persevere in what we can already do~~
4. [x] TODO: rerun exercises
    1. see [[2024-08-05]] about additional meditations
    2. plus [[2024-08-10]] for continuation & [[2024-08-11]] for conclusion


## [[52- The Fundamental Group]]
1. [[52- The Fundamental Group (rerun)]]
    1. interesting finding: homotopy groups determine homotopy type of CW complexes, but not of arbitrary topspaces! 
        1. Whitehead's theorem for complexes & Warsaw circle as a counterexample.
        2. ^^Q: how does one prove homotopy groups & non-contractibility for Warsaw circle?^^
2. ~~TODO:~~
    1. ~~review~~
    2. meditate some more on naturality in Ex. 6
    3. ~~finish Ex. 7~~
    4. finish the outtakes

## 53: Covering spaces
1. [[53- Covering Spaces]]
2. TODO:
    1. exercise 6
    2. review (later)
3. outtakes:

## 54: The Fundamental Group of the Circle
1. [[54- The Fundamental Group of the Circle]]
2. TODO:
    1. exercise 8
    2. review
        1. in particular memorize ɸ & Φ better
    3. meditate on how to _motivate_ covering spaces
    4. meditate on fundamental groups of various spaces
        1. Mobius is homotopic to S¹.
        2. _sphere_ I'm confused about! can we do a covering space smh?
            1. [[Meditations on covering space of S²]]
            2. (%%they instead do it via a slice of Siefert-van Kampen.%%)
## 55–57
1. 55 seems to be basically a prereq to 56 & 57? & _at the moment_ I kind of don't care for them? so let's skip ahead to more fun things where we get to fuck w/ more homotopies?
    1. ---or maybe play w/ some pieces of 55 & finish it properly later.

2. 55: Retractions and Fixed Points
    1. concept of a retract(?) ~within the space (X→A that's const on A)
        1. in particular a homotopy retraction X→A makes the group morphism i*:π₁(A)→π₁(X) injective
        2. .....others I'm still meh on.
    2. 
3. 56: The Fundamental Theorem of Algebra
    1. ----rederived separately, w/e.
4. 57: The Borsuk-Ulam Theorem

## [[58- Deformation retracts - homotopy type]]
1. TODO:
    1. review
    2. go through exercises, mark completeness, do the rest

## [[59- the fundamental group of Sⁿ]]
1. TODO:
    1. review
    2. exercises: 4th?

## [[60- Fundamental groups of Some Surfaces]]
1. TODO
    2. meditate on their proof of commute, the "kernel vanishes" argument seems good to understand
    3. review
    4. exercises
