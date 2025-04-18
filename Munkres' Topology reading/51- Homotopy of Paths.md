# 51: Homotopy of Paths

1. Aight. once again, but now it's Munkres.

1. Paths in X are simplfy functions f : I → X.
1. we can, in general, have a homotopy between 2 maps from any X → Y! just,
    1. F : X × I → Y is a homotopy between f₀ f₁ : X → Y if F x 0 = f₀ x & F x 1 = f₁ x.
    1. obviously being homotopic is an equivalence relation:
        1. reflexive by F : X × I → Y via π₁ ; f
        1. symmetric by flipping I
        1. transitive by F;G : X × I → Y mapping x ≤ ½ as F and x ≥ ½ as G; that's cont. because they're cont on closed subsets & agrees on intersection.
            1. oh, right! it's called the pasting lemma.
    1. there're constant maps; those equivalent to them are called nulhomotopic.
1. now, given two paths p q : x ↝ y in X we can have a _path_ homotopy between them, requiring that:
    1. we have a normal homotopy F : I × I → X between them
    1. but also F 0 _ = x & F 1 _ = y
    1. so really F is a map from a square that's x on the left, p on top, y on the right, & q on the bottom.
1. that's also an equivalence!
    1. I mean, same proof works; the additional requirement that const & inverse & compose are constant on the left & on the right are all obviously satisfied
1. Example 1 (homotopies in general)
    1. if we have f g : X → ℝ² then...we can make a homotopy between them? by F x t = (1-t) ⋅ f x + t ⋅ g x?
    1. which is....continuous because.... t & (1-t) are cont and ⋅ and + are cont. oook.
    1. this has a designated name: straight-line homotopy. hm. ok.
    1. ofc if f & g are paths x ↝ y it's a path homotopy! x & y stay in place.
    1. this homotopy _almost_ sounds like bullshit, because it implies that all images of anything to ℝ² are equivalent? but like. it's ℝ². it's simple. not...that surprising that any image of X in it is homotopic to any other.
    1. same arguments apply to...any convex subset of ℝⁿ, really. ok.
    1. this...doesn't work if we map to R, does it? but no, it ought to? ⋅ and + are still cont if we're not doing them componentwise! aight.

1. Example 2: homotopies in the punctured plane
    1. ok, let's have paths: f x = cos π⋅x, sin π⋅x; g x = cos π⋅x, 2⋅sin π⋅x
    1. now to visualize that....mm. cos 0 = 1, cos π = –1, it goes to 0 & -1. ah, f is the upper semicircle, right. and g is something similar, but y-coord goes 0-2-0; it's a semicircle stretch upwards 2×.
    1. ok, yeah, straight-line between them will work, for sure
    1. now, if we define h x = cos π⋅x, –sin π⋅x, that's the bottom semicircle, & straight-line goes through the hole, so, doesn't work.
    1. .....oh, and indeed they're not path homotopic? ....sound like they ought not to be!

1. Aight, path-~~composition~~ concatenation (up to homotopy):
    1. given paths p : x ↝ y & q : y ↝ z, we can ~~compose~~ concat them into the path p ; q : x ↝ z in the obvious way
        1. i.e. by mapping the first half as p & the second as q and pasting-lemma them
    1. also, given a homotopy α : p ≃ p' and β : q ≃ q' we'll have α ;ʰ β : p ; q ≃ p' ; q' by, uh, 
        1. (paper paper)
        1. well we can map a square in 2 halves, the left half as α & the right as β and the middle as constant y
        1. by pasting lemma that's cont, and that's a path homotopy p;q ≃ p';q'
        1. cool.
1. ok so! claim: paths up to homotopy and concatenation form a groupoid.
    1. ...ok, lemme list out properties first because that's useful to remember.
        1. there're points/objects. there're arrows between them.
        1. there's composition of arrows, it's associative.
        1. there're identity arrows, they're left and right units.
        1. there're inverse arrows, they're left & right inverses.
    1. ok, so with that in mind, let's show paths to form a groupoid.
        1. points are points of X; arrows are paths.
        1. composition was just given. associativity!
            1. (paper paper)
            1. so....for a homotopy between (p;q);r and p;(q;r) we'll want a square in which p q r are ¼,¼,½ on top, but ½,¼,¼ at the bottom.
            1. so....we just want a continuous mapping that stretches I to send 0 to 0, ¼ to ½, ½ to ¾, 1 to 1. we can do this by.....piecewise linear stretching?
            1. like, there're 3 segments in the square; first is like F x y = p (y ⋅ (4⋅(1-x) + 2⋅x)) ? and similar for the other 2. (I'll be lazy & not do them explicitly again.)
            1. piecewise definition of F agrees on segments' intersections & pieces are cont by continuity of p (q,r) & + & ⋅, so by pasting lemma we have a full F. 
            1. ok cool.
        1. identity arrows are ofc constant maps p: x ↝ x, p _ = x. left and right identity laws!
            1. well same scheme, we have idₓ ; p on top & p at the bottom. we have just 2 segments: a triangle contracting idₓ to nothing and the trapeze stretching p. works the same way.
            1. for rid, same! the triangle's on the right but yeah.
        1. inverse arrows: well given an p : x ↝ y we can have p⁻¹ : y ↝ x via p⁻¹ t = p (1-t). now to show p ; p⁻¹ = idₓ, p⁻¹ ; p = id_y.
            1. why isn't there a unicode subscript y. UNICODE WHY. anyway.
            1. (paper paper)
            1. so there're 3 triangles; I _think_ the way we do it is we ....go less and less along the way of p, then stay constant at the midpoint, & then go back
            1. so the middle triangle is something like: F x t = p (max x (1-t)). is that....cont? I assume so? it _feels_ continuous.....
            1. and then the side triangles are F x t = id_{p (1-t)}, I'm guessing. no that doesn't sound like they'd agree on the boundary.
                1. no, wait.
                1. ....we could just do F x t = p x in the middle, and that'd agree w/ id_{p (1-t)} on the sides? we'd get a homotopy to id_y though, that's.....not what we needed.
            1. hmmm. if the middle triangle starts from x always, we can make the side triangles be const x. that sounds good.
            1. so instead....in the middle, let's start from x "later" and progress along p at the normal pace, and come back at the midpoint. how'd we encode that.
                1. F x t = p (2 ⋅ x – t) at left half & F x t = p⁻¹ (2 ⋅ x – t). at x ≥ t that proceeds at the normal (double) speed, and at x = ½ we have p (1 – t), going exactly from y to x, cool.
                1. and that's cont because ⋅ & – are! ok cool that ought to work.
        1. right-inverse is the same.
    1. ok, that's our proof of groupoid; let's see how it works in the book.
        1. thesis 1: composing a path homotopy in X w/ a cont f : X → Y we get a path homotopy in Y.
            1. constant on the left and right: sure
            1. continuous: sure, by composition
            1. path on top and at the bottom: sure, p ; f and q ; f are paths f x ↝ f y in Y.
        1. thesis 2: composition w/ a cont f : X → Y agrees w/ path concatenation: (p ⧺ q) ; f = (p ; f) ⧺ (q ; f)
            1.  I mean that's.....obvious.....by definition of _⧺_. right.
        1. oh hm! they define some simple paths in I, and homotopize them in I² because I² is convex (so, straight-line path homotopy works?), and then use the fact that (e₀ ⧺ i) ; f = (e₀ ; f) ⧺ (i ; f) = eₓ ⧺ f, and so....the obvious homotopy i ≃ e₀ ⧺ i extends into f ≃ eₓ ⧺ f by that extension. hmmmmmmmmmm.
            1. %%after rerun: no! they homotopize in I! I² is just a suggestive picture.%%
        2. so the proof technique here is something like.....let's not fuck around w/ paths or homotopies in a complicated space X; let's figure a projection from something simple like I into X that'll get us desired paths, and then homotopize arguments of the projection in the simple space.
        3. this sounds like a bit of a bullshit, in that it's...not very obvious how to find such a projection? but maybe this will go away if we practice this approach.
        4. so, for inverses, they do the same thing, but with i ⧺ i⁻¹ ≃ e₀.
        
        5. and for associativity.......I _think_ they're doing a similar thing, fundamentally homotopizing I into I piecewise-linearly, and then applying p-q-r to that? sigh. can't claim I understand this to the point of being reproduce. need practice at this proof tech. ok.
2. Last lemma of the chapter: we can split a path into any finite number of segments, and of course this doesn't change the homotopy class of it.
    1. I mean ofc, by induction, through the core 3-segments assoc.

3. Exercises!
    1. let's have homotopic....maps p p' : X → Y, and also homotopic q q' : Y → Z.
        1. claim: p ; q & p' ; q' : X → Z are also homotopic.
        2. o...k, so: being homotopic means that there's an α : X×I → Y that's α x 0 = p x, α x 1 = p', and also β : Y×I → Z for q & q'.
        3. so we want an α;β : X×I → Z that's gonna be like p;q at 0 and p';q' at 1.
        4. (paper paper)
        5. what if we....α;β x t := β (α x t) t
        6. then at 0 it's β (α x 0) 0 = β (p x) 0 = q (p x), and likewise at 1.
        7. huh.
    2. so we can have X → Y, cont maps from X to Y. we can also have.....[X, Y]; those same maps but up to homotopy.
        1. (btw, _who in their right mind_ uses a symmetrical notation for directional things! augh!)
        2. a: [X, I] is trivial; all maps X → I are homotopic.
            1. ...the argument here is the same as for convex subsets of ℝⁿ? I is a convex subset of ℝⁿ! you can straight-line homotopize from any map to any other! right? seems so.
        3. b: if Y is path connected, then [I, Y] is also trivial
            1. ooh! that's nice!
            2. so by definition, when Y is path connected, for any 2 points y y' there's a path p : y ↝ y'.
            3. so....I think if we have paths p : x ↝ y & q : z ↝ w, we should be able to homotopize p into q by like...pulling it along p, free y ↝ z, and q?
            4. so let's pick a ! : y ↝ z. then there're obvious paths p;! : x ↝ z and !;q : y ↝ w. now let's define α x t = ....
            5. (paper paper)
            6. ok, so let's imagine a rectangle that's p on top, p;! on the left, !;q on the right, q on the bottom
            7. then cut in 2 triangles & a parallelogram
            8. then do suitable linear-ish funcs on the 3 and glue them by pasting lemma & that works for a homotopy p ≃ q. hm. ok I guess.
        4. b2: rosie suggests to go through constant paths! ok, let's do this also.
            1. ---also, motivation: this way we...chip away at the problem, cutting away distinct paths we need to consider; first all to constant, then constant to ~~nothing~~ unit
            2. so then. first, we can homotopize any path to a constant one via (draws a square w/ p-p-e_y-e_y sides) that
            3. .....thaaat actually works regardless of path-connectedness, hm. wait, does it?
                1. yeah; does not contradict non-homotopy of upper and lower semicircles because they're not *path*-homotopic; they're ordinary-homotopic all right.
            4. now, if we're path-connected, and we want to homotopize eₓ to e_y, we can..α x t = p t for p : x ↝ y and that's it.
            5. hum.
    3. contractibility! a space is contractible if its identity map is nulhomotopic, i.e. homotopic to..any constant map. ok.
        1. a: I and ℝ are contractible.
            1. as above, any path is homotopic to a constant path! id : I → I is a path!
            2. ℝ: how about we define α x t = x ⋅ (1 - t). that's id on top and 0 on the bottom and it's cont as usual.
        2. b: a contractible space is path-connected
            1. hmmmm. given an α : id ≃ eₓ, we can.... α y : I → X, α y : y ↝ x. now that gives us a path to a fixed x, but then we go to x & then back to z, and there's our path y ↝ z.
        3. c: if Y is contractible, then any X has [X, Y] trivial; all maps are homotopic.
            1. ok, is-contr Y means that the identity map is homotopic to a constant map. in particular, implies that Y is path-connected.
            2. I _think_ this implies that any map of X is homomorphic to a constant map by composition w/ id & its homotopy to const? because....well f : X → Y is homotopic to itself, and id_Y is homotopic to e_y, so f = f ; id_Y ≃ f;e_y = e_y : X → Y.
            3. and we already know that in a path-connected space any 2 constant maps are homotopic; see ending of b2 above. voila.
        4. d: if X is contr and Y is path-connected, then [X, Y] is again trivial.
            1. I think we'll homotopize f : X → Y to a const, and then those are all homotopic in path-connected Y, as above
            2. and for the first I think we had a theorem? id_X ≃ eₓ because X is contr; `_;f`-ing this homotopy will get us f ≃ e_{f x}, as desired.
            3. yeah, it's a fact above, that for F : p ↝ q, F;f : p;f ↝ q;f.
4. (Endpoint)