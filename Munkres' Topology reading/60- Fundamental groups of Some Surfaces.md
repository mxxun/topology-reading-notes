# 60: Fundamental groups of Some Surfaces

## Theorem: fundamental group commutes w/ products!
1. (paper paper paper paper)
2. ---I've been thinking on this a bunch, & first proved a partial result (that product of groups embeds into the group of products, because ofc it goes back & that's a factoring of product through itself & so an iso & the first is of course an inj)
3. but then there was a revelation: any loop in X×Y _is in fact_ homotopic to its left projection ⧺ its right projection!
    1. like so: "any loop" is actually a path (f t, g t) through X×Y, projections acquirable by projections.
    2. now consider a square I×I and its image in X×Y by α i j = (f i, g j).
    3. ofc the loop itself is the image of the diagonal, and p⧺q is an image of one path along the boundary, & ofc the preimages are homotopic in the square by straight-line and so images are homotopic. and there we go.
4. so the reverse composition, (f t, g t) ↦ (f t, x₀) ⧺ (x₀, g t) is also an id, and we got our isomorphism. cool.

5. obvious corollary: π₁(T¹) = ℤ×ℤ.

## Action: let's define the projective plane & compute its fundamental group!!!
1. ok, definition is simple: we quotient S² by antipodes.
2. ........does that mean that. S² is a covering space of P². a simply connected one.
3. and therefore the fundamental group has 2 elements, like basepoint has 2 preimages.
4. so it's ℤ/2.
5. WHAT THE FUCK.
6. .....it is also compact, because we can preimage the cover, pick a finite subcover in the sphere, and yeah.
7. ------to be clear they're careful to show explicitly that small neigh of S² indeed embeds isomorphically into the quotient, but, eh, w/e, obvious.
8.  ......extension: ℙⁿ is a quotient of Sⁿ, doubly covered, so all projective spaces have as a fundamental group ℤ/2. 

9.  Exercises: what if we factor the circle?
10. .....well that's again a circle, and the covering map corresponds to the 2-winding loop.
11. Lemma: π₁(S¹∨S¹) is not abelian!
12. so like. abāb̄ is not trivial.
13. ....I can do...._a_ covering space that.....looks like a double spiral.
    1. .....the problem is that after lifting exactly nothing changes about the loop abāb̄.
14. .......ok, HOW ABOUT. WE DIRECTLY MODEL THE COVERING SPACE ON THE FREE PRODUCT.
15. yyyyeah. yeah, now any loop that does not retrace its steps ends in a distinct copy of the intersection, labeled exactly by the word of the loop.
16. the space is........contractible.......by, approximately, straight-line homotopy. therefore it is in particular SC, so preimages of basepoint give us the fundamental group.
17. & by construction composition of paths works like concatenation of words in the free product, so the fundamental group is free product.
18. and I think we're done.

19. TERRIFYING!!!
20. THAT'S TOO MUCH POWER!!
21. THIS GENERALIZES TRIVIALLY TO N-BOUQUETS!!!
22. & I BET FINITE 1-DIMENSIONAL COMPLEXES ARE ALL HOMOTOPIC TO N-BOUQUETS!!
23. WHAT!!!