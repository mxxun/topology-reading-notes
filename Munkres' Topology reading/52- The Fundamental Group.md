# 52: The Fundamental Group

1. so! we have a path groupoid of the space, but we don't have a specific group.
1. we can, however, pick a point x₀ and restrict the groupoid to loops at this basepoint. that gives us a fundamental group π₁(X, x₀).

1. ---oh btw review of groups.
    1. morphisms ofc; kernels ofc; mono is..inj & epi is surj & iso is bij, yeah..
    1. left cosets gH form a partition, sure; normal subgroups with gN = Ng yep
    1. quotient by normal where we consider G up to N yep. and that's an epi w/ kernel N yeah.
    1. and conversely any epi can be represented as a factor by its kernel yeah that's fun.
    1. G/H for _right_ cosets? ok....
    1. aight.
1. `there're πₙ(X, x₀) but we shall not study them in this book` well Munkres might not have pages for it, but my napkins are vast and multitudinuous; I suggest we do take a moment here and there to meditate on higher homotopy groups.
    1. (e.g.: does method X generalize to them? can they be computed easily? does definition generalize? etc.)
1. Example: ℝⁿ have π₁ trivial at any point.
    1. because straight-line homotopy contracts them to the constant loop! so, up to homotopy there's only the constant loop.
    1. ..generally, same works for any convex subset, obviously.
1. Q: does basepoint matter?
    1. A1: I _think_ it shouldn't if basepoints are connected?
    1. (by text) so there's an obvious map converting loops @ x₀ to loops @ x₁ given a p : x₀ ↝ x₁, i.e. p⁻¹ ; _ ; p.
    1. Hypothesis: this map is a group isomorphism.
        1. ....I mean. applying it along p⁻¹ will give us p ; p⁻¹ ; l ; p ; p⁻¹ ≃ l, so it's obviously bijective. now to show it's a group morphism.
            1. ---this technically proved invertability in one direction.
            1. the other direction is same though.
        1. given loops f g @ x₀, concat of their maps is p⁻¹ ; f ; p ; p⁻¹ ; g ; p ≃ p⁻¹ ; f ; g ; p, i.e. map of their concat, as desired.
        1. well there we go?
1. ok so! fundamental groups of X do not vary within path components!
    1. in particular, if X is path-connected, it has a single fundamental group.
    1. `it is usual to deal with only path-connected spaces when studying the fundamental group` yeah makes sense.
1. ....note that different paths may induce different isomorphisms between fundamental groups at points, and so....it's normally important to track the basepoint.
    1. (and paths we go through when moving it, presumably.)
    1. `isomorphism between π₁ at different points is independent of path iff π₁ is abelian` what the fuck!!! why!! ok, fine, exercise.
1. Def: X is simply connected when it's path-connected and its π is trivial.
    1. ..in which case basepoints _really_ do not matter to groups, because ! : 0 ≅ 0 is unique.
1. Lemma: for a simply connected space, any 2 paths with same endpoints are path homotopic.
    1. so ofc p ; q⁻¹ ≃ eₓ ≃ q ; p⁻¹, but if we cut that in half we do not get a path homotopy; the midpoint moves.
    1. (paper paper) hm. how about a homotopy p ≃ q that...takes the square of homotopy p;q⁻¹ ≃ eₓ, and...takes line segments from it as function of t, fixing the end at y (midpoint of top) and rotating the beginning through left, bottom, and right?
    1. might need to paste it from 3 pieces, but that's fine
    1. the first piece would be something like α x t = x ⋅ β 0 t + (1-x) ⋅ β ½ 0, though ofc I don't mean ⋅ & + normally, I mean "mix arguments to β with this weighting". and others similarly.
    
    1. they do...something much simpler?
    1. they go: p;q⁻¹; q ≃ p obviously, but also ≃ eₓ;q ≃ q because p;q⁻¹ is nulhomotopic. huh.
    1. that.....feels like a BS algebraic trick? but maybe not that BS; "try to collapse an expression both ways you need" is like. standard practice, and also has...specific techniques to find a well-collapsing expression? mmmm.

1. Hypothesis: π₁(X, x₀) is a topological invariant.
    1. ...indeed, it's probably reasonable to go about proving it via lifting cont maps to π₁ morphisms?
    1. Thesis: given a cont f : X → Y there's a natural morphism f* : π₁(X, x₀) → π₁(Y, f x₀).
    1. we'll define it as....p : I → X ↦ p;f : I → Y. it is known that F : p ≃ q ==> F;f : p;f ≃ q;f, so this is well-defined.
    1. now that it's a morphism: that (p ⧺ q) ; f = (p ; f) ⧺ (q ; f) is a lemma of previous chapter.
    1. ofc if f is an iso then p ; f ; f⁻¹ = p exactly, and likewise q ; f⁻¹ ; f = q. so, as an invertible morphism, f* is then an iso.
    
    1. functoriality of π₁!! that is, that Π₁ & –* form a functor Top → Grpd.
        1. they talk about pointed groups and pointed induced maps; that's ok, though I'm sure sam arguments work for the full form.
        1. or like, we could say that π₁ & –* form a functor Top* → Grp.
    1. ok, so. functorial properties are: functors respect composition of arrows, and they respect identity arrows.
    1. in our case, this caches out into:
        1. (f;g)* = f* ; g*
            1. this is obvious from definition of –*! it maps p ↦ p;f;g, and ofc composition is associative in Top.
            1. ..and, well, the fact that elementwise agreement of group morphisms makes them equal.
        1. (id_X)* = id_{π₁(X, _)}.
            1. well again, p ↦ p ; id_X = p, so.
1. Exercises!
    1. A ⊂ ℝⁿ is star-convex is it has a point from which the whole A is visible.
        1. a: a star conves set that's not convex is like. take a triangle and cut into its sides convexely. or do a star graph.
        1. b: if A is star convex, A is simply connected.
            1. well it's obviously...contractible? by straight-line homotopy to the constant path at a₀. and I think contractible spaces are simply connected.
            1. so, if X is contractible, id_X ≃ eₓ. so we can take a loop p : I → X, precompose it to that homotopy, and get p ≃ eₓ, as...desired.
    2. say we have p : x ↝ y & q : y ↝ z. claim: (p ; q)⁻¹ = q⁻¹ ; p⁻¹.
        1. I mean uh. by...definition of –⁻¹ and _;_? p⁻¹ t = p (1-t); p;q t = p(2t) `glue` q(2t-1).
        1. (p ; q)⁻¹ t = p;q (1-t) = p (2-2t) `glue` q (1-2t).
        1. (q⁻¹ ; p⁻¹) t = q⁻¹ (2t) `glue` p⁻¹ (2t-1) = q (1-2t) `glue` p (2t-2). `glue` is unordered, so.
        1. ......wait, did we prove entirely the wrong thing. let's see. ......yeah; they use \hat to denote mapping of cont maps to their induced group morphisms. fiiiine.
        1. ok, another claim: p* ; q* = (p ; q)*.
        1. ok, by definition, p* l = p⁻¹ ; l ; p. obviously (p ; q)* = (p;q)⁻¹ ; l ; (p;q) = q⁻¹ ; p⁻¹ ; l ; p ; q = q* (p* l) = (p* ; q*) l.
    3. let's have X path-connected w/ 2 points x & y. π₁(X, x) is abelian iff for any p q : x ↝ y, p* = q*.
        1. we...can recall the fact that π₁(X,y) ≅ π₁(X,x) by path-connection.
        1. I.....have some suspicion that if we have a non-commuting element in π, we can nontrivially, what's the word, _conjugate_ the group by x⁻¹⋅_⋅x, and that begets a distinction between induced morphisms of...p and, uh, x⁻¹;p;p* x?
        1. ...sounds suspicious; if we unfold p* x, isn't that simply p⁻¹ ; x ; p, and therefore this above is x⁻¹ ; p ; p⁻¹ ; x ; p = p. ok, that doesn't work.
        1. ...ok, how about we map π₁ _to itself_ by a p that does not commute w/ q? then that maps q ↦ p⁻¹ ; q ; p ≠ q, and eₓ* decidedly maps y ↦ y, so that's 2 different maps p* ≠ eₓ*. so, if any 2 maps agree, then π₁'s abelian.
        
        1. now, if π₁ is abelian, we want any 2 paths to give identical maps p* = q*.
        1. when paths are loops, that's true because p⁻¹ ; _ ; p = p⁻¹ ; p ; _ = _ because abelian.
            1. (..moreover, it's obviously the identity iso of π₁.)
        1. now....of course q = p ; p⁻¹ ; q, and q* = p* ; (p⁻¹ ; q)* because functor.
        1. but the second morphism is from a loop, and therefore identity by above. so, q* = p* as desired.
        1. Huh!!
        
        1. ok, uh, what's the moral of this proof.
            1. for loops, q* is conjugation-by-q
            1. i.e., for loops, –* sends π₁ to Aut π₁ as usual for conjugations
            1. but non-abelian element produces a nontrivial conj, so if all conjs agree, all elements are abelian. ok.
            1. conversely, abelian groups have all conjugations trivial.
            1. and also, for any p q : x ↝ y we can represent one as the other plus a loop.
            1. so, if all loops' conjugations are trivial because abelian, ofc p* = q*.
        1. hm.
    4. say we have a retraction of X onto A, i.e. a cont. r : X → A that acts identically on A. Claim: for a ∈ A, r* : π₁(X, a) → π₁(A, a) is surj.
        1. I mean like.....any loop within A is mapped identically by r? & for any element in π₁(A, a) there's an identical element in π₁(X, a) that gets mapped into it?
        1. What am I missing!
        1. I mean sure sure their elements are classes not loops, and technically they're distinct classes because there're more homotopic loops in X, but c'mon! mapping ought to work on representatives and it sure does work on representatives!
        1. .....I have a deja vu about this exercise.
    5. let A ⊂ ℝⁿ and have a cont h : (A, a) → (Y, y). now, _if_ there's an extension of h to g : ℝⁿ → A, then h* is trivial (i.e. maps any loop class to the unit, the constant loop class).
        1. 
    6. 
    7. 