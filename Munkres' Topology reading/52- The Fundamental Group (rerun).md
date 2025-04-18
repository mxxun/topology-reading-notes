# 52: The Fundamental Group (rerun)

1. .....wait, did I get it right that homotopy classes of maps have a group structure exactly the way fundamentals groups do?
    1. groupoid of paths has.....horizontal composition of _paths_ and vertical composition of _homotopies?_
    2. hm. of path homotopies. but arbitrary homotopies are....not in the path groupoid.
    3. ......let's meditate on this.
        1. homotopies are between p: x↝y & q: z↝w.
            1. they do form a..1-category w/ paths as objects & homotopies as arrows
            2. homotopies have....a natural symmetric arrow? not exactly an _inverse._
            3. but then if we ignore the variety of self-homotopies p≃p and factor them all out, we get...a 1-groupoid of paths and their homotopies?
            4. and if we ignore distinctions between homotopies at all, we get...the equivalence-class structure on paths.
            
            5. I wonder if inverse-homotopies are weak inverses, in the categorical sense?
                1. where there needs to be a 2-category & 2-isos in it that homotopize inverses to id.
                2. ok, then: in what sense F;~F : p ≃ p is connected to id_p? what's the relevant cell?
                3. ....we _could_ say that they're connected by a higher homotopy, but that way lie ∞-categories, I think, & I don't really want to go there.
                4. i.e. then _that_ will need to be an iso, and its inverse is _also_ weak, and there we go.....
                5. (nlab nlab)
                6. ......they ought to work coinductively though.
            6. so we _could_ go for the "maximally weak sense" and say that homotopies are weak-equivalences because they have weak inverses, i.e. that F;~F is connected to id by a cell that is itself a weak equivalence.
            7. but also fuck that, let's go back.
        2. homotopies are between p: x↝y & q: x↝y.
            1. so we have a meaningful 2-category, right? points, 1-arrows are paths, 2-arrows are homotopies.
            2. & then we cut off higher homotopies because we don't care, and only consider existence/nonexistence of 2-arrows.
            3. then, we still have vertical composition of homotopies & horizontal composition of paths (which respects/whiskers vertical)
            4. & indeed horizontals can and do have....weak units? because actually p;id ≃ p only up to 2-cell, not on the nose. hm.
                1. that's valid for sufficiently weak 2-categories, e.g. bicategories! a bicategory is equipped w/ associator 2-cells _and_ unitor 2-cells!
            5. ok so! weak units for horizontal arrows (paths), w/ unitor 2-cells equivating their compositions id;p ≃ p
            6. and weak inverses for horizontals also, w/ (invertor?) 2-cells equivating p;~p ≃ id
        3. .......we _could_ maybe say that fundamental groupoid is....enriched in booleans (w/ AND?) @ 2nd level? so... we don't have hom-sets of 2-arrows between 1-arrows; we have hom-truth-values of 2-arrows between 1-arrows.
        4. so that's a fun idea.

2. .....anyway. let's go do fundamental groups actually.
3. target: define fundamental group, show that it's a topological invariant.
4. reminder of groups:
    1. morphisms yes; kernel is f^-1({e})
    2. mono if...injective? = kernel is trivial?
        1. ok, mono-injective makes sense; & kernel....exactly characterizes non-injectivity because First Isomorphism Theorem, f: G → H factors into G ↠ G/ker f ⥲ Im f ↪ H
    3. cosets & normal subgroups yes ofc. quotients = kernels yes ofc.
5. fundamental group! here we go.
6. Example 1: ℝⁿ has a trivial fundamental group.
    1. I mean yeah? fundamental groups are [S¹, X]*, and for contractible X those are trivial.
    2. (...Q: are there non-contractible spaces w/ all homotopy groups trivial?)
        1. A: yes there are!! Warsaw circle!! i.e. topologist's sine closed w/ a circle arc connecting the free tail w/ the limiting boundary.
            1. I.....do not have an idea how to prove that homotopy groups of it are trivial, _nor_ that it is not contractible. that should be fixed.
        2. _and_ there's a theorem giving sufficient conditions for homotopy groups to determine the space uniquely (up to homotopy)! Whitehead's! says CW complexes are determined such.
7. Question: are π₁ point-dependent?
    1. hm, so: for a given path p: x₁↝x₂ we can define a....morphism of groups π₁(X,x₁) → π₁(X,x₂), right? let's do that.
        1. ...yeah, sure, let's do it covariantly. from x₂ go back along p, then loop at x₁, then go forward to x₂ again. loop ↦ ~p ⧺ loop ⧺ p.
    2. hypothesis: this is an isomorphism, because composed either way it's actually id.
        1. like so: send loop along p to ~p⧺loop⧺p, and then back along ~p to p⧺(~p⧺loop⧺p)⧺~p.
        2. now outer p-~p loops contract to trivial loops (by groupoid lemma) and we in fact got back the same homotopy class as the original.
    3. ...note: they define it directly on homotopy classes of loops _and_ of paths, so ̂p [l] = [~p]⧺[l]⧺[p], and even note that this map depends only on [p], not on p.
        1. .....& they...actually remember to show that it's a group homomorphism. uh.
        2. ~p ⧺ l₁⧺l₂ ⧺ p ≃ ~p⧺l₁⧺p ⧺ ~p⧺l₂⧺p, because we can contract the p ⧺ ~p in the middle to id? yeah.
    4. consequence: any path-connected space has the same fundamental group everywhere!
    5. ...._but_ they note that 

1. Definition: simply connected!
    1. X is simply connected if it is path-connected _and_ its fundamental group (everywhere) is trivial.
    2. so, contractibles are CW + πₙ = 0; if we drop CW, we get PC + πₙ = 0 that have non-contractible Warsaw circle; we can also drop πₙ = 0 to π₁ = 0 and get "simply connected" = PC + π₁ = 0.
    3. Thesis: not only all loops trivial, but also all parallel paths homotopic.
        1. well given 2 parallel p & q, p;~q ≃ id, & we can observe p ≃ p;~q;q ≃ q.
2. Hypothesis: FG is a topological invariant.
    1. i.e. that it's the same for 2 homeomorphic spaces.
    2. I think this derives readily from the thesis that FG is a functor as so:
        1. if FG is a functor, it maps morphism-compositions to morphism-compositions and ids to ids.
        2. so an isomorphism of spaces (f,g): X ≅ Y is mapped to an isomorphism of FGs, because π₁(f);π₁(g) = π₁(f;g) = π₁(id_X) = id_{π₁(X)}, and so f,g-induced morphisms of fundamental groups satisfy requirements of iso.
    
    3. so let's try to define the induced morphism of groups and observe that it's functorial.
    4. ....ok, what-all do we need for π to be a functor?
        1. [x] we already know how it maps objects.
        2. [x] we need to define how it maps arrows f:X→Y to arrows π(f): π(X) → π(Y).
        3. we need to show that it respects composition: π(f;g) = π(f);π(g).
        4. & also ids: π(id_X) = id_π(X).

    5. ok, first observation: f: X→Y can act coherently on underlying sets of π₁(X, x) & π₁(Y, f x), that being homotopy classes of pointed loops.
        1. obviously pointed loop l in (X,x) goes to a pointed loop l;f in (Y,f x) by postcomposition.
        2. then: a path homotopy p≃q in (X,x₁,x₂) goes to a path homotopy p;f≃q;f in (Y,f x₁,f x₂), as known.
        3. so, path homotopy of loops l₁≃l₂ becomes path homotopy of loops l₁;f ≃ l₂;f
        4. & so f does act coherently on homotopy classes of loops: [l];f = [l;f]. good.
    6. next: now we can lift f to the map π(f) of FGs π(X, x) → π(Y, f x).
        1. the action is known; π(f) [l] = [l;f] (: loop class in (Y, y))
        2. now to show that it's a morphism of groups. for that we'll need ([l₁⧺l₂]);f = [l₁;f] ⧺ [l₂;f].
        3. I think we had that already, for arbitrary paths? that, indeed, (p⧺q);f = p;f ⧺ q;f? ....yeah, fairly obviously.
        4. so....yeah, sure, morphism of groups; postcomposing an f to a join of loops is indeed a join of postcomposed loops.
    7. respects composition of arrows: π(f;g) = π(f);π(g).
        1. that's topological maps.
        2. well let's see. π(f;g) [l] = [l];(f;g). and π(f);π(g) [l] = ([l];f);g. checks out.
    8. respects ids: π(id_(X,x)) = id_π(X, x).
        1. ok, π(id_X) [l] = [l];id_X = [l]. that sure is the identity morphism of π(X,x).

1. Exercises!
    1. [x] we'll call A ⊂ ℝⁿ *star convex* if there's a point a₀ in A that's connected to the all A-points by line segments lying entirely in A.
        1. [x] find a star convex that's not convex.
            1. ...arch logo? i.e. any non-convex deltoid?
            2. oh they're call kites. concave kites, even! cool.
            3. ....ok, how about a more deranged example: a set of line segments from a₀ is star convex. in fact any star convex is a set of line segments from a₀.
            4. .....that last is technically correct but note that it's not necessarily bounded; "a ray from a₀" is a valid component of a star domain.
        2. [x] star convexes are simply connected.
            1. .....they're actually contractible? w/ a₀ as a trivial point of contraction? what are you _on?_
            2. oh btw wiki calls these star domains.
    2. [x] let p: x₀↝x₁ & q: x₁↝x₂ and r = p⧺q. then it is claimed that ̂r = ̂p;̂q.
        1. ok, uh, remind me the notation? that's the action "inject the fundamental group along the path", right. so, by definition, ̂p = \l → ~p;l;p.
        2. so then, ̂r l = ~(p;q);l;(p;q) = ~q;~p;l;p;q = ̂p;̂q.
        3. why is this so simple.
    3. [x] thesis: π₁(X, x₀) is abelian if and only if for any p,q : x₀↝x₁ we have ̂p = ̂q.
        1. ...._huh._
        2. well, ok, action of ~p reverses the action of p, so in particular we have that (p;~q) map π as id.
        3. ...oh! l;p is also a path x₀↝x₁! so then we have e.g.
            1. l₁ ↦ ~(l₂;p);l₁;l₂;p = ~p; ~l₂;l₁;l₂ ; p under (l₂;p)
            2. and ~l₁ ↦ ~p; ~l₁ ; p.
            3. so id = ~l₁;l₁ must go to ~p; ~l₁;~l₂;l₁;l₂ ; p.
        4. but ̂p is a bijection & in particular injection, so ~l₁;~l₂;l₁;l₂ = id, as desired.
            1. simplification: we can act on those loops by ~p, and get loops on x₀ back directly.
        5. [x] ....actually, let's try to explain this smh.
            1. the idea is that.....loops are valid paths by which to send a group to itself, and action of the loop is _conjugation automorphism._
            2. so....if the action of l₁;p is the same as action of p....then, actually, action of _l₁_ is the same as action of _id_ (by postcomp w/ ~p), & therefore all conjugations are trivial, which is to say, the group is abelian.
        
        6. ..that's ̂p = ̂q → abelian; now let's go the other way
        7. ok, p & q are bij, so let's find an l where they disagree and send l to q;~p ; l ; p;~q, which is gonna be distinct from l.
            1. ....not very intuitive?
            2. ....waaait. p;~q is a loop on x₀. so it commutes w/ l, and we can observe how l is sent to ~(p;~q); l ; (p;~q) = ~(p;~q); (p;~q); l = l.
            3. so q is an inverse for p, & so their actions agree.
        8. hmmmm. and how do we explain _that_ sensibly?
            1. there's....something here mirroring the loop-has-action idea from above; conversely, actions-have-loops, in the form of p;~q being a loop.
            2. that is to say: if all loops conjugate trivially, then so does the loop q;~p, which is the same thing as p being the inverse of q.
        9. ...ok, so maybe I have a 3-step "moral" explanation:
            1. loops act on their group as conjugations
            2. group is abelian = all conjugations are trivial
            3. ̂p = ̂q ≡ ̂p;~̂q = (p;~q)^ = id
            4. (p;~q) is a loop
            5. ....that misses the 1st half, a little...
            6. oh, here's the missing part: p;~q is a loop _and_ any loop is p;~q by taking p=l;q.
        10. ok, so, again, & finally:
            1. π is abelian iff all conj are trivial
            2. loops act by conj, so iff l* = id
            3. p;~q is a loop & any loop is p;~q, so iff (p;~q)* = id
            4. which is the same as q being an inverse of p, or p & q acting identically.
    4. [x] define r to be a *retraction* X → A ⊂ X if r is id on A. Thesis: r* : π₁(X,a₀) → π₁(A,a₀) is surjective.
        1. ........uhhhhhhhhhh..........
        2. any loop lying entirely in A......is also a loop in X....and is mapped to itself....?
        3. what the fuck, Munkres?
    5. [x] let A ⊂ ℝⁿ and h: (A, a₀) → (Y, y₀). if h is extendable to ℝⁿ→Y, then h* is the 0 morphism.
        1. I mean like. ℝⁿ is contractible, so [ℝⁿ, Y] is trivial & action of h* on any loop in ℝⁿ (i.e. the only one) is trivial.
        2. .....this is weird because....I don't readily understand how restriction of h to subspaces translates into restriction of h*.
        3. like....ok, restriction to subspaces respects specific loops but not their homotopy classes.
        4. still, h couldn't help but act identically on the whole class in ℝⁿ, which is to say, to act on all loops like on a trivial one, sending everything to [0].
        5. & after going to the subspace, the homotopy classes splintered but the action on individual loops did not, & they're all still mapped to 0.
        6. hm.
        7. this _is_ quite interesting! in particular shows how nontrivial embeddings of nontrivial spaces cannot factor through ℝⁿ.
    6. [x] Thesis: sending the group from (X,x₀) to (X,x₁) along p & then to (Y,y₁) along h is the same as sending first to (Y,y₀) by h & then to (Y,y₁) along (p;h).
        1. or: the diagram on these 4 fundamental groups commutes.
        2. it is.....rather obvious after we write out where l goes under all these maps by definition.
        3. the question is: is there some kind of a natural transformation here?
        4. well.....we could say that π is a functor, but then there's no...second functor here, just 4 cases of the same functor acting on 4 distinct(?) spaces.
        5. .....ehhhh.
    7. [ ] .....ok, let's try finish the 7th also.
        1. let (G, ·, x₀) be a topological group. (i.e. · and ⁻¹ are continuous.).
        2. let Ω(G,x₀) be loops at x₀. we can ⊗ loops by f ⊗ g i = f i · g i. .........this is continuous & so also a loop & ofc in Ω. horrible!
        3. [x] with that, Ω is a group.
            1. ok uh. associative by passing to G.
            2. identity by taking const x₀ & passing to G, f i · x₀ = f i.
            3. inverses by.....hm. ok, we want a "new" inverse loop f⁻¹ that will send i to (f i)⁻¹. we.....can do this by composing f & ⁻¹, which are both continuous. note that this is _not at all_ the inverse loop that happens after inverting I; (f i)⁻¹ might not be at f at all!
        4. [x] ⊗ induces _another_ group operation on π₁(G,x₀).
            1. i.e. it respects homotopy classes of loops. horrible!!!
            2. ...ok, nope, tomorrow.
            3. ...ok, it is now tomorrow; let's finish this.
            4. the usual phrasing is that [f ⊗ g] = [f] ⊗ [g], though it bears unpacking: it's that if f ≃ f' & g ≃ g' then f ⊗ g ≃ f' ⊗ g'.
            5. ......I mean uh. ⊗ is a peculiar postcomposition w/ ·, so...I bet homotopies also postcompose w/ it?
            6. ok, so let's define F ⊗ G x i = F x i · G x i. it's continuous. @i=0 it reduces to f x · g x = f ⊗ g, and likewise to f' ⊗ g' @i=1.
            7. so yeah.
        5. [x] from there, though, the final two ("⧺ = ⊗" and "⧺ is abelian") are almost easy; in principle we can say "by Eckmann-Hilton Argument" but wiki has a _beautiful_ elucidation so let's present it.
            1. The preconditions are: 2 operations, unital, satisfying the Square Association, in which (a ∘ b) · (c ∘ d) = (a · c) ∘ (b · d). (it's so much more vivid in the square form.)
            2. then we can show that a. units agree, b. operations commute & also agree, c. they associate too.
            3. the first is units: split 1₁ = 1₁ · 1₁ = (vertically split into a chess matrix) = (horizontally combine) 1₂ ∘ 1₂ = 1₂.
            4. the 2nd is equality & commutation: a · b = (matrix w/ 1s antidiagonally) = a ∘ b; a · b = (matrix w/ 1s diagonally) = b ∘ a.
            5. assoc: the matrix (a, b) (1, c) associates one way & the other.
        6. 


3. ok, outtakes:
    1. we forgot to re-show that moving the group along a path is a morphism of groups.
    2. that there're no canonical isos between connected points' groups, so omitting the point is not done
    3. ......I should maybe finally cache the thesis that π is a functor and stop rederiving it.