# Rotman's Algebraic Topology reading meta

## Meta
1. grew out of [[Algebraic Topology reading meta]]'s consideration that Hatcher is Not Fun Actually
2. _atm_ I'm 

## Plans
1. well I want Theorem 11.31 about lower homotopy groups. 
    1. & also I want to understand Hatcher's cellular approximation but I do not want to read Hatcher about it.
    2. so let's read Rotman's Simplicial Approximation, including the key theorem 7.5 that drives the conclusion.
## Logs
### Simplicial complexes
#### Definitions
1. 
    1. laments that homology theory & raw definition of the fundamental group do not suffice to e.g. compute π₁(T)
    2. but notices that triangulable spaces are comparatively easy to work with! so we'll do that.
    3. vertex set, proper face obv.
    4. simplicial complex: intersect on faces, yeah
        1. ---they talk about it being finite though, that's something.
        2. ----non-obvious technical details: underneath, they are honest convex hulls of points in ℝⁿ.
        3. and they're using *union inside ℝⁿ* + intersection condition instead of a tree of compatible injections, so that's....fun.
    5. underlying space: ofc
    6. polyhedron / triangulation: hee. yeah ok.
    7. examples!
        1. the torus example is interesting in that triangulations do not always survive a factoring: we can triangulate the square I² directly but after the factor its triangles have the same set of vertices and we...can't? make a simplicial complex just on them.
        2. .....that a 18-triangle cut of a torus _works_ is....a little surprising....but yeah! I remember this construction in our meditations on homologies; S¹ is _definitely_ triangulable with 3 segments, & we do this twice & then cut the squares into triangles and there we go.
2. exercises:
    1. the RP² as defined by the square w/ identified sides is homeo to the disk w/ identified points.
        1. ....stretch the disk outwards into the square and then it's the exact same identifiaction.
    2. a compact connected subset of ℝ² that's not a polyhedron.
        1. ....a bounded spiral? mmmm no that's just a I, regardless of its winding.
        2. topologist's sine or a warsaw circle? both are connected (circle even path), both should be closed & bounded, but uh. they have no 2d parts, so a 1d complex is required. but....the sine curve cannot be covered by finitely many Is.
        3. ...I am not satisfied with this intuition that's not a proof.
        4. — can be lifted into a proof I think? smth like.....any map of I → there can only cover finitely many sine waves, because otherwise....you take an open cover by "small region around peak, rest", and preimage of around peak gives countably many disjoint pieces in I, and that violates compactness.
    3. btw another I think workable example: a spiral that countably winds around a _circle_ instead of a point. a fun thing actually!
        1. example: clothoid = Euler spiral = Cornu spiral.
        2. compact: yeah; connected: circle is path & so is the spiral. but any open containing the circle intersects the spiral, so.
        3. .....I can't find its algtop characterization anywhere. is it....hard...?
    4. Q: why isn't 2×2 triangulation of the I² not a triangulation of T?
        1. uh you get simplices w/ the same set of vertices again. which is _fine_ if we had the machinery for it but yeah.
        2. honestly I think Hatcher's right that the machinery is worth it to cut down on simplices; this is horrible.
2. 
    1. open simplex: either the point or subtract the boundary.
    2. complex is a disjoint union of opens! fun!
    3. star of the vertex p: opens of all simplices touching p
    4. hm.
3. Ex:
    1. closedness via every intersection closed: boring, come back later maybe
    2. every point in unique: ...obviously?
        1. ....well ok explicitly. from complex to simplex: if x is in multiple simplices then it's in the intersection which is a face & so a simplex.
        2. then if x is in interior it's there & otherwise it's on the boundary and on a face and recurse.
    3. let x lie in the unique open simplex s°. x is in stars of exactly vertices of s.
        1. that it is in stars of s is obvious.
        2. any other star will not union s° because any other p would not touch s, not being its vertex.
    4. stars of K-vertices are open in K and form an open cover.
        1. well uh
        2. open cover easy: any point lies in an s° and any s° is in the star of some vertex.
        3. open in K: uhhhhh well we probably make it contain a small neigh of any point in it.
        4. I _think_ any s'° the small neigh intersects has s° as a face? and so is itself in a star.
    5. a star contains line segments from its core.
        1. ----I mean, any s° is an interior of a simplex? and a line from a point to the simplex vertex is inside the simplex? so yea.
    6. pₙ have a simplex on them iff their stars all intersect somewhere.
        1. well if there's a simplex they do intersect on its °. ----no, on all simplices containing theirs as a face.
        2. and if there's not they....don't? to belong to a star of p is to have p as a vertex, to belong to all is to have them all....
4. Dimension: ok yeah
5. Theorem: homeomorphic complexes have the same dimension
    1. uh.
    2. nnnnot sure how to prove it w/o invoking homology groups or the like.
    3. ok, uh, what they do is:
    4. assume there's a difference m > k. pick an m-simplex, its interior is open in K, map to L. intersect w/ some interior in L, get an open W in L. 
        1. now embed the p-simplex containing W in an abstract m-simplex's interior: if done directly, its image will contain _no_ empty sets as subsets, but by sending W back to K and then there the image of W must be open. a contradiction.
#### Simplicial Approximation!
1. category of simplicial maps 𝓚!
    1. we simply...send vertices to vertices, requiring that all simplices between them persist.
2. Theorem: it's a category, and "take the underlying" is a functor 𝓚 → Top.
    1. id: stay in place; composition: compose set-maps & composition respects persistence. assoc inherited, lid & rid inherited.
    2. functor: well map of vertices extends to a piecewise linear map of their convex hulls. action of individual simplices agrees on their instersection, lower simplices, by recursion. ah yes |id| = id.
    3. ----ah shit functors must respect composition. ....ughhhhh.
    4. ...I _think_ it suffices that composition of affine maps agrees w/ the affine map of 2 vertex-mappings on any given simplex? because they assemble into the whole map uniquely.
    5. & then uhhhhhh functor sure respects action on vertices, and action on a point is a weighted action on vertices and yeah ok fine.
    6. eugh.
3. Q: can we functor Top back to 𝓚?
    1. absolutely not. subcategory of polyhedra either, because continuous maps are a shit.
    2. what if we consider maps up to homotopy? _still_ no because Hom_𝓚 is always finite and π₁(S¹) is not.
    3. we......can construct approximating sequences with subdivision. I think.
4. Definition: if K & L are SiCom. ϕ simplicial and f continuous, ϕ is a simplicial approximation of f if:
    1. at every vertex p, f(★p) ⊂ ★(ϕ p)

### first taste after discovering
1. rotman, reading shallowly ch.11 (homotopy groups): already like it more smh!
2. notably more categories; I think it sold me on Eilenberg-Steenrod axioms (by saying the homotopy groups satisfy them except excision)
3. cogroups & some kind of appealing categorical treatment of loops and suspensions
4. ...homotopy groups via cogroup structure on Sⁿ!
5. its Theorem 11.31, about πᵢ(Sⁿ), goes through chapter 7 (simplicial approximation), and I think does motivate it
6. and in the same breath, nontriviality of πₙ(Sⁿ) they prove via "homotopy equivalent maps induce the same maps on homology groups, and `const _` and `id` induce distinct endomorphisms on Hₙ(Sⁿ), so there you go, 2 nonequivalent elements of πₙ(Sⁿ)"
    1. --and I bet you get the whole ℤ by saying "the n-winding map induces the ·n map on Hₙ(Sⁿ), & so they're all not homotopy equivalent"
7. ..fibrations and fibration exact sequence...
8. ...Hopf fibrations and correspondencies for homotopy groups! huh!
9. buuuuut it only teases with statements of Hurewicz, Whitehead, and Freudental (& Blakers-Massey) and Eilenberg-MacLane and Postnikov :<
10. 