# Hatcher's Algebraic Topology reading meta
## Meta
1. [The book](https://pi.math.cornell.edu/~hatcher/AT/AT+.pdf)
    1. additional: https://pi.math.cornell.edu/~hatcher/AT/ATpage.html
    2. also, Ch.5: https://pi.math.cornell.edu/~hatcher/AT/ATch5.pdf

1. meditation on hardness
    1. ..given how hard Hatcher goes & how easy the _not first_ reading of fundamental group went, I think it might be wise to, well, read through a bunch of it somewhat shallowly first, such that we catch basic concepts & soak in some proof sketches and techniques.
    2. on that front, it sounds about approximately correct to run through the rest of Ch.2 and also 3 and 4, in parallel w/ finishing 2 properly?
    3. sure why not I guess
2. meditation on alternatives
    1. [[Algebraic Topology reading meta]]
## Plans

1. 2024-12-23:
    1. I'm in an alternative mood, I disliked hatcher's exposition of a lot of shit, & want to touch homotopy groups :<
    2. soooo I'm skipping over reviewing homology and what we managed to understand about cohomology and jumping right into Ch.4 about higher homotopy groups.

### plan/status (2024-09-ish):
1. We ran through Ch.0, and some of that was somewhat new (e.g. infinite CW complexes), & should really do the exercises & such
2. Ch.1, the fundamental group and van Kampen and covering spaces, we know from Munkres already, so we jumped right to Ch.2
    1. but we do not e.g. know K(G,X) spaces and those sound important.
3. Ch.2:
    1. after a couple passes we got like 70% of a whole lot of things going on there.
    2. singular homology! exact sequences! chain complexes and chain maps and chain homotopies! abstract homology groups! the zigzag lemma for producing long exact sequences of homology groups!
    3. barycentric subdivision in 4 parts, smh leading to excision and equivalence of singular homology to any other!
    4. aaaanyway, we still need to do a couple more passes to compile this thing in full, and then _also_ do exercises. eesh.
    5. and that's just 2.1! there's also the whole 2.2 of Computations and 2.3 of Axiomatic Homology, though the last I expect to go easier.
    
    6. somewhere along the line there's a motivation for homology w/ coefficients, because it can sometimes be nonzero even when ℤ-coefficient homologies are 0!
        1. particular example of some long sequences for dunce-cap-like constructions w/ alternating-0 homology groups in ℤ, where shifting the dimension by 1 gives only zero maps, but for ℤ/n they are all nontrivial & have nonzero maps
4. Ch.3: Cohomology
    1. looks no less interesting than just homology, want
5. Ch.4: Homotopy proper
    1. WANT
    2. _especially_ methods of calculation
    3. and then also at least some additional topic (spectra? loopspace? Steenrod? we'll see.)

## Chapters

### [[Hatcher 3.0- Cohomology intro]]
1. todo: ....maybe extract/list new concepts introduced & review?

### [[Hatcher 3.1- Cohomology Groups proper]]
1. todo: ....maybe extract/list new concepts introduced & review?

### 4: Homotopy Theory
#### 4.0, aka homotopy theory intro
1. blurbs from the intro!

1. abelian! (I know.)
2. relative homotopy groups! (...augh? ok fine probably relatives are useful....)
    1. long exact sequence around them, just like there's a long exact of relative homology groups
    2. .....huh.
3. ...in general, neither excision nor van Kampen, sooooo πₙ are much harder to compute than π₁.
4. Whitehead's theorem, that a map between CW that isos all the groups is a homotopy equivalence!
    1. (but mere iso of groups is not generally enough, huh)
5. Eilenberg-MacLane spaces!
6. Hurewicz theorem, that first nonzero homotopy group is ≅ first nonzero homology group!
7. ...excision does hold sometimes, which is e.g. Freudental's suspension, & then we get stable homotopy groups & theory and computations for spheres

8. .....fiber bundles, generalizing covering spaces!! huuuuh.
9. ...and later further generalization: fibrations, twisted products, Postnikov towers, k-invariants

#### 4.1: Homotopy groups
1. table and observations
    1. 0s below diagonal, for i < n. supposed to be easy.
    2. πᵢ(S¹) = 0. easy to prove by....what? "covering space theory"?
    3. the, uh, π_i(S^2n) ≅ π_i-1(S^2n-1) × π_i(S^4n-1) for n = 1,2,4
        1. for n=1 it means that π_i(S²) = 1× π_i(S³); for n=2 it's π_i(S⁴) = π_i-1(S³) × π_i(S⁷), which is...interesting.
        2. & actually if we ignore the 2-torsion it's true for all n. (James, SSAT)
    4. ℤs on the diagonal: Hurewicz.
    5. Serre (SSAT): for i>n all groups are finite, except for π_4k-1(S^2k), which are ℤ + finite.
2. definitions!
    1. homotopy classes of maps of cubes that keep the cube boundary at the basepoint.
    2. addition by gluing the 2 cubes on the 1st dimension.
    3. (doesn't matter the dimension! tbh there's the eckmann-hilton argument for how these operations work.)
    4. equivalently, maps of spheres! the addition is via belting the sphere up into 2 spheres.
    5. -----aaaaand here I'm going on a distraction about trying to naively extend covering spaces to spheres and how that doesn't quite work.
        1. [[Covering S² and how it-s not a covering space]]
    6. ...moving the basepoint is kind of uninspiring but sure ok fine. γ f, γ (f+g) = γ f + γ g, γ (η f) = (γ ⧺ η) f, 1 f = f, the works. and then PC spaces have groups indep of basepoint.
        1. ---the trick is to take the map of the cube, shrink it to map a smaller inner cube, and then map the intermediate radially by γ. this is "obviously" continuous, and it does change the basepoint, and has all the convenient properties above.
    7. ......ok, yes, π₁ acts on πₙ by [γ] [f] = [γ f].
    8. that πₙ is a functor is not _shown_ at all. exercise, then.
    9. that a homotopy between maps sets these maps' action on the group to be the same is also not shown.
    
    1. nice behavior wrt covering spaces! covering space projection induces isomorphisms of all higher homotopy groups.
        1. I....do not understand their proof at all.
        2. I think they say "maps Sⁿ → X lift at all, by lifting criterion, so long as Sⁿ is SC", which makes the map from π of the covering space surjective.
            1. well they send to Prop. 1.33, let's maybe look at that
        3. and injective, they get from...."covering homotopy property"? what?
            1. like in 1.31, so, likewise.
            2. in 1.31 they note that π₁(p) is injective, because a loop that contracts to a trivial with the homotopy α can have this homotopy lifted right back. and therefore contracts in the covering space also. so, the kernel of π₁(p) is trivial and it's injective.
            3. ----ah, covering homotopy property is exactly the same as homotopy lifting property.
        4. ----ah, so. uh. _maps_ lift, so any group element has a preimage, so the group morphism is surjective.
            1. ----ah, there's a criterion for maps lifting!
            2. it says that Y, from which we map, should be PC and locally PC
            3. but also that (f: Y→X) f(π Y) should be contained in the p(π E).
            4. ....ahhhh, and they satisfy that last by making n ≥ 2 and therefore π₁(Sⁿ) = 0
        5. but also homotopies between maps lift, & so an element homotopic in the image is also homotopic before the image, & so it's injective.
        6. huh.
    2. ---in particular, if X has a universal cover that's contractible, then the cover has all groups trivial, & so X has all groups above the first trivial. fun!
        1. and that gives us πₙ(S¹) = 0! fun.
        2. products of circles, like n-torii, are too! because ofc universal cover product (I think it's true) & so they have univ-cover ℝⁿ.
    3. group of product is product of groups
        1. because, uh, by definition of product, maps Y → Πᵢ Xᵢ are bundles of maps Y → Xᵢ, and so the group of product factors into groups of components.
    
    4. relative homotopy groups!
        1. normally we map (Iⁿ, ∂ Iⁿ) → (X, x₀).
        2. let's instead pick a face Iⁿ⁻¹, define Jⁿ⁻¹ as the union of the other faces, and map (Iⁿ, ∂ Iⁿ, Jⁿ⁻¹) → (X, A, x₀), with homotopies to match.
        3. I think in normal terms we pick a face that's allowed to go to A instead, but all the other boundary (including shared -2-faces) must still go to the basepoint.
        4. it _is_ a generalization: if we set A = x₀ we recover the original homotopy groups.
    
    5. now, πₙ(X, A, x₀) is a group for n ≥ 2 and abelian for n ≥ 3; that's because we typically pick the face that has nth dimension 0.
        1. ----that's because we can still cram 2 cubes into 1; we don't even need to orient the faces right because they're already oriented.
    6. .....ah, if we pre-collapse Jⁿ⁻¹ to a point, we get the final face of the cube to be its entire boundary, and so get maps (Dⁿ, Sⁿ⁻¹, s₀) → (X, A, x₀).
3. %%.....I'm having problems keeping my attention on relative things, so there's a skip here, through Whitehead%%
4. Cellular approximation!
    1. notion of the cellular map: between 2 complexes X → Y, cells of X must map to cells of Y of same degree or lower; f(Xⁿ) ⊂ Yⁿ.
        1. i.e. image of a point is a _point;_ image of an edge...must stay within edges and must in fact start and end at the point; image of a face must stay within faces and have -1-faces at the boundary. et cetera.
    3. Theorem 4.8: any map of CW complexes is homotopic to a cellular map!
    4. ............oh. this means we can say _a lot_ about possible maps-up-to-homotopy between CW complexes like spheres.
    5. ........in particular if we take the 2-cell structure for i-sphere and n-sphere (i < n), a cellular map Sⁱ → Sⁿ must map the i-simplex to the point, and so..... πᵢ(Sⁿ) = 0.
    6. .......what?????? just like that????? what???