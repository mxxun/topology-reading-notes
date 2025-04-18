# 54: The Fundamental Group of the Circle

1. a *lifting* of...any map f: X → B, really, is a map ̅f : X → E that –;p converts to f.
    1. so in particular paths might lift to paths, and homotopies.. _might_ also lift to homotopies, but that's less obvious.
2. Examples: lifts of paths in S¹ to ℝ.
3. Lemma: path lifting property!
    1. let p:E→B be a covering, p(e₀) = b₀, and f:I→B start at b₀. then there's a *unique* lifting of f to a path starting at e₀!
    2. let's take a stab.
        1. sooooo for every point b in the image of f take its evenly covered neigh.
        2. these constitute a cover of the image, &, image of I being compact, we can take a finite subcover.
        3. now, take an element of the finite cover that contains b₀ & call it U₀. exactly 1 of its slices V₀ᵢ will contain e₀; call that slice V₀. take the U₀ ∩ f & pick its preimage in V₀ as definition of ̅f...?
        4. .....actually, some shit might happen if f fucks around, going out of U₀ and then back again. so we wan't get a semiinterval, we'll get a bunch of intervals as well. or maybe worse.
    3. well our old idea was to use, er, a sequence of "nails"? such that every bᵢ..bᵢ₊₁ has an evenly lifted neigh covering it.
    4. or maybe I'm forgetting how exactly I formulated it & my formulation might be wrong. that's what they use, anyway.
    5. more precisely, they acquire a segmentation of _I_ such that f([sᵢ, sᵢ₊₁]) is covered by an evenly covered set.
    6. but they do this.........by fiat!!!!! what the fuck!!!!
    7. well.....actually, by "Lebesgue number lemma", which I Do Not remember, because it was used in "Compact Subsets of Real Line", which, yeah, fuck that.
    8. but the lemma basically says that given any open cover 𝓒 of a compact metric space, we can pick a size δ>0 of such that _any_ open set of diameter <δ is contained entirely in some C ∈ 𝓒.
    9. & we sure have a cover of Im(f) by evenly covered sets, so we can preimage that cover back to I, and lo, we can cut I into finitely small pieces sᵢ..sᵢ₊₁, image of each entirely contained in an evenly covered set. fun.
    10. but then, yeah, we take the image of sᵢ..sᵢ₊₁, we find the unique slice Vᵢⱼ that contains the previous nailed point, & we send sᵢ..sᵢ₊₁ to the isomorphic preimage of f(sᵢ..sᵢ₊₁) in that Vᵢⱼ under p⁻¹. the 0th nailed point is b₀ (to e₀), the next nailed point is Vᵢⱼ ∩ p⁻¹ (f sᵢ₊₁).
4. ....&&outtake:&& it's crucial to work in _I_ when cutting it, not in its image, because I is fairly well-behaved and the image isn't really.
5. Lemma: homotopy lifting!
    1. let F: I×I→B, F 0 0 = b₀. then F uniquely lifts to ̅F: I×I→E, ̅F 0 0 = e₀. moreover, if F was a path homotopy, then so is ̅F.
    2. ok uh. I×I is also compact. so we can take a pointwise even covers of Im(F), project them back, & get segments of I×I that are covered by evenly-covered Uᵢ.
    3. then.....basically in the same way we can lift F uniquely?
    4. and if F was a homotopy then its boundaries inevitably lift to preimage of b₀ & b₁, &, those preimages being discrete, it actually lifts to constant maps const e₀ and const e₁ for some e₁?
    5. ---they actually extend 2 full boundaries first, by directly applying path lifting, but I don't think I care
6. Theorem: path-homotopic paths lift to the same endpoint & are path-homotopic after!
    1. OBVIOUSLY!!!! just lift their homotopy and there you are.
7. Definition: for a given cover p and lifted basepoint e₀, let's map loop classes to their lifted endpoint. call this mapping ɸ.
8. Theorem: if E is path connected, ɸ is surj; if it is simply connected (loops trivial), it is also bijective.
    1. surjective, i.e. every lift of basepoint is represented by some loop.
        1. I mean like. path-connect e₀ to eᵢ, project it back, bam, a loop class.
    2. if loops in E are trivial, it is _also_ injective, i.e. 2 loop classes can't map to the same point.
        1. I mean uh. if loops are trivial, parallel paths are also all homotopic, so any 2 loops lifting to the same endpoint are homotopic in E, & that projects back to B.
    3. and......there we go.
    4. HUH.
9. Thesis: π₁(S¹) = ℤ.
    1. ℝ is a covering space of S¹ that's both PC and SC. therefore, loops in S¹ are given by p⁻¹(b₀), which is to say, by integers.
    2. then you can observe that the (1) loop generates all the other loops, and there you go.

10. a mild strengthening of the theorem about ɸ:
    1. let p:E→B be a cover and p(e₀) = b₀.
    2. [x] p*: π₁(E,e₀) → π₁(B,b₀) is a mono.
        1. obviously because homotopies in B lift to homotopies in E.
    3. [x] let H = p* π₁(E, e₀). there's an injective map Φ: π₁(B,b₀)/H → p⁻¹(b₀), bijective if E is PC.
        1. so uhhhhh we do not take a factorgroup because H is not normal; we just take cosets, but still map them to preimages of b₀.
        2. well like. a loop in B preimages to a path in E. if you prepend a loop in E, the endpoint doesn't change, so we can indeed map whole cosets.
        3. if E is PC then surj just like before: path in E to loop in B to coset /H.
        4. unconditionally injective...
        5. ah: let 2 loops lift to p,q: e₀ ↝ e₁. p;~q is a loop in E, so these 2 loops are in the same coset, done.
    4. [x] if f is a loop in B, then [f] ∈ H iff f lifts to a loop in E.
        1. .....ob...viously...?
        2. if f lifts to a loop then it is...an image of the loop & is in H by definition.
        3. if f is in H then it's an image of a loop, &, lifts being unique, lifts to that loop.
        4. like iunno what to do here.


1. Exercises!
    1. [ ] what's wrong w/ path-lifting if we "cover" the circle w/ ℝ₊?
    2. [x] why so careful about the order of rectangles?
        1. because....we need every next rectangle to glue coherently to all the others? and this might not be guaranteed if we let the gluing boundary be not simply connected?
        2. ..let's look more carefully into this though.
        3. ah! the important part is connectedness, so the previously-defined piece lies in a single V₀.
        4. & the problem would happen not @ the point where we have a hole surrounded by boundary — that's fine, the boundary is connected & the hole will lift!
        5. but rather @ the point where we have 2 disconnected pieces of a boundary: 2 parallel edges, or an edge & a vertex.
        6. though note that we can do this in _w/e_ order such that:
            1. new rectangle is at least 1-point-connected to previous
            2. new rectangle's gluing boundary is connected.
        7. so e.g. we can do diagonal, & then disconnected diagonal trees, and then fill in between! why not!
    3. [x] lifting and ⧺ commute.
        1. ......obviously? if you ̃p ⧺ ̃q, that projects down to p ⧺ q? & so is a unique lifting?
    4. [x] regarding the spiral cover of ℝ²–0: let's lift some paths.
        1. [x] path f t = (2-t, 0)
            1. that's a line from (2,0) to (1,0).
            2. it lifts into....a bounded spiral?
            3. ......that's 100% wrong. liftings are disjoint.
            4. it lifts into a series of lines from (2,0) to (1,0), on all the layers of the spiral covering.
        2. [x] path g t = ((1+t) cos 2πt, (1+t) sin 2πt)
            1. starts from (1,0), rotates full circle, ends at (2,0). spiraly.
            2. it...well, it goes to the next layer, doesn't it.
        3. [x] path h = f;g.
            1. oh it's a loop in B!
            2. & it lifts to "line within 1 layer, spiral around to get to the next layer".
            3. &, yeah, ℝ²–0 sure is homotopic to S¹ & has the same fundamental group.
    5. [x] How does a (1,2)-loop on a torus look like?
        1. [x] (draws a rectangle) yeah like that
        2. [x] ....ok, lifting that to _ℝ×ℝ_ is an exercise in something.
        3. ........wait. we just need to. not loop around. ha.
    6. [x] so there're maps S¹→S¹, zⁿ and z⁻ⁿ. they induce homos π(S¹, b₀) into itself. what do those look like?
        1. A: ....well like. a morphism of ℤ is determined by its action on 1. & these guys send 1 to n. so.
    7. [x] generalize the S¹ theorem to work on T.
        1. well......ℝ² is a simply connected cover of T, so the mapping π(T,b) → p⁻¹(b) is a bijection. basepoint has a single preimage in every square, so, there we go, ℤ² points.
        2. but wait: do they compose like ℤ²?
        3. well like. if we compose two loops l⧺r and then lift them, we will first get a curve b₀↝l₀, and then l₀↝l₀+r₀. because lifting the 2nd loop starting at l₀ will get to the endpoint r₀ shifted by the exact same offset.
        4. so, ⧺ maps to (+) on pairs of integers. done.
    8. [ ] 