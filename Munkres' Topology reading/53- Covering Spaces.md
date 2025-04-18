# 53: Covering Spaces

1. ...ok, let's take notes on covering spaces actually.
    1. concept of the covering space which we're currently rotating: every point has an evenly covered neigh.
    2. Example: identity.
    3. Example: ℝ → S¹.
2. note that we want connected covering spaces actually, because X×(discrete) always works.
3. local homeomorphism, in which each point of preimage has a neigh that's mapped homeomorphically!
    1. ----necessary but not sufficient for covering!
    2. example: ℝ⁺ → S¹, which...is not....evenly covered..?
        1. ...not evenly covered _at_ the spiral-starting-point, where indeed any neigh has a half-cover in the preimage.
    3. Example: connected cover for S¹ that's not ℝ: S¹ with winding 2! i.e. by complex map z ↦ z².
4. so....restriction of a covering map is not necessarily one also.
5. restriction on the base space works though:
    1. if p: E ↠ B & B₀ ⊂ B, then E₀ := p⁻¹(B₀) evenly covers B₀ by p.
    2. the proof is easy.
6. another thesis: a product of covering maps is a covering map!
    1. ok uh let's have p: E ↠ B & q: F ↠ C.
    2. an open in B×C is U×V, U in B & V in C.
    3. preimage of U×V by p×q is uh (U-slices)×(V-slices), right?
    4. & indeed a we can rearrange discrete-components into one and U- & V- components into U×V components, and....yeah, p×q certainly maps any of them to U×V....homeomorphically?
    5. I mean. yeah. just, fix indices Uᵢ × Vⱼ and see how p×q is a homeomorphism by assumption.
    6. .......therefore, for example, the plane ℝ² covers the torus T = S¹×S¹ by product-covering of ℝ→S¹.
    7. *Example:* restriction! take the torus & take the figure-eight out of it: the subset (S¹ × b₀) ∪ (b₀ × S¹). now take the restriction in ℝ². what do we get?
        1. A: preimage of b₀ is....ℤ? & so we get (ℝ × ℤ) ∪ (ℤ × ℝ), i.e......the grid.
    8. Example: consider S¹×ℝ₊ and cover it by ℝ×ℝ₊, by product of std. p:ℝ→S¹ & the identity cover i:ℝ₊→ℝ₊.
        1. & then we can remember that S¹×ℝ₊ is iso to a plane w/o a point, and observe the...covering of the plane-sans-point by the...open half-plane?
        2. & the picture of it is thus: ℝ→S¹ is a spiral, and ℝ₊ extends outwards from it, so we get a....thick spiral, whatsitscalled, screw, right.
        3. i.e. "the Riemann surface of the complex logarithm". OK!!
7. ...and that's the chapter, and exercises are upon us! huh.
    1. [x] if Y is discrete, then fst: X×Y → X is a covering.
        1. .......obviously????
        2. in fact _X_ is evenly covered here???
    2. [x] let p:E→B cont. and surj, U open in B & evenly covered. Thesis: if U is connected, then partition of p⁻¹(U) into slices is unique.
        1. if it is _not_ connected then it might well be that U ≅ U ⊔ U and uniqueness is fucked then.
        2. & what we mean by "unique" is: if we have 2 decomposition of p⁻¹(U) into slices, Vᵢ and Wⱼ, then....every Vᵢ is exactly some Wⱼ and vice versa.
        3. I think this is equivalent to "if Vᵢ & Wⱼ intersect, then they're equal". yeah sounds about right.
        4. ok, so let's suppose Vᵢ and Wⱼ intersect.
        5. we can obsereve that Vᵢ ∩ Wⱼ is also open in E, in themselves, & so in U.
        6. ......hm. how about: if Wⱼ – Vᵢ is nonempty & open, then its image = U – Vᵢ ∩ Wⱼ is also open, & that's a partition of U into 2 opens, which is no-go.
        7. welllll.......every point of Wⱼ is in exactly one Vₖ₍ⱼ₎. so, for any of these points, we can take Wⱼ ∩ Vₖ₍ⱼ₎ as a neigh disjoint from Vᵢ, and their union constitutes Wⱼ.
    2. --ok, to compress this:
        1. "partition is unique" means "for two partitions Vᵢ & Wⱼ, Vᵢ are all Wⱼ and conversely"
        2. & that's equivalent to "if Vᵢ & Wⱼ intersect then they're equal".
        3. & we'll do "if Vᵢ & Wⱼ intersect but Wⱼ–Vᵢ is nonempty then U is not connected".
        4. as so: Vᵢ ∩ Wⱼ is obviously open, so if Wⱼ–Vᵢ is nonempty open then images of these two in U are open & U is not connected.
        5. & then we'll make Wⱼ–Vᵢ open as a union of contained neighs of a w: each w lies in exactly one Vₖ, so Wⱼ∩Vₖ is a suitable neigh.
    3. [x] let p:E→B covering, B connected. if p⁻¹(b₀) has k elements at 1 point, it has k elements at any point.
        1. huh!
        2. hypothesis: if 2 points have nonequal multiplicities under p⁻¹, then their evenly covered neighs are disjoint....?
            1. because like....take their intersection. even covering over 1 point gives us n copies, & under other, m copies. which, what?
            2. ....technically possible as long as the intersection is not connected? & I think that's practically possible?
        3. & if that's true, then we can take a union of all k-points' neighs & a union of all others' neighs, & these are disjoint, & that's a separation of B.
        4. ...I think the key here is that _points_ have a fixed multiplicity. so if we have an n-point & and m-point & their evenly covered neighs intersect, then points in the intersection ought to have multiplicity n (from n-point preimage into n copies of Uₙ) but also of m (from m-point preimage into m copies of Uₘ). so....yeah.
    4. [x] let q:X→Y & r:Y→Z be covering. if r⁻¹(z) is finite at any z, then q;r is also a covering map.
        1. huh!!
        2. ok, so we need even coverings of neighs of points of Z.
        3. .....ahhhhh I see where finite comes from.
        4. we take the neigh U of z from r. that gives us finitely many (open) copies of U in Y. 
        5. now, for each copy of _z_, yᵢ, we want an i-uniform neigh Vᵢ over each of them that's evenly covered by q, because then r(Vᵢ) has Vᵢ as r-reimage, and q⁻¹(⋃ᵢ Vᵢ) is a p-even-covering of that, by adding up even coverings of Vᵢ, which are identical.
        6. we get this family of i-uniform neighs over yᵢ via taking their q-neighs Wᵢ, taking r(Wᵢ) (open, ofc), intersecting them all & U, and projecting back to Y. these Vᵢ are then all contained in r⁻¹(U) and are a preimage of an open set U' in Z.
        7. then Vᵢ are an even cover of U' (wrt r), & ⋃ᵢ q⁻¹(Vᵢ) is an even cover of U' wrt q;r: slices are ofc disjoint, & slices are all iso first to Vᵢ (being subslices of even coverings of yᵢ) & then to U'.
    5. [x] z ↦ zⁿ is a covering map.
        1. I mean like...
        2. a typical point in S¹ has a small interval as a neigh. its preimage under zⁿ is...n copies of n×-shorter intervals. & there you go.
    5. [x] .........could we....meditate on how covering maps are actually _useful,_ here?
        1. well.....knowing of path-lifting and homotopy-lifting properties, we could say that any loop (i.e. path) has a semi-unique lifting..to any covering space, right? and homotopies between them lift also.
        2. the question remains though: how do we a. enumerate all the loop classes, b. show they're not homotopic?
        3. ....hmmm.
        4. it seems...unarguably true that if 2 loops uniquely lift to 2 paths w/ distinct endpoint, then there....cannot be a lifted homotopy between them? because homotopies _do_ lift, but a lifted homotopy would not be one by virtue of not having a fixed endpoint.
        5. so that....actually gives us a method of both generating novel non-homotopic loops & showing that loops are not homotopic.
        6. ...in fact, even the zⁿ maps give us many distinct loops in S¹? you wrap the circle on itself 0..n-1 times, & preimage of that path under zⁿ is a path ending @ 2π · i/n. so none of them are homotopic, & so the base single-wrapping loop generates a free subgroup ℤ of π₁(S¹).
    5. [ ] ok, & is there a way to then eliminate all the other possibilities of loops?
        1. maybe if we have a way to project _homotopies_ in E back to B?
        2. ....wait. homotopies already project, by postcomposition, right?
        3. the whole point is _constructing_ them.
        4. so if E is a space in which it's really easy to construct homotopies — e.g. _contractible_ — then there we go, preimages of b₀ will enumerate distinct loops of B, loops lifting to b₁≠b₂ won't be homotopic because a homotopy wouldn't be able to lift, and bᵢ produces exactly one loop because all loops lifting there are homotopic in E.
        5. wow. ok.
    6. [ ] ....I don't actually want to lift properties of B to E. maybe later.