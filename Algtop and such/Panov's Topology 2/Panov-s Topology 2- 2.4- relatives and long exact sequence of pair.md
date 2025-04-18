# Panov's Topology 2: 2.4: relatives and long exact sequence of pair

up: [[Chewing on NMU-s Panov-s Topology 2 (algebraic)]]


1. .....ok, this I mostly skimmed in hatcher, time to try to figure it out.
2. trying to generate ourselves, but still.

3. ok so.
4. Cₙ(X,A) is defined as CₙX/CₙA. weird?
5. I.....think....I want to meditate on the categorical structure here.
    1. so obviously there's a category of, uh, spaces and subspaces? where maps make the injection square commute.
        1. ---the important part here is that the map (X,A) → (Y,B) must in fact take A to B. not injectively or surjectively or anything, but at all, yes.
    2. in a certain sense it's just a generalization of the category of pointed spaces: a point is just a map * → X.
    3. and then, we'd like to functor this category to chain complexes again, and informatively.
    4. it's...true....that ∂ restricts to A? Δ-maps to A have boundaries (restrictions) in A, yeah.
    5. and therefore, ∂ also restricts to...CX/CA! this is A Thing to fit into the mind, but it's true; we've figure out this lemma for homology groups already. A↪B↠B/A maps by f:B→Y to X↪Y↠Y/X because f restricts to A naturally, and then b±A goes to f b ± f A and is a meaningful mapping of factorgroups, and inherits morphism properties from B.
6. and now we have a...wholly different chain complex Cₙ(X,A)......and we can do homology groups to it.
    1. ....and then there's an obvious SES 0 → C A → C X → C X A → 0 and presumably it extends to a chain map and from there to the long exact sequence H A → H X → H X A → H A.
    2. let's...check that in fact it extends to the chain map. 
        1. C A -i> C X must commute with ∂: obviously!
        2. C X -j> C X / C A must commute w/ ∂: well if we take a homology class cx ± CA & send by ∂ we get the class ∂ cx ± ∂ CA. if we ∂ it first we get to ∂ cx & then to ∂ cx ± C₋₁A which is the same class so yeah.
    3. groups H X A are......nnnnnnot very intuitive.
    4. their elements are, well, zxa ± B X A. zxa is from CX/CA and has ∂ = 0 considering that. it's a chain in CX whose boundary is...in C₋₁A?
    5. and 0 in H X A is, well, bxa, which is a boundary ∂(CX/CA), right?
        1. they say that's when it's a boundary in X plus _anything_ in A, which, fair
7. ok, geometric intuition for the ∂ : H X A → H₋₁ A.
    1. unfolding a little, it goes zxa ± bxa ↦ _ in C X ↦ _ in C₋₁ X ↦ _ in H A.
    2. bxa I think won't matter because it dies fast. zxa is a cx | ∂cx ∈ C₋₁A. so it lifts to cx ± CA in any case but also with that side-condition.
        1. so, zxa ± bxa ↦ cx ± CA ± j⁻¹ bxa in CX.
    3. then ∂ to ∂cx ± ∂CA. ---ah, this is not trivial because ∂cx ∈ C₋₁A, not ∂CA.
    4. ...and then we lift to the exact same boundary in C₋-1A! cool!
    5. so: class of H X A is represented by zxa, which is from CX/CA w/ ∂=0, i.e. a cx whose ∂ is 0 up to CA, i.e. ∂cx ∈ CA.
    6. and the ∂ : H X A → H₋₁ A sends zxa exactly to the boundary ∂cx ∈ CA!
        1. ....it should be in ZA though.
        2. well, in X it'd be a BX actually, because it's a boundary of cx.
        3. I suppose A might lack, well, cx of which it is a boundary.
        4. ∂ing it again, however, must produce 0 in CX, and in CA also because it's just a restriction.
        5. so it's in ZA.
8. 