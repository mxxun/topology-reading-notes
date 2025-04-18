# 27 Compact Subspaces of Real Line

1. First big theorem: more general than I
    1. simply ordered & have least upper bound & order topology
    1. goal: any closed interval is compact
    1. everywhere we assume a < b & \mathcal A to be an open (internal to [a,b] in subspace) covering of it of which we are trying to construct a finite subcover
    
    1. Lemma 1: if x < b, then there's an y > x s.t. [x, y] is coverable by at most 2 sets of \mathcal A
        1. if x has a direct successor, we pick it to be y, [x,y] = {x, y}, & we're done
        1. if it doesn't, we pick any A around x; A....should contain some [x, c), then we choose an y in (x, c) & we're done
    1. Step 2: let's consider all points y>a s.t. [a, y] has a finite cover (by \mathcal A). call this C.
        1. it's nonempty because Lemma 1.
        1. then it has an upper bound c (because upper bound property).
    1. Step 3: c must also be in C.
        1. bascially: reach down from c by an A around it.
        1. A contains a (d, c].
        1. (d, c] contains e in C, or else d would be a smaller upper bound.
        1. then we can take a finite cover of [a,e], add A, and get a finite cover of [a, c].
    1. Step 4: c must be =b.
        1. or else there's a d above c s.t. [c, d] is covered by 2, so [a, d] is too covered finitely, so c could not be the upper bound.
1. I _think_ this is similar to our construction, but more general, & working by closure properties of the set of points whose downintervals are coverable, which is more elegant
    1. & I think this set is in fact definable, so it's a valid set to take
    1. but tbh I think defining this set as a fol-formula is nontrivial

1. ok, we'll need to review that later to not forget entirely
    1. & why not now, semi-immideately
    1. we define the set of points C whose downwards intervals have a finite cover built as a subcover \mathcal A
    1. by lub property it has a lub
    1. its lub must be inside the set because otherwise we can reach down by a neighbourhood around it, & then either it's not a lub, or there's a midpoint in that neighourhood that's in C, & then the lub has a cover through the cover of midpoint + that neighbourhood
    1. its lub must be the upper point, or else there will be a finitely coverable point above it (through the neighbourhood too)

1. corollary: every closed interval of R is in fact compact

1. Theorem: subspace of R^n is compact iff it's closed and bounded (in euclidean or in square metric)
    1. (euclidean and square metrics' boundedness are the sam thing by somewhat uncomplicated algebra)
    1. compact => closed and bounded
        1. closed because we're in Haus
        1. bounded because its finite covers by balls are bounded
    1. closed and bounded => compact
        1. a finite cube is compact as a product of intervals
        1. boundedness implies a cube containing the thing
        1. & then it's a closed subset of a compact, & so is compact itself
1. Examples
    1. spheres and balls are compact
    1. {(x, y) | xy=1, 0 < x <= 1} is closed but not bounded & so not compact
    1. topologist's sine (before closure) is bounded but not closed
    1. topologist's sine must be compact because closed _and_ bounded

1. Extreme value theorem!
    1. let f : X -> Y be from a compact X to ordered Y
    1. there are c and d s.t. for every x, f(c) <= f(x) <= f(d)
    1. .....or, simpler, there are points that are projected into strict inf and sup of the whole image
    1. I think first step is that image of compact is compact
    1. ...second is we explicitly state that our goal is m and M, smallest and largest elements of the image; then their preimages will have c and d etc.
    1. if there's no smallest element, there's a succession of ever-smaller elements
    1. then we can form a sequence of open rays that fail to cover the image finitely, & this contradicts compactness
    1. likewise for largest element
    1. cool!

1. 