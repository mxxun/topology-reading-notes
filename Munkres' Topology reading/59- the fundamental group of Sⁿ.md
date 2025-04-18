# 59: the fundamental group of Sⁿ

## slice of Seifert-van Kampen:
1. given open U & V, X = U ∪ V & path-connected U∩V, images of π(U) & π(V) generate π(U ∪ V).
    1. easy: take a loop, cut into segments wholly in U & V, insert paths to and from the basepoint @ each segment boundary, & you have a decomposition of any loop in U ∪ V into a word in the alphabet of loops of U & V.
2. corollary!! if U & V have a trivial fundamental group (SC), they generate 0 ⊔ 0 = 0 the trivial fundamental group (SC) of U ∪ V.
3. consequence: Spheres are simply connected!
    1. a punctured n-sphere is obviously ≅ ℝⁿ.
    2. so take 2 poles & cover an n-sphere w/ two puncturings. these are open & ≅ℝⁿ & so SC, their intersection is PC because it's ≅ ℝⁿ – *, so the whole sphere is also SC.
4. .....that's it, that's the chapter!!
## exercises!
1. [x] compute the group of S² ∨ S²!
    1. I mean like. simply connected, right.
    2. because we can take open subsets slightly bigger than spheres, which are basically "sphere + a tiny piece of sphere glued to the pole", & which are fairly obviously homotopy equivalent to a sphere proper.
    3. & then the intersect is PC & we have our SC by that shard of Seifert-van Kampen.
2. [x] Q: and when is the wedge sum of 2 SC not SC?
    1. well the construction above needs to not work.
    2. maybe the small subset around the basepoint cannot contain a contractible subspace of the other space?
    3. ......well yeah sure that does happen if we wedge 2, uh, S²-earrings, but those are not....SC....??
        1. ------apparently yes they are???
        2. but in any case computing the group of 2 wedged earrings by that van Kampen slice does not _reduce_ the problem, so, yeah, ok.
    4. .....do they just mean that "a point in common" is not enough, you need "the intersection is PC"? so, wedges are fine but 2-point-wedge of 2 Is is a circle?
        1. they refer to Spanier, algebraic topology, p. 59.
        2. (half an hour of wrangling a djvu reader later)
        3. .......OK!!
        4. the construction is indeed about the earring: consider a cone over an earring, at (0,0,1). now reflect this set against the origin, getting an earring in negative half-plane & a cone at (0,0,-1). these 2 cones are simply connected, intersect only at (0,0,0), but their union is said to be not simply connected.
        5. .........because you can't simultaneously contract the loop on 2 sides to the point, because one sides contracts to 1 point & the other to another. I think.
        6. wild topology calls it the *Griffiths twin cone.* cool.
        7. it shows some more!
        8. any single loop through the twin earrings is contractible in the cone; therefore any finite concat of loops is trivial
        9. a loop _only on the left_ or only on the right is also contractible in its cone.
        10. if we take infinite alternations of left and right loops, however, that doesn't look trivial! because you can't simultaneously contract infinitely many of the loops, because their contraction paths alternate in the 2 disjoint subsets.
3. ....wait, am I missing something about that van Kampen part?
    1. ---ahhh right the 2 unioned parts need to be open.
    2. and if the wedge point has no contractible neighbourhoods then yeah.
4. [x] criticise the proof that S² is SC because any loop is straight-path homotopic to a point.
    1. there're space-covering paths, fuckheads! you can't pick a point not lying in the image of f! that's the whole problem!
5. [x] ℝ /≅ ℝⁿ
    1. because removing a point disconnects one but not other?
    2. because _adding_ a point gives Sⁿ, and S¹ has a nontrivial group but S² & up are SC?
6. [x] ℝ² /≅ ℝⁿ also!
    1. because removing a point gives a space homotopy equivalent to Sⁿ⁻¹, and for n=2 S¹ has nontrivial group but etc etc.
7. [ ] 