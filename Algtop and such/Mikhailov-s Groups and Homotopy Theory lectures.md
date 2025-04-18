# Mikhailov's Groups and Homotopy Theory lectures

## meta
1. well we've looked at them from afar _a number of times,_ didn't we.
    1. so let's take notes, perhaps, why not?
2. as of 2025-02 they're _still_ a fair bit above our level.
    1. some kind of spectral sequence to compute homotopy groups of a certain weird group.
    2. some explications through Künneth formula and also through standard interpretations of low-rank homotopy-groups.
3. nonetheless, they're appealing (the 1st lecture?) because they sketch the bleeding edge / the big problems to reach for. a sense of direction.

## logs
### 1st / intro
1. ok, so there's a bunch of stuff about soft/hard math and methods, I think not worth reconstructing
2. what's worthwriting down: Moore's (?) hypothesis about homotopic exponents.
    1. ok, so, fix a space X and consider its homotopy groups πₙ(X). if their p-torsions are bounded — there're groups with ℤ/pᵐ torsion but not ℤ/pᵐ⁺¹ torsion — it's said to have homotopic exponents.
        1. examples: spheres Sᵐ have exponents ε(m).
        2. wedges of spheres do not; they contain within themselves copies of _all_ homotopy groups of spheres, and therefore all exponents.
            1. (this is shown via the cup product?? intriguing!)
    2. second, consider rational homotopy groups πₙ(X)⊗ℚ. they have a dimension k(n). there's a fact that it either goes to 0 or grows exponentially with n. going-to-0 spaces are called elliptic and grow-exponentially hyperbolic.
    3. Moore's hypothesis: consider a (simply connected) space X. it has homotopy exponents iff it is elliptic.
        1. simplest case where the link is unknown: ΣℝP².
        2. even more concrete: it is known that π₇(ΣℝP²) ⊃ ℤ/8, but unknown if any πₙ ⊇ ℤ/16.

1. another direction: group theory! Burnside groups!
    1. oh that's where I heard about monstrous groups with weird properties.
    2. Tarski's monsters: infinite, any proper subgroup is cyclic. 2-generated, even!!
    3. another: finitely generated infinite group w/ exactly 1 nontrivial conjugacy class
        1. —i.e. all elements are conjugate / all conjugation auts are the trivial aut.
2. the problem of zero divisors.
    1. let G be torsion-free.
    2. hypothesis: the group ring ℤ[G] does not have zero divisors.
        1. proved for nilpotent torsion-gree G.
    3. it is _suspected_ that there's gonna be a counterexample because all kind of weird shit happens in groups.
3. Whitehead's asphericity problem
    1. let K be a 2-dim cellular complex. let it be aspherical, i.e. have π₂=0.
        1. note: all higher πs are also 0, as so: consider its universal cover. that cover is also a 2-dim complex with π₁ and π₂ trivial. and then uh....by Hurewicz its π₃ = H₃ and that's 0 because it's 2-dim? and likewise for all the other πs. huh.
    2. consider a subcomplex L ⊂ K.
    3. hypothesis: L is also aspherical.
    4. feels weird!!! but no counterexamples are known.
    5. Adams attacked that, some weird algebra fell out; perfect ideals = maximal perfect subgroups were involved
4. lower central series
    1. we take G; we take its commutant [G,G], then we take γₙ₊₁ = [γₙ, G].
    2. a group is called nilpotent-approximated(-able?) if γ_ω = ⋂ᵢ^ω γᵢ is 0.
    3. fun fact: the series might not stabilize at γ_ω!
    4. this plays a role in topology!

### 2nd: the prescient feeling of functorial surgery
1. Q: how do we compute nontrivial differentials of spectral sequences?
    1. A: by showing that everything in a spectral sequence is functorial, that differentials are nattranses, and showing that 2 given functors must have trivial nattranses & therefore differentials are 0.
2. definitions of various horrible group functors!
    1. (..let's work with abelian groups, they're nice and simple here.)
    2. ok, the tensor product / power ⊗ is at least semi-familiar.
        1. classic formal definition: for abelian G,H consider the free abelian on the alphabet of their product, 𝓕 G×H, (symbols of the alphabet denoted g⊗h) and then factor it by the relation that confers bilinearity:
            1. g₁+g₂ ⊗ h = g₁⊗h + g₂⊗h
            2. g ⊗ h₁ + h₂ = g⊗h₁ + g⊗h₂
        2. & now I want to practice a bit with it so let's try to compute some familiar forms for tensor products of simple groups.
        3. cyclics:
            1. we quickly see a &&lemma&&: 0⊗b + 0⊗b = 0⊗b, ergo a⊗0 = 0⊗b = 0.
                1. also, a⊗b + (-a)⊗b = 0 = a⊗b + a⊗(-b), so negation goes in and out.
                2. also, ofc n·(a⊗b) = (n·a)⊗b = a⊗(n·b); this shows reminds us about abelian groups being modules over ℤ, I think.
            2. in ℤ⊗ℤ, the above quickly gives us n⊗m = n·m·1⊗1, collapsing any formal sum into an a·1⊗1 and an iso to ℤ by 1⊗1 ↦ 1.
            3. exactly the same thing for ℤ/2⊗ℤ/2: n⊗m = n·m·1⊗1, collapsing to a group generated by 1⊗1 and relations 2⊗1 = 0. so, ⥲ ℤ/2.
            4. which is where we notice another &&lemma&&: for A,B generated by aᵢ & bⱼ, A⊗B is generated by aᵢ⊗bⱼ.
                1. (Σᵢnᵢ·aᵢ)⊗b = Σᵢnᵢ·(aᵢ⊗b) and etc.
                2. consequence: if we want a ⋀²A nontrivial, we'll need a non-cyclic A, because ⋀² sure removes 1⊗1.
            5. obviously ℤ/n ⊗ ℤ/m = ℤ/(gcd n m) and ℤ/n ⊗ ℤ = ℤ/n.
            6. ..&&corollary&& of generators: A⊗ℤ = A by a⊗n = n·a⊗1 and a⊗1 ↦ a.
            7.  and A⊗ℤ/n..sure does something n-torsiony to A? now n·a⊗b = 0 and so we get something like....A/{aⁿ=0}? I think.
        4. ok! let's product around some noncyclics.
            1. e.g. ℤ/2²⊗ℤ/2².
                1. ok, the first is generated by a₁,₂ & second by b₁,₂, so ⊗ is generated by the four a₁,₂⊗b₁,₂.
                2. obviously all of them have degree 2.
                3. it's commutative ofc.
                4. I...think....they have no reasons to be equal to each other?
                5. so it's ≅ ℤ/2⁴?
                6. (after considering ⋀ below) nnnno? maybe x²=0 is not the only imposed relation on them?
                7. —ah, seems like ⋀ eats another copy of ℤ/2 in its own way. ok then.
                
                8. .....ok, & if we zero out a₁⊗b₁ and a₂⊗b₂, we'll get..? I hear it should be ℤ/2? but naively I'd think it's ℤ/2²?
                9. ...let's do another notation, via a⊗b. so we have a⊗a, a⊗b, b⊗a, b⊗b as generators. (there's also 0 ofc.)
                10. so e.g. there's a⊗a + a⊗b = a⊗a+b. & if we sum all 4, we can do a⊗a+b + b⊗a+b = a+b⊗a+b. --waaaait.
                11. it _is_ true that after the factor a+b⊗a+b goes to 0, but also it sums out to a⊗b + b⊗a! so also these two must be inverses of each other now, & what's left is not ℤ/2², it's just ℤ/2.
            2. ...what's the smallest abelian non-cyclic after ℤ/2²? I think ℤ/2³, ℤ/4×ℤ/2, and ℤ/3²?
                1. ok, for ℤ/2³ I think I'll call generators of it a,b,c, and then there're 9 generators to the tensor square, & I think it's ≅ ℤ/2⁹?
                2. the exterior square ⋀² obviously eats a⊗a, b⊗b, c⊗c; also, like in ℤ/2², it eats a+b⊗a+b, generating a∧b=b∧a, and likewise a∧c = c∧a and b∧c = c∧b, down to at most 3.
                3. but there's also a+b+c∧a+b+c = 0! but I think this is auto-satisfied, because all symmetric pairs are already 0d out.
                4. so ⋀² is....ℤ/2³?
                5. (groupprops says yes! ok good.)
            3. for ℤ²:
                1. ⊗² is I think generated by the 4 elements again, & no square-relations now, so it's probably just ℤ⁴
                2. ⋀² obviously kills a⊗a and b⊗b and sets a⊗b = –b⊗a. (for a,b generators of ℤ².) now, does it do anything else?
                3. ....don't think so? so what's left is just a ℤ. neat.
    3. outer product/power Λ
        1. NB: for nonabelians it's more complicated and is usually called non-abelian outer product.
        2. ##why is there basically no definitions for it on the internet!!!##
        3. anyway, it's ⊗ⁿA / <⊗ᵢaᵢ | for some i≠j, aᵢ = aⱼ>
        4. &&Observation&&: a+b∧a+b = 0 = a∧a + a∧b + b∧a + b∧b = a∧b + b∧a ⟹ a∧b = -b∧a.
    
    4. aaaaanyway. there're also others.
    5. symmetric power: ⊗ⁿ/action of Sym n.
    6. ...separated power Γⁿ? defined for free abelians: invariants of action of Sym n on ⊗ⁿA.
        1. i.e. the subgroup that's stable under Sym n.
    
3. claim: –⊗ℤ/p is additive! i.e. F A⊕B = F A ⊕ F B.
    1. because.....0ing out p-powers simultaneously or per-component gives the same result, right?
4. also, there's a definition of polynomial functors of degree n
    1. any functor has a natural map F(A₁ ⊕ .. Aₙ) → ⊕ᵢ F(A₁ ⊕ .. ¬Aᵢ .. Aₙ).
    2. if it has a trivial map (is an iso?) at some n, the functor is polynomial, and the minimal such n is the degree of F.
    1. I..._might_ be missing something, e.g. a +1 at some index
5. definition: cross effect of a functor
    1. I think that's the kernel to the map F A⊕B → F A ⊕ F B.
    2. and generalized for nth crossed effect

6. sketch of a proof that the only nattrans A⊗A → A⊗ℤ/p is 0!!
    1. consider the crossed effect of ⊗ as a functor of F. it...has a nattrans to F A = A⊗A?
        1. (isn't it supposed to have a nattrans to F A⊕B?)
        2. (ahhh, I'm inattentive. there's the natural A⊕A → A, which we'll lift to Cross_F A → F A⊕A → F A.)
    2. it will transpire that it's epimorphic.
    3. then, we'll consider the cross effect of ⊗ℤ/p. it...is 0! because ⊗ℤ/p is additive.
    4. but cross effect is also a......functorial? construction, and so nattranses F → G lift to nattranses Cross_F → Cross_G.
    5. & then we have a commuting square where the bottom 0s out and the left is epi. then the top can't be anything but 0. and there we go.
7. works the same for any additive functor!!
    1. & also whenever we can show that F A|A ↠ F A.
8. works..similarly? for an additive functor → ⊗² to be 0
    1. we'll use the natural map A → A⊕A instead but it's claimed it works similarly.

9. a wonderful method of computing arrows between functors!
    1. we'll be computing Sym² → ⋀²
    2. we'll be in...freely generated abelian groups, but that's fine, because:
        1. these functors commute w/ limits, so....finitely generated is enough for everything??
        2. and also they're epicfunctors (right exact?) & so free abelian imply everything?
    3. (to be precise, we'll treat them as operating on the _domain_ of freely generated abelian groups; codomain is arbitrary abelian.)
    
    4. there's.....an unhinged equivalence of categories? of quadratic functors FreeFinAb → Ab and of diagrams in Ab of form A -P> B -H> A  where HPH = 2H & PHP = 2P.
    5. (a digression: there will be at some point a Hopf map πₘ(Sⁿ) → πₘ(S²ⁿ⁻¹) and Whitehead's bracket (of the id map?) back, πₘ(S²ⁿ⁻¹) → πₘ(Sⁿ). annnnnnd turns out these satisfy HPH=2H and PHP=2P & therefore induce a quadratic functor of some kind. wild.)
    
    6. construction!!!
        1. we'll send functor F to the diagram F ℤ → F ℤ|ℤ → F ℤ, with the exact same arrows as before
            1. i.e. F ℤ → F ℤ⊕ℤ → F ℤ|ℤ by F-ing the diagonal map &....(ah. F ℤ|ℤ splits inside F ℤ⊕ℤ?) yeah, ok. so that's H.
            2. and for P we F ℤ|ℤ ↪ F ℤ⊕ℤ → F ℤ (by F \a⊕b → a + b).
    7. anyway, let's do the diagrams.
        1. (a bunch of diagrams in which we compute F ℤ and relevant maps for specific functors)
        2. %%todo%%
        3. note: this is not enough to show existence — we'd need to do the reverse of the equivalence — but enough to show that the only nats are 0.
            1. because then we'll.....do induction over n in ℤⁿ and that'll show 0s for any fingen free abelian. ....neat.
    8. example of how 0s happen:
        1. Sym² has the diagram ℤ -2> ℤ -1> ℤ. ⋀² has 0 → ℤ → 0.
        2. the only not-immediate arrow in Sym²→⋀² diagram is the middle one, but...ofc it's also 0: the left square goes to 0 on the left.
        3. & ∧²→Sym² likewise but from the right square that 0s on the right.
    9. (a definition of how to convert diagrams back to functors via a functor whose value is given by generators & relations. weird-ass.)
1. Observation: this diagram, A → B → A, can be shifted to B → A → B with.....the eaxct same properties. this gives a kind of duality to quadratic functors.
    1. Thesis: this shift is........functorial? extremely exactly functorial? i.e. all kinds of diagrams on functors are preserved by this shift.
    2. smth smth a...comprehensible...ish....diagram on 6ish functors converted, magically, into the Koczul sequence? complex?
2. Observation: same shit can be done with nattranses!
    1. they're represented by the morphism of diagrams A→B→A ⟹ C→D→C.
    2. obviously we can rotate them both, but! we can also rotate only 1!!!
    3. shift the bottom row leftwards once. morphisms A→D and B→D are the most obvious ones, compositions of the initial diagram.
    4. it is _blatantly_ again a diagram. done.
    5. likewise can shift the top....some direction.
    6. (this is not idempotent! but apparently so deeply exact/functorial that all diagrams involving original morphisms oblige us.)
    7. *THAT's* what's called functor surjery.
3. so this way we can rotate a single functor in a diagram along with maps into/from it, and get interesting shit.
    1. example: start from the Id: ⊗² → ⊗².
    2. rotate ⊗² on the left once. becomes the (pase?) functor. well, ok.
    3. rotate again, get ⊗² back. but the nattrans is not Id now. it is now a⊗b ↦ a⊗b + b⊗a.
    4. it has Sym² as image; ⋀² as kernel; ⊗²~ as cokernel. so, most of things we were concerned with.
    5. neat?