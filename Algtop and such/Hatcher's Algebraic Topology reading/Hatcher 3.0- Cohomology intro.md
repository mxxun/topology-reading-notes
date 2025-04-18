# Hatcher 3.0: Cohomology intro

## meta
1. first log from around 2024-09
1. extracted from [[Hatcher's Algebraic Topology reading meta]]

## log of the first-ish readthrough
1. sketch: cohomology groups are _basically_ just homology groups of Hom-iszed chain complexes
    1. i.e. by taking Hom(—, X) you convert the descending chain complex w/ ∂ₙ: Cₙ → Cₙ₋₁ into the ascending chain complex
2. some motivation: there's a natural Hᵢ×Hⱼ → Hᵢ₊ⱼ(X×X), but if we wanted to go → Hᵢ₊ⱼ(X) after that, we'd need a map X×X → X to induce it, and the only obvious natural maps (projections) are boring.
    1. however, if we change the variance, we'd need a map X → X×X, and by taking the diagonal map we get something interesting!
    2. and that's gonna be the cup product, which is said to be "considerably more subtle than the additive structure" and make homology groups into a ring.
3. (and then there're also "cohomology operations", which are not gonna be discussed for a while, but provide a structure of a module over a complicated ring.)

4. Example:
    1. let's consider a graph. label vertices by elements of G, and we get C⁰ = V → G.
        1. ---actually, C⁰ = C₀ → G, C₀ being Free(V), so that we can map chains of vertices.
    2. label edges by the coboundary operator δ : C⁰ → C¹ := λ(f: V→G) (e: E) → f (∂ e), and there you go, a boundary map C⁰ → C¹.
    3. microexercise: figure out cohomology groups here.
        1. we have an chain complex 0 → C⁰ → C¹ → 0.
        2. H⁰ = ker δ / im 0 = ker δ. uh, 0 of C¹ is the const-0 map e ↦ 0. which mappings of vertices f go to a const-0 map?
        3. well, obviously any edge should connect identically-labeled vertices. so, any map that assigns labels on a connected-component basis is a cohomology class. I think that's it?
        4. yeah, the textbook agrees. and also notices that the group structure there is Gⁿ, where n counts connected components.
        5. what about H¹? it's C¹/ im δ, and the latter is..not obvious.
        6. hint: when would it be trivial?
        7. hmm. when any map of edges is achievable as a coboundary.
            1. I think it's gonna deal w/ loops in the graph? let's consider simple examples.
            2. 1 edge: easy
            3. a tree of edges: easy
            4. 2 edges: no go! indeed it'd be G×G/(x,-x), which is, uh, (g,h) ~ (g+h, 0), and I _think_ this is iso to G by sending [(g, 0)] ⟺ g? yea sounds right.
            5. and the same thing goes for same-direction edges, and also for any additional loop.
            6. so. H⁰ counts connected components, and H¹ kinda-counts cycles??
            7. sick!
5. ok, next: from graphs which are 1-dim Δ-complexes to 2-dim Δ-complexes.
    1. now we also have C² = G^(faces), and δ : C¹ → C² by (f: G^E) ↦ λ [v₀, v₁, v₂] → f [v₁, v₂] - f [v₀, v₂] + f [v₀, v₁].
    2. their meditations on the intuitive meaning of δ ψ:
        1. measures to what extent ψ is not additive, i.e. how much it fails ψ [a, c] = ψ [a, b] + ψ [b, c]
        2. if δ ϕ = ψ, then δ ψ = 0, so the actual value of δ ψ is...an obstruction? to solving δ ϕ = ψ, i.e. to surjectivity of im δ¹.
        3. they say that δ ψ is a..local obstruction? in that if δ ψ = 0 smh, that only means it's in ker δ, not that it's in im δ.
            1. they also say local because it "only depends on values of ψ within individual 2-simplices"
    3. geometric intrerpretation of δ ψ = 0 for ℤ/2:
        1. means every simplex has 0 or 2 1-edges
        2. & then we can connect these edges by a curve in the simplex, and from there produce a collection of disjoint curves that intersect exactly 1-edges
        3. and also, the 2 regions ~within and ~without the curves have identically-valued vertices, 0 in one and 1 in the other. huh.
    4. and for ℤ, we can do a curve touching-point per unit of value of the edge. and end up with...level curves!! huh!!