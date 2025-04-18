# Panov's Topology 2: 2.1 (singular homotopy definition & first properties)

(up: [[Chewing on NMU-s Panov-s Topology 2 (algebraic)]])

1. ok, why not chew on nmu's https://old.mccme.ru/ium/postscript/f24/panov-topology2_09-09.pdf.

1. take: we've been skipping the proper infinitary definition of (semi?)simplicial complexes, let's unskip it this time.
    1. definition: it's a family of maps Δⁿ → X with properties:
        1. they all are injective on internals, _and_ every point of X is inside unique image of the internal
        1. restricting to a face gives another map
        1. A ⊂ X is open iff it's open under all preimages.
            1. open → preimage open is just continuity.
            1. all open → open is some kind of joint-openness of the maps.
    1. exercise!
        1. consider the subspace of ℝ² made of radiuses from (0,0) at angles 2π/n. it is said that this is _not_ semisimplicial due to the 3rd property.
        1. I...think naively if we glue ω Is into a wheel like that we'll get no limits and we do have limits here, so let's try to construct something around the limits that'll violate the 3rd property.
        1. we...can't violate open → preimage open because ofc these things are continuous.
        1. I...think the spokes topology is rougher than the ω×I one, so we should be able to find a set that'd be open by the property but not in ℝ².
        1. —oh ofc. an open interval inside the x-axis radius would be open normally but not in ℝ². and all of its preimages _are_ open because they're either itself or empty.
1. ...claim: semisimplicial complexes are a rather bounded class of cellular complexes.
    1. hm. I guess maybe? sounds weird though; aren't cells close enough to simplices?
1. definitions of simplicial homologies, some sample computations
    1. ----annnnd I find myself reaching for sequences to compute homologies of the torus! ok, yeah, I do want to recomprehend homology exact sequences.
    1. there're, what, relative, ?excision? and some other? is Mayers-Vietoris relative or something else? something else. ok.
1. exercises:
    1. semisimplicial → cellular: ....well I'll need to look up cellular for that. fine.
        1. ......ok LET'S TRY.
        1. "injective on internals and every point is in the image of a unique internal" translates directly into "every cell's map is iso on the internal". there's an exercise to show that they are in fact isos in simplicials so fuck it.
        1. boundary of every cell is in the union of fin many lower-dim cells: yeah, because simplicial cells are just faces (I so defined) and boundary of any cell is obviously finitely many its faces.
            1. ----_all_ its lower faces actually but it's good.
        1. ok, & now we need to connect "open iff all simplicial preimages open" to "closed iff intersection with every cell-closure is closed".
            1. ...within the cell-closure?
        1. hm. if A is closed then coA is open, preimages to all simplices from coA are open & so preimages of _A_ are closed, being complements within the simplex. so we also have "closed iff all simplicial preimages are closed"?
            1. ----not exactly? closed → all preimages closed. all preimages closed → preimages of complement open → complement open → closed. ....huh.
            1. yeah sure seems like these are all biimplications.
        1. ok, so yeah we have a more convenient "closed iff all simplicial preimages are closed".
        1. well uh. that's almost identical to the goal?
        1. intersection of A with a cell-closure is an intersection with a simplex-image. we want A to be closed (by rules of semisimplicial) iff its intersection with all cell-closures is closed.
        1. ok, 2 sides.
        1. A closed by rules of semisimplicial → intersect w/ cell-closures is closed.
            1. that means all simplicial preimages of A are closed. they are.....not exactly intersects w/ cell-closures....
            1. idea: maybe an intersect w/ cell-closure _should_ be closed.
            1. how about simplicial preimages of A ∩ ϕ for some image. if they're all closed we won.
            1. closed under ϕ: yeah, that's just preimage of A under ϕ.
            1. under others: well how can others intersect w/ the image of ϕ? if no intersection, then automatically closed.
            1. if yes intersection, then actually intersection ϕ ∩ ψ can't intersect ϕ°, so it's inside of ∂ϕ, and we recurse into "why is A ∩ ∂ϕ closed."
            1. until we get to the end where ∂ϕ is a set of points that is....obviously? closed, and so etc.
        1. .......maybe I'm overthinking this, and it should be as simple as "cell-closures should be closed, so if A is closed then A ∩ ϕ also closed ofc"?
            1. welllllll cell-closures are in fact images of ϕ and we might need to motivate their closedness the same way as above. ok, w/e.
    1. cellular that's not semisimplicial: ughhhh
        1. ...hmmm. let's try to retrace definitions of both.
        1. semisimplicial: maps of simplices, inj (→iso) on internals, faces are maps, open iff all preimages open
        1. cellular: maps of balls, disjoint and iso on internals, C (boundary is finitely contained in lower maps), W (topology: closed iff all intersections w/ cell-closures closed)
        1. ...ok, easy to violate the letter by attaching the boundary not at all along----wait can't glue it wherever, it should be contained in lower maps!
        1. and given that characteristic maps are disjoint on internals, we can't map the boundary...wherever? or can we? confused :<
        1. ok, example: sphere w/ a seam. w/ a point maybe, even! 2 cells: sphere & point; charmaps are disk w/ boundary to point and point to point. boundary of the disk (image) is contained adequately (C) and it's W because finite and, like, normal. ok.
        1. this....is not a semisimplicial structure because there're no d1-maps to be seen.
    1. ....now to define a CW complex that cannot be given a semisimplicial structure is I think more of a challenge.
        1. %%ehhh fuck it maybe later.%% ....there are in particular simplicial approximations, so uh. (...are they only for (semi)simplicial complexes? hm.)
        1. anyway, questions on mathoverflow suggest sphere w/ a point for the exact same reason (no 1-cells) nd suggest that that's the answer. ok.
    
1. CW complex: split into (open) disjoint cells; every cell has a characteristic map Dⁿ → Φ that's an iso on the internal. plus conditions.
    1. Cellular: boundary of every cell is contained in a union of finitely many less-dimensional cells
    1. Weak: Y is closed iff its intersection with every cell-closure is closed.
        1. commentary: weak is Whitehead's terminology, and he said "weak topology" where we'd say "fine topology"; CW topology is the finest in which all characteristic maps are continuous. aha. innnnteresting?
    1. alternative definition: we can attach an n-cell to a CW complex Y by sending the boundary ϕ: Sⁿ⁻¹ → Y however (continuously) and taking the factor Dⁿ ⊔ Y / (x, ϕ x), gluing along the image of the boundary.
    1. and then the ω step has topology in which Y is closed iff Y ∩ Xⁿ is closed for any finite skeleton.
    1. .......I'm not exactly of the mind to do the exercise to show that these 2 are equivalent but, surfacedly, sure.
    
    1. examples/non-examples
        1. curious one: ω×I with _metric_ topology (along the space) as opposed to the standard factor one.
        1. it is said that the factor one is finer! example: sequence of 1/k along kth spoke must be closed by W (intersect with any spoke: get the closed point) but in metric it has 0 as a limit and closed sets are closed under limits.
        1. I _think_ this is because the standard factor says "open set around the 0 is _any_ union of individual open sets per disjoint component", including open sets that decrease infinitely as the spokes go on.
        1. that _would_ be finer, for sure.
    1. -----i find that I don't want to force CW complexes formalities into my brain presently.
    1. I suppose I might not progress without there. fiiiiiine.

1. ---anyway, more exercises.
    1. consider the dunce cap, w/ cellular structure of point, circle, and disk whose boundary is glued into the circle w/ 3-layer map. that's....cellular because boundary is covered by lower maps all right. 
        1. Q: do these three give a semisimplicial complex structure?
        1. ......well once again let's recall the definition......
        1. simplex maps ✓. inj and disj on internals..✓, the circle is fine. boundary is a map: .......no? boundary of the disk goes as the 3-fold map, not as the inj circle map.
    1. compute simplicial homologies of a klein bottle and of a sphere.
        1. ...semisimple are in fact easier either way.
        1. hooooow about not now and instead in the morning or something.
        1. %%()%%
1. oooook, singular homologies and their computation tools.
    1. disjoint sum of spaces → direct sum of homology groups!
        1. honestly trivial-ish?
        1. I'm....ok, maybe I should say explicitly that disjoint sum of spaces has the cycle group _obviously_ factor into direct sum and likewise for the boundary group
            1. for finite disjoint sums it's blatant, for infinite we should take care, but still: there's a fairly obvious isomorphism between group of disjoint sum and sum of components via "take the formal series, every element is an element of some component, done"
        1. now how to say "ofc Z⊕Z/B⊕B = Z/B ⊕ Z/B" and sound convincing.
        1. well the convincing argument is an isomorphism between the 2 canonical presentations of these 2 distinctly defined groups.
        1. a generic argument of the first factor is (z,z)±(b,b). of the second sum, (z±b, z±b). given that ± works componentwise, these extrapolate (z,z) into the exact same set I'm pretty sure. the group op obviously works the same after translation so yeah ok.
    1. reduced homology and that H₀ loses a ℤ in progress.
    1. that path-connected has H₀ = ℤ.
        1. I mean yeah? collapse the free abelian to 1 generator by equating them all.
    1. homologies of a point are H₀ = ℤ and Hₙ = 0. (and reduced are 0 everywhere.)
        1. well uh. singular, right. there's....exactly 1 map of anything higher into the point. its boundary is....uhhhh.
        1. for I, the boundary is 0, so it's in the kernel.
        1. for Δ², the boundary is in fact I because there's an odd # of faces.
        1. and so on; in odd dimensions Z = B and H = 0, in even dimensions Z = B = 0.
1. ow shit functoriality and homotopy invariance.
    1. that Hₙ is a functor......is annoying to think about. but I think we should.
    1. ok uh. functoriality.
        1. for f : X → Y there's an obvious chain map f♯ of singular complexes f♯ : CX → CY that postcomposes individual maps Δⁿ→X in the chain with f, into Δⁿ→Y.
        1. it's a chain map because boundary before and after postcompose is the same? sounds suspicious.

## review of the previous
1. ok so we read what exactly?
    1. (semi)simplicial complexes, homologies and start of singular.
1. outtakes?
    1. proper definition of a semisimplicial complex!
        1. it's a collection of maps Δⁿ → X.
        1. cond1: images of internals of maps are injective (iso), disjoint and cover X.
        1. cond2: restriction is a map
        1. cond3: subset is open iff all preimages are open.
    1. and also of a CW complex.
        1. disjoint collection of cells (internals)
        1. every cell equipped with charmap from a disk, which is iso on the internal
        1. C: every boundary is contained in finitely many lower-dim cells
        1. W: A is closed iff every intersection with cell-closures is closed
    1. and later, definitions of simplicial & singular homologies (which I skipped because surely I know _those_)
    1. and also some computations of simplicial homologies!
        1. disjoint unions go to direct sums fairly obviously
## Continue: functoriality and homotopy invariance
1. functoriality: see [[2025-01-13]]
2. homotopy invariance: 
    1. ok there're 3 points. definition of chain homotopy, homotopy → chain homotopy, chain homotopy → homology group iso.
    2. definition honestly falls out of homotopy → chain homotopy construction. (actually, I started doing it & forgot, but it sure did fall out.)
    
    3. homotopy → chain homotopy:
        1. (paper paper paper)
        2. OK UH.
        3. this is Nontrivial to define.
        4. but the idea is thus: we'll want to define an operator Prism^F : Σ(Δⁿ → X) → Σ(Δⁿ⁺¹ → Y).
            1. (there should be a notation for formal sums but I forgot so it's a Σ.)
            2. the way it's done is thus: first, we'll collapse the Σ monad at the end, so just reach for (Δⁿ → X) → Σ(Δⁿ⁺¹ → Y).
            3. then, do this: (Δⁿ → X) → (Δⁿ×I → X×I) (obvious) → (Δⁿ×I → Y) (by –;F) → Σ(Δⁿ⁺¹ → Y) (by cutting the prism into simplex-inclusions).
        5. we'll need to be careful w/ prism-cutting definitions so the signs align.
            1. rough sketch: think of the prism as having vertices 0..n–1 and 0'..n–1'. then take as simplices Σ_j=0..n–1. [0..j, j'..n–1']·(–1)ʲ.
            2. spot check: boundary will have +[0'..n–1'] & [0..n–1]·(–1)²ⁿ⁻¹ (n-1' is nth)
            3. every simplex has, in the boundary, [0..j–1,j'..n']·(–1)ʲ·(–1)ʲ (+) (j is jth) and –[0..j,j+1'..n'] (·(–1)ʲ·(–1)ʲ⁺¹, j' is j+1th). for j≠0,n–1 these compensate each other to 0.
            4. ....let's consider a generic k-face of a j-simplex and sum over j? where we removed either k or k'?

            5. the boundary of the j-simplex is, uhhhhh.
            6. %%()%%
        6. ------gods, fuck this, let's figure out chain homotopy → same group morphism and think about signs a little later.
    4. chain homotopy → identical H-maps
        1. for f–g = 0 (on H) we need (f–g)(z±b) = 0±b, or (f–g) z = ±b, or (f–g) Z ⊂ B.
        2. behold: (f–g) z | ∂z=0 = (∂P+P∂)z = ∂Pz ∈ B. as desired.
3. ok, overview....
    1. we do remember prisms in principle
    2. forgot but rederived exact form of chain homotopy
    3. fucking algebra, but I think I'll succeed eventually
    4. z±b notation is good, c|∂c=0 is good, "derive new forms, leave them be, plug in when suddenly useful" is surprisingly functional