# Hatcher 3.1: Cohomology Groups proper

## Meta
1. 1st log from around 2024-09
2. extracted from [[Hatcher's Algebraic Topology reading meta]]

## 1st readthrough log

1. Goals:
    1. figure out that cohomology groups are determined entirely by homology groups
    2. some basic properties of cohomology groups of spaces
2. observation: any chain complex of finitely generated free abeian groups is a direct sum of elemetary complexes of forms 0 → ℤ → 0 and 0 → ℤ -m> ℤ → 0
    1. and then dualizing converts the ℤ/m component of Hₙ into ℤ/m comonent of Hⁿ⁺¹. huh.
    2. Q: and what'd happen if we dualized by Hom(—, G) instead of Hom(—, ℤ)?
        1. well the original complex also splits, and ℤ → G ≅ G fairly obviously, and the map ℤ -m> ℤ becomes a map G -m> G? yeah, make sense: if the latter ℤ goes as 1 ↦ g, then the former goes as 1 ↦ m ↦ mg. ok.
        2. then the 0 → G → 0 components stay where they are, and 0 → G -m> G → 0 components, uh
        3. and, ok, what's G/mG look like in general?
        4. well ℤ-components of G become ℤ/m; ℤ/n coprime with m I think stay in place?
        5. ...ok, actually, let's compute how mG looks like first, and then G/mG will be uncomplicated.
        6. for a cyclic ℤ/n, mx=0 mod n..won't have solutions when m and n are coprime?
        7. elsewise, the element n/(gcd n m) goes to 0 in mℤ/n ≅ ℤ/(n/(gcd n m))
        8. and.....ok, by abstract nonsense: factor of cyclic is cyclic, of size n/(n/(gcd n m)) = gcd n m.
        9. there, done. ℤ/n-components of G shift up and become ℤ/(gcd m n)-components of H.
3. oh btw things from earlier we skipped over: split sequences
    1. first, criteria of split sequences
        1. SES of abelians 0 → A → B → C → 0 splits if any of 3 equivalent conditions
            1. B ≅ A ⊕ C s.t. maps go a ↦ (a, 0) and (–, c) ↦ c
            2. there's an inverse B → A that's id from A
            3. there's an inverse C → B that's id from C
        2. (1) → (2) is obvious via (a, —) ↦ a, (1) → (3) is obvious via c ↦ (0, c)
        3. (3) → (1): C ↪ B provides a canonical labeling of A-cosets in B. now send b to its decomposition c + a, which is a homo because b₁ + b₂ = c₁ + c₂ (∈ im C) + a₁ + a₂ (∈ im A), just like in C ⊕ A. action of maps is easy to verify.
            1. this works because now we _can_ pick representatives of cosets that, themselves, form a C-subgroup.
        4. (2) → (1): exactly the same way, we have a canonical labeling of A-cosets in B, and we get B ≅ A ⊕ ker (B → A). and if we then map by j, the A-part zeroes out and we get a surjection ker (B→A) → C. ..but _only_ A-part zeroes out, so it's an injection also.
    2. second, claim: 0 → A → B → C → 0 always splits if C is free
        1. ..so like. for every generator cᵢ of C, we arbitrarily pick its preimage jᶜ cᵢ in B, and then jᶜ is a homomorphism?
        2. i.e. we send Σᵢ nᵢ cᵢ ↦ Σᵢ nᵢ (jᶜ cᵢ). C presented like that only has trivial relations, & with this definition they of course hold.

4. The universal coefficient theorem!
    1. I'm still annoyed that they do not _telegraph_ that the following several pages of arcane diagrams will have a satisfying payoff, but, ok, fine. maybe it's a learning experience that in the real math things don't work this way.
    2. also, we'll need to reread this to understand how they.....approach the problem at all. there's strategy in there!
    3. but anyway.
    4. the buildup here is to the thesis that cohomology groups _can_ be computed from homology groups (& the target group).
    5. to get there, they do...a bunch...of...things....
    6. but in particular they smh figure out that there's a surjection Hⁿ(X,G) → Hom(Hₙ X, G)
    7. and then by some arcane manipulations with extensions they manage to embed the Hom right back into Hⁿ, which shows that the exact sequence ker h → Hⁿ → Hom splits! which is quite blatant about the structure of Hⁿ.
    8. then they manage to compute the ker h also!
    9. smth smth yet more SES joined into a LES, and somehow they arrive at a dualization of a free resolution, which is a device to be introduced shortly
    10. and then all free resolutions are chain-mappable to each other, uniquely up to a chain homotopy, and from there cohomology groups only depend on the base group & on the dualizing group.
    11. and then for abelian groups there's an uncomplicated free resolution 0 → F₁ → F₀ → H → 0, H⁰ is smh trivial, but H¹ is interesting, and is called Ext(H, G)! so that's cool.
5. ok, let's...go through the motions properly, perhaps?
    1. concept of a free resolution: yeah----uh, ok, actually I've been missing whether it's an exact sequence or merely a chain complex.
        1. an exact sequence! ... → F₁ → F₀ → A → 0.
    2. thesis: any abelian group has a 2-term resolution.
        1. well, as they said: pick a set of generators of A, generate F₀ on them freely, map obviously to A.
        2. it's a homo because free, and exact at A because surj obviously.
        3. now, ker f₀ is ~~generated by nx, n-multiples of generators x that go to~~ WRONG and also DOESN'T MATTER
        4. ker f₀ is _a subgroup of the free F₀_ and therefore is itself free.
        5. set F₁ to be the relevant subobject, and we get exactness at F₀ by im=ker and also at F₁ by inj.
    3. thesis: for any abelian H,H' and their 2 free resolutions, any map h: H → H' extends to a chain map h* between the resolutions, unique up to chain homotopy.
        1. (paper paper paper)
        2. oh!! I see!
        3. & I think we're starting to get the hang of these homotopic algebra techniques.
        4. ..should we try to enpost it?
    4. ---ok, let's sketch what we'd...need.....to include in the post such that it is remotely comprehensible.
        1. the target is the theorem:
            1. formulation: "for any free resolutions F ↝ H, F' ↝ H', a map h:H→H' extends to a chain map (F→H→0) → (F'→H'→0), uniquely up to a chain homotopy."
                1. "free resolutions" can simplify immediately to "a long exact sequence", but that's not saying much.
            2. so: chain complexes (+ motivation) → exactness and LES
            3. a brush on associated homology groups, just so we know what's the big payoff
            4. criterion for chain homotopy and motivation
                1. that it suffices to show that the two maps induce the same morphism of homotopy groups
                2. but also, rearranging it as f.Pₙ₊₁ = f-g-Pₙ.f, we often can _construct_ a suitable Pᵢ inductively, thereby demonstrating that some pair of morphisms is not worth distinguishing. (not uncommonly, we can then pick a canonical morphism that's equivalent to many others but convenient to work with, or show that some morphism f is equivalent to id and therefore induces isomorphisms.)
            5. and then also the proof!
                1. first, the trick where we can map generators of F wherever and that's a valid morphism
                    1. and, like, the first part of the proof where we show existence
                    2. %%()%%
                2. second, the instructive n=0 case, in which f-g → ker f₀' = im f₁', and so we can pick the action of P₁ to provide that
                3. third, the general case, where we use the f.Pₙ₊₁ = ... representation to gesture suggestively, define the action of Pₙ₊₁ by freeness assuming the LHS is in im f, and then use the im=ker trick again, apply f, and compute until we reach 0, as desired.
        2. .....I could in principle do this. maybe it _would_ be marginally better than Hatcher, because I would in fact call attention and explain the tricks.
        3. but honestly the moment is past. let's go on.
    5. ---tho let's recap, it's a couple days later now.
        1. first part: the extension exists.
            1. base step: construct the h₀. (draws the H-H'-F₀-F₀' diagram.)
                1. F₀ is free so it suffices to send its generators _anywhere_ that will satisfy the commutativity square.
                2. observe how f₀' is surjective, so the image h (f₀ x) of F₀ in H' is contained in the image of F₀'. now, for any h (f₀ x), pick some preimage of that in F₀', and send x there. we're done.
            2. induction step: this actually works for hᵢ.
                1. hᵢ is a component of the chain map (on the side towards H), so it sends ker fᵢ to ker fᵢ'. which is to say it sends im fᵢ₊₁ → im fᵢ₊₁. this is exactly the condition that allowed the base construction to work, so, hᵢ extends to hᵢ₊₁ in the same way.
        2. second part: any 2 exts are chain homotopic
            1. ...honestly I still don't have a good description/representation for this.
            2. work from the form of homotopy chain condition where we put the newly-defined Pₙ on one side as f'.Pₙ and others on the other side.
            3. observe that it suffices to show that the other side is in im f', i.e. ker f'ₙ₋₁. apply that last and derive zero.
            4. derive zero how: well f'(h-h) - f'Pf = (h-h).f - f'.P.f = (P.f+f'.P).f - f'.P.f = 0.
            5. so like....push the hs down & unfold by the homotopy chain sometimes?
    6. ---oh hey, I think I see how chain homotopies stay chain homotopies after dual
        1. see, f-g-Pd-dP=0 is a map X*→Y*, and therefore a map (Y* → Z) → (X* → Z), by precomposition. or rather, all of these lift to dual maps by precomposition, and addition of maps commutes with duals (I think?), so we get a dual of the added map. 0;f = 0, the dual map sends everything to 0, & so the dual of the 0 map is again the 0 map! and so homotopy chain condition holds after dualization.
        2. and therefore the inexact sequence & its cohomology groups are all one and the same, because any map F → F' has a homotopy inverse F'→F (chain homotopic to id_F), and therefore the composite action on the cohomology groups is an iso, & therefore both steps are themselves iso, so cohomology groups are canonical, independent of the choice of the free resolution.
        3. ok.
---
1. ok uh. 
    1. we were meditating on Ext¹ and why it's the only interesting cohomology group of an abelian group, & I think we got enough of it
    2. example of how it's nontrivial:
        1. Consider Z → Z → Z/2 and dualize against Z/4.
        2. to figure out the action of reverse arrows it's instructive to consider maps X → Z/4 labeled by images of 1, and how precomposition w/ ∂ alters them, as visible in the triangle e.g. Z -2> Z -{0123}> Z/4.
        3. buuut to cut the story short, we get maps: Z/4 <2- Z/4 <2- Z/2
        4. & then we observe H¹ ≅ Z/2 and H⁰ ≅ 0, i.e. ker f¹ = Hom(G,H) as embedded by the injection.
    3. this leads us to the following 2 interesting facts:
        1. f⁰ is in fact an injection!
            1. i.e. if we have a mapping of generators of G into H, that produces a mapping of generators of F₀ into H, distinct for any distinct.
        2. and also, ker f¹ _is_ the same as im f⁰, i.e. any morphism F₀→H in ker f¹ we can factor through a morphism G→H and f₀.
            1. that's because f¹ acts on F₀→H by restricting functions to their action on images of f₁, i.e. elements of F₀ which are 0 in G.
            2. and ker f¹ is exactly functions F₀→G which map all G-zeros to 0.
            3. but any such function is factorable through G like this: you send generators of F₀ to G, then you send g:G wherever its preimages f₀⁻¹(g) go to under μ.
            4. this is a morphism as inherited from the fact that the original F₀→H is a morphism.
            5. it's coherent because for 2 preimages f¹, f² of g have f₀(f¹-f²) = 0, and therefore μ(f¹-f²) = 0, so μ f¹ = μ f².
    4. oh, and also the example shows us our mistake:
        1. we thought H¹ would be trivial because the ∂¹ ought to be surjective, because we thought it'd be a direct-sum-like subgroup, and so mappings of generators of F₀ encompass all mappings of generators of F₁.
        2. not so! some maps of F₁ can't be factored through F₀, because we can't map e.g. ng to h when h has no n-divisor, but we can map the (ng) element of F₁ so.
2. next thing I wanted to do is to figure out wtf they're talking about w/ cokernels & the formulation of the universal coefficient theorem.
    1. thesis we'll need at some point: dual of a split SEE is also split
    2. computations for Ext:
        1. Ext(H⊕H', G) ≅ Ext H G ⊕ Ext H' G
        2. Ext (Free —) G ≅ 0
        3. Ext (ℤ/n, G) ≅ G/nG
    3. 