# 26 Compact Spaces

1. Meta: <=26.2 were before a chatt semi, 26.3–26.9 except 26.6 were on chatt semi

---

1. I could swear I did this before? But evidence points that not; that previously we stopped @ local connectedness & its exercises
    1. (I could also swear we did those, but, eh, maybe later, I'm hyped to rederive Alexandroff, so, later)
1. Ok, let's do a nonstandard first pass, with the goal of rederiving alexandroff:
    1. we'll only list theorems & try to rederive their statements from first halves, & try all proofs ourselves
    1. & then we'll try to use that for alexandroff

1. def: cover: +
1. def: compact space: +
1. 26.1: Lemma: a subspace is compact iff its covers all satisfy compact-condition of "has finite subcover"
    1. if they all do, then any its strict cover is a cover & satisfies the condition & so has finite subcover
    1. if it is compact, then all covers can be cut to it, we get a finite strict subcover, we extend it back & get finite subcover of the original, done
1. 26.2: closed subspace of compact space is compact
    1. if it isn't, there's its unfinitizable cover, & together w/ its complement it forms san unfinitizable subcover of the whole space
    1. conversely: pick any its cover; add the complement; pick finite subcover wrt whole space; remove the complement, done
1. 26.3: compact subspace of hausdorff is closed 
    1. so, hm, if we're in a subspace, & any its cover has finite subcover, & any 2 points are separated, then it's closed aka has all limit points
    1. let it not: then there's a limit point outside; let's separate it from some point in the subspace
    1. ---
    1. ok, repeating the proof from the textbook which I also heard on the semi
        1. (M: hearing it somehow felt much unpleasant? & like it was harder to understand?)
        1. (M: it _might_ be in fact nontrivial, w/ a lemma and shit)
    1. we'll show that a compact K is closed by showing its complement open
    1. which we will do by building a neighbourhood disjoint from K around every point outside of it and unioning those
        1. (this is the lemma 26.4)
    1. which we will do like this:
        1. for every point in the compact, build a hausdorff pair of open sets U and V around the chosen x outside K and y inside
        1. V_y form a cover of K; pick finite subcover and consider corresponding Us
        1. uniond Vs, intersect Us; due to finity U stays open, but now it cannot intersect the V, which covers the K, & so is disjoint from K, as desired

1. 26.4: given a compact subset of Haus & point outside of it, there're open sets that disjointly contain them
    1. (see above)
1. 26.5: image preserves compact
    1. comparatively trivial: take infinite cover of Y, take preimage, it's a cover of X; pick finite subcover, consider its progenitors again; they're a finite subcover of Y, done.
1. 26.6: if f : X -> Y is bijective (cont.), X compact & Y Haus, then f is homeo
    1. ok, so Y is by 26.5 also compact
    1. & I assume X is also Haus
        1. pick 2 points in X, send them to Y; unequal images because bijective
        1. pick Haus separating neighbourhoods, project them back
        1. disjoint and open in X, as desired
    1. ok, now we need image of open to be open
        1. or image of closed, closed, good enough
        1. closed are compact because X is; their images are compact by 26.5; they're closed in Haus Y by 26.3
        1. and done I think?
        1. apparently two points above were excessive, but w/e, honestly
1. 26.7: finite product preserves compact
    1. We figured this ourselves!!!!
    1. We had a hint in the name of tube lemma but still
    1. ok, 2 steps:
        1. fix y and cover C of X×Y. X×y is compact, there's a finite subcover U^y_i of it. project U^y_i into Y, take intersection, call it V_y; note that X×V_y is contained in \cup_i U^y_i.
            1. note that we can assume that U^y_i are basis elements, because we can take any cover, decompose it into basis elements, and take finite subcover still & get a finite _basis_ cover.
            1. this is the tube lemma.
        1. V_y form a cover of Y; pick a finite subcover V_j.
        1. now, only formalities remain: V_j cover Y; X×V_j cover X×Y; \cup_i U^{j}_i contain X×V_j; altogether U^{j}_i are finite, and a cover of X×Y. \qed.
1. 26.8: tube lemma: see above
1. def: finite intersection property
    1. C, a collection of subsets, has f.i.p. if any finite number of them have nonempty intersection
1. 26.9: X is compact iff any C w/ finite intersection property also has nonempty intersection
    1. this is really a restatement of definition of compactness, we just flip everything & "C is a cover" becomes "co-C has empty intersection" & "there's a finite subcover" becomes "there's a finite co-C w/ still empty intersection"

# Exercises

1. 
    1. a) two comparable topologies; which way compactness goes?
        1. in coarser there're strictly less covers, & any subcover stays a subcover; I say that compactness in finer implies compactness in coarser but not the other way
        1. another way to look at this: introducing new sets may introduce new covers, which may well not have the finite subcover property
    1. b) if X is compact Hausdorff under two topologies, they're either equal or incompatible
        1. ......let's `id` from finer to coarser
        1. this is continuous and bijective, source is compact and dest is Haus
        1. so by lemma 26.6 `id` is iso; done
1. 
    1. in finite complement of R, everything is compact
        1. in which open sets are R except a finset of points
        1. so uh suppose we have an X and its cover C
        1. a simple case in which X is contained in some C: boring
        1. can we have an X which is not covered by any finite collection of C?
        1. ....actually, like this:
        1. pick any C; it does not cover at most finitely many points of X
        1. for any of those points, pick a C_i that covers it; we're done!
    1. let's have a countable-complement of R; is [0,1] compact?
        1. it is not if we can have a cover w/o an infinite subcover, which seems doable
        1. let's make countably many holes in [0,1], e.g. {1/n}
        1. and then have a cover which has "increasingly fewer" holes in subsequents
        1. so, R–{1/n|n>=1}, R–{1/n|n>=2}, etc
        1. union of them all has all points, but all of them has holes
        1. so [0,1] is not compact
        1. neither is any infinite set, in fact
1. 3: finite union of compacts is compact
    1. binary is enough
    1. & we did that previously
    1. any cover of the union is a cover of either, so has finite subcover of either
    1. take 2 of those subcovers; their union is again finite & is a finite subcover of the original cover
    1. done
1. 4: compact in a metric space is bounded and closed
    1. ok, so in metrics, open balls are a basis
    1. metrics are all hausdorff because we can do small balls
    1. also, "bounded" means "fits inside a finite-size ball"
        1. or "diameter is finite"? w/e, same thing
    1. ok, so, Haus, so we get closed by the theorem
    1. now bounded
    1. suppose we have a compact unbounded subspace of a metric space
    1. if we cover it by epsilon-balls, then, hm
    1. any finite amount of epsilon-balls only cover a bounded set, because metric is total and then triangle
    1. so there
1. 4': metric space in which there's bounded closed noncompact subspace
    1. meh, later
1. 5: A and B are disjoint compacts of a Haus X; build disjoint open U and V covering them
    1. by lemma, every b in B has a neighbourhood disjoint from a cover of A | A itself
    1. if we take a union of those, we can get a cover (& a finite cover) of B disjoint from A
    1. likewise symmetrically, but then we have U and V disjoint from B and A, not from each other; they can intersect outside of A and B
    ---
    1. there's a thing where we can pick a point and a compact and produce a pair of disjoint opens; one around the point, another around the compact
        1. and in the process, we have produced _finite_ amount of pairs; Us jointly covering the compact and Vs all covering the point
    1. it _feels_ like we should be able to do a similar thing w/ whole closed sets
    1. let's try a stab:
        1. we do this for every point in compact K2.
        1. so, we have an infinite number of covers of K1, one for every point in K2, all disjoint from their respective points in K2.
        1. .....oh, I see.
        1. so we take a finite subcover of K2 by those open sets around its points.
        1. then we intersect the finite amount of covers of K1 disjoint from them.
        1. now that intersection is still an open cover of K1, but is disjoint from every set in that cover of K2.
        1. And, unioning those covering K2 jointly, we get our 2 open sets.
        1. Cool!
1. 6.
    1. if f : X -> Y is cont, X is compact and Y Haus, then f maps closeds to closeds (is a closed map)
1. 7. if Y is compact, pi_1 : X×Y -> X is closed
1. 8: 
    1. let f : X -> Y (not cont), Y compact Haus.
    1. let _graph of f_ be {(x, f x) | x : X} : X×Y
    1. then f is cont iff its graph is closed.
    1. (there's a hint.)
1. 