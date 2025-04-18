# Chewing on NMU's Panov's Topology 2 (algebraic)

## Meta
1. ooook, let's for now just keep logs here and later on maybe structure something better.
1. --tho reviews are good! let's do reviews.

1. primary source: https://old.mccme.ru/ium/postscript/f24/panov-topology2_09-09.pdf.
    1. there's also http://higeom.math.msu.su/people/taras/teaching/panov-topology1.pdf for e.g. CW complexes

## history
1. 2025-01-04: 2.1, some exercises, reviewed it even

## progress
1. 2.1: [[Panov-s Topology 2- 2.1 (singular homotopy definition - first properties)]]
    1. properly learned exact defs of simplicial and CW complexes!
2. 2.2: functoriaity & homotopy invariance
    1. we successfully rederived most of the proofs; on paper though
3. 2.3: long exact sequence, i.e. the zigzag lemma
    1. likewise we successfully rederived. I'm not yet satisfied w/ the zigzag lemma but it'll hold.
4. 2.4: [[Panov-s Topology 2- 2.4- relatives and long exact sequence of pair]]
    1. .....ok, this I mostly skimmed in hatcher, time to try to figure it out.
    2. .....try to generate ourselves, but still.
    3. .....well we finished but I might want to review what...exactly was there.
5. 2.5. [[Panov-s Topology 2- 2.5- excision and consequences]]
    1. [x] one statement of excision
        1. there's a natural injection (X–Z, A–Z) ↪ (X,A); if cl Z ⊂ int A, then it induces iso of relative homologies!
    2. [x] equivalent often more convenient
        1. for subspaces A,B there's likewise a natural injection (B, A∩B) → (X, A); if int B ∪ int A = X then it likewise induces iso of relative homologies.
    3. [ ] equivalence of these statements
        1. ....let's try to figure it out first, how about.
        2. there's a hint that we can take B and A to be something. e.g. let's say that B = X–Z and A = A.
            1. I think we'll need to prove that cl Z ⊂ int A ⟹ int X–Z ∪ int A = X, and then indeed the second statement entails the first.
        3. ...and conversely, we could set Z = X–B and A = A and....
            1. & then if we have int B ∪ int A = X ⟹ cl X–B ⊂ int A then the first entails the second.
            2. ....well quite obviously X – int B is closed and is contained in int A, and i'm pretty sure that given X–B ⊂ X – int B, cl X–B ⊂ cl X–int B also holds.
    4. [x] consequences
        1. [x] statements (homologies of X∪CA; for a cofibrative injection, CA-factor is an equiv and gives H X A ≅ H~ X/A)
        2. [x] proofs (mostly)
    5. [ ] at some point would be good to figure how cofibrations cause homotopy equiv of the cone
        1. Top 1, Proposition 4.9
    6. [ ] need to meditate on how excision-theorems are...generated
    7. [ ] review the suspension via CX,X
    8. [ ] chew through the wedge sum
    9. [ ] invariance of domain? about ℝⁿ ≠ ℝᵐ.
6. [ ] 2.6: proof of excision
    1. ehhhhhh?
7. [ ] 2.7: mayer-vietoris
    1. [ ] statement
    2. [ ] chase the detail of proof we don't see immediately, the C A+B = C X part following from something about excision
    3. [ ] comprehend use-cases?
8. [ ] there're some fun exercises!
    1. [ ] naturality of the pair sequence
    2. [ ] homology groups of complements of linked & unlinked circles in ℝ³
        1. unlinked: first let's put them parallel. then mentally encase them in a torus each. then deform-retract thus:
            1. half-space to one side of the torus into it
            2. inside of the torus into it
            3. the insides of the hole of the torus into a disk
            4. the space-slice between the tori into a ribbon connecting the disks.
        2. this sure looks like a wedge sum of 2 horn toruses, which either of them have H₁ and H₂ ≅ ℤ, so we'll have the total reduced groups: 0, ℤ², ℤ², 0 etc.
        3. for linked, I...think....we can deform-retracked into 2 linked torii? in which the hole of either is filled with the other.
            1. or, equivalently, 2 torii w/ filled holes, except they go through each other's fillings.
    3. [ ] of complements of coordinate axes in ℝ³ and in ℂ³
        1. ---ok, in ℝ³ kinda obvious. that's homotopy equivalent to a sphere w/ 6 holes, aka plane w/ 5 holes, aka wedge of 5 circles. so, ℤ⁵.
1. 3: cellular homologies.
    1. I.....don't.....care?
    2. maybe worth skimming for interesting things?
2. 4: homotopy groups and homologies!
    1. ohhhhh. it casts many powerful theorems about higher homotopy groups as consequences of "given sufficient connectedness, there's excision, and therefore suspension and relative→factor isomorphisms"