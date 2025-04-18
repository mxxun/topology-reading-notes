# 51: Homotopy of Paths (rerun)

1. ok, once again, I forgot that they install a ==homotopy== between 2 general maps f,f' : X → Y
    1. by, well, F : X×I → Y with F x 0 = f x & F x 1 = f' x.

2. incidentally, when f ≃ (const _) we call f ==nulhomotopic==.

1. they use a symmetric symbol ≃ for homotopies. ^^let's justify^^ that it's an equivalence relation.
    1. refl: f ≃ f by F x _ = f x.
    2. sym: if F : f ≃ f' then we have f' ≃ f by F' x i = F x (~i).
    3. trans: if F : f ≃ f' and F' : f' ≃ f'' then we can have f ≃ f'' by F'' = F ⧺ F', or more explicitly:
        1. F'' x i
            | i ≤ 1/2 = F  x (2·i)
            | i = 1/2 = F  x 1 = F' x 0 = f' x
            | i ≥ 1/2 = F' x (2·i – 1)
        1. which is continuous, because it's a glue of F & F' which are defined on closed regions & agree on intersection.
            1. ---the pasting lemma, right.

2. and there's a stronger relation for specifically paths.
    1. paths are called path-homotopic when their homotopy keeps their endpoints constant.

3. oh good they also prove equivalence explicitly. let's follow them and extract their proof style.
    1. _this time_ our proofs are exactly identical to theirs!!!! what the fuck!!
    2. ok, to articulate.....
    3. our proofs last time were...more sketchy and more ~by-composition; cat-theoretical, maybe
    4. and this time (and in Munkres) we're giving homotopy maps' definitions explicitly. all right then.
4. oh right the extension to "_path_ homotopy is also an equivalence".
    1. .....they just state it like it's obvious.
    2. ok fair enough it's obvious enough I don't want to go into details, and writing down lack-of-details would be useless.

6. ok, Example 1. 
    1. any 2 maps X → ℝ² are homotopic.
    2. ...well _I'd_ prove it through "any map X → ℝ² is homotopic to (const 0)", but eh.
    3. ....& now Iunno what'd be my proof, because I glimpsed theirs.
    4. the idea is that you can do F x t = (1-t)·(f x) + t·(g x), and that's continuous. ==straight-line homotopy!== fun.
        1. (wait, but why is this continuous? ....because..... _+_, _·_ : ℝ²×ℝ² → ℝ² are continuous...and so we can.....
        2. for any given pair of maps Y → ℝ²....rectify the pair into the single (f;g) : Y → ℝ²×ℝ² 
        3. (by the universal property of products)
        4. and then postcompose that w/ _+_ or _·_ and get a continuous f + g : Y → ℝ². right.
        5. oh, and _+_ and _·_ are continuous because uhhhhhh they act componentwise on underlying products, and of course componentwise maps on underlying components of _any_ limit are proper arrows? yyyyyeah I think that's good enough.)
    
    5. if those were paths, then we have a path homotopy! so, any 2 paths between any 2 points in ℝ² are path-homotopic.
    6. also true for any Y = any convex subset of ℝ²! for the same reason!
7. another example: "upper semicircle" and "upper semicircle stretched 2× upwards" are ofc path-homotopic even in ℝ²–{0}, but "upper" and "lower" semicircles are not.

1. the known definition of path concatenation I don't care to repro again.
    1. except to gripe that it should have been called f ⧺ g.
2. Thesis! ⧺ respects path-homotopy, [f] ⧺ [g] = [f ⧺ g].
    1. or, more explicitly, for a given f' ≃ f, g' ≃ g we can construct a f' ⧺ g' ≃ f ⧺ g.
    2. (draws a picture)
    3. well of course? (F ⧺ G) x t = {glue F : I × [0; 1] → Y and G : I × [1; 2] → Y along the {1}, where they agree, being f 1 = g 0.}
    4. or, more explicitly, for f, f' : x ↝ y and g,g' : y ↝ z:
        1. (F ⧺ G) i t
            | i ≤ 1/2 = F (2·i)     t
            | i = 1/2 = F 1 t = y = G 0 t
            | i ≥ 1/2 = G (2·i – 1) t
        2. by construction, this is f ⧺ g up (t=0), x left (i=0), f' ⧺ g' down (t=1), z right (i=1).
        3. this can be verified further by expanding definitions & simplifying by assumptions, but I can't be assed.
3. Thesis! [⧺] forms a groupoid.
    1. assoc:
        1. uhhhhhhhhh.
        2. ok, so like. we can push ⧺ inside the equivalence-class brackets, right.
        3. so the goal quickly becomes [(p ⧺ q) ⧺ r] = [p ⧺ (q ⧺ r)], or simply (p ⧺ q) ⧺ r ≃ p ⧺ (q ⧺ r).
        4. ohhh right this is not refl-solvable; it requires a drawing of a trapeze or such.
        5. (draws a rectangle of these two)
        6. ok, what I'd do is.....define a closed-piece-wise-continuous explicit mapping of the square.
        7. %%()%%
    2. id, lid, rid:
        1. ----let's first at least state the thing w/o proving.
        2. id: ∀ x there's the eₓ : x ↝ x s.t. ∀ p,
            1. lid: [eₓ] ⧺ [p] = [p], or simply, eₓ ⧺ p ≃ p
            2. rid: p ⧺ e_y ≃ p
        3. %%()%%
    3. inverse, linv, rinv:
        1. inverse: ∀ p : x ↝ y there's a ~p : y ↝ x s.t.
            1. linv: p ⧺ ~p ≃ eₓ
            2. rinv: ~p ⧺ p ≃ e_y
        2. %%()%%
4. ok, let's look @ their proof (style) and practice in that.
    1. first thesis: for a path homotopy F : I×I → X : f ≃ f' and a map k: X→Y, F;k is _also_ a path homotopy, of f;k ≃ f';k!
        1. it's continuous: check. it's k (f 0) = k x & k (f 1) = k y on endpoints: check. it's f;k and f';k on boundaries: ofc it is.
    2. second thesis: given the same k : X→Y, (f ⧺ g);k = f;k ⧺ g;k.
        1. yeah kinda obvious. the proof is by unfolding ⧺ by definitions and checking that branches agree.
    
5. *ooooh* now I kind of remember what's their proof idea.
    1. the simplest place to demonstrate is indeed the id & lid/rid!
    2. to...not yet formulate comprehensibly, they do this:
        1. we want to prove that eₓ ⧺ p ≃ p. _actually,_ let's factor out _p_ to the right, because our proof is not about p, it's about homotopy of, mm, variously stretched interval maps I→I.
        2. so, of course p = id_I ; p. however, what's eₓ ⧺ p?
            1. well eₓ is const x, and p sends 0 to x, so eₓ = e₀ ; p.
        3. and we know that p respects ⧺, so eₓ ⧺ p = (e₀ ⧺ id_I) ; p.
    3. and so we reduced the goal eₓ ⧺ p ≃ p to the goal (e₀ ⧺ id_I) ; p = id_I ; p, or simply, e₀ ⧺ id_I ≃ id_I.
    4. now, the second trick: I is.............a convex subset of ℝ².....and therefore there's a straight-line homotopy in it.
    5. and that's it.
    6. yikes.
6. ok, to shorten this:
    1. the first trick is to recognize that the target paths are images of some paths in a convex subset of ℝⁿ.
    2. the second trick is that convex subsets have straight-line homotopy, and by postcomposition we get the target homotopy in the codomain.
7. Ok, but here's a crucial skill that is not demonstrated _even in the proof:_ *how* do we recognize that some symbolically-written path is an image of something really really simple?
    1. .....maybe rectangles are helpful here also?
    2. ...I mean I sure can write this operation down in terms of rectangles, but it's doesn't really help in noticing the factorization.
    
    3. ok, here's 1 part: _constants,_ including eₓ, preimage obviously, and of p = id;p.
    4. that suffices to factor lid's eₓ ⧺ p into e₀ ⧺ id_I and from there, yeah, ok, straight-line in the convex I.
        1. and rid also of course.
    5. let's look at the linv & rinv and see if that also suffices?
        1. ok, here we might want another microlemma: ~p =, uh, ~ ; p. I mean, this is actually true by definition; ~p i = p (1–i).
        2. but then, yeah, p ⧺ ~p = (id_I ⧺ inv_I) ; p, and of couse id_I ⧺ inv_I are a path 0 ↝ 1 ↝ 0 and we have the SLH to e₀.
        3. and likewise for ~p ⧺ p = (inv ⧺ id) ≃ e₁.
    6. ok, and what about assoc? assoc's the one that gives me intuitive trouble.
        1. mmmmmmmmrgh
        2. ok let's try to babble.
        3. I keep trying to reach "but can't we postcompose by some uniform mixture of p⧺q⧺r", and.....not directly!
        4. this postcompose thing worked for ids and invs because idₓ is factorable by p and ~p is also factorable by p.
        5. ok, but.......it's the same _curve_ in X, right.
        6. it _does_ make sense to take the image of one and preimage it by the other and get back a path in I.
        7. so if we just....figure out the right mapping of I such that one becomes the other...
        8. ok, so: (p⧺q)⧺r maps (1/4, 1/4, 1/2) and p⧺(q⧺r) maps (1/2, 1/4, 1/4). I claim that there's a map ⇝: I→I s.t. (p⧺q)⧺r ; ⇝ = p⧺(q⧺r).
        9. this map is just the piecewise-linear map that maps points (0, 1/4, 1/2, 1) to points (0, 1/2, 3/4, 1). Or explicitly:
            ⇝ i = case i of
                [0;   1/4] → 2·i     ([0;   1/2])
                [1/4; 1/2] → i+1/4   ([1/2; 3/4])
                [1/2; 1]   → i/2+1/2 ([3/4; 1])
    7. ...ok, let's check if that's what they do. I bet not for assoc?
        1. well....not _exactly_
        2. they define a triple product parametrized by the cut-points, factor it into the last part after the piecewise-linear mapping of the interval, and reduce the triple ⧺ to triple products w/ different params. ok.
        3. I mean, yeah, ours _could_ be generalized to this but indeed ours is also a magic-trick "here's the specific mapping" w/o the moral reason in terms of piecewise-linear mappings and cut-point-parametrized joins
    8. 

1. see also active-recall & exercises in [[2024-08-05]], [[2024-08-10]], [[2024-08-11]]
