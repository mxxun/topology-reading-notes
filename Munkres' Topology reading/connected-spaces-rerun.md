# Connected Spaces Rerun

1. We can have separations of spaces: whenever we can cut a space into 2 disjoint open subsets, we have a separation.
1. A space is connected if it has no separations.

1. Note that any clopen subset constitutes a separation, and vice versa.

1. There's another construction of connectedness for subsets:
    1. if we have 2 sets splitting the subspace, and neither contains limit points of another, we have a separation.
        1. separation -> that: separation is clopen and therefore does not contain limit points outside itself
        1. that -> separation: ....not contatining limit points wrt the subspace is sufficient condition to be closed, & we're done.

1. Examples of separations (and not)
    1. indiscrete topology on 2-point space: yeah there's no separation
    1. Let's have a [-1, 1]\{0}. it's separable along the 0.
    1. [-1,1] does not have a separation.
    1. Rationals are separable upon irrational points.
    1. if we take two curves in R², xy=1 and y=0, the subspace they form is separable because they do not intersect.
1. Lemmas:
    1. connected subspace lies entirely within one of the sets of a separation
    1. (or else restricting them to the subspace would constitute its separation)
1. union over connected subspaces that are "linked" is connected
    1. one format of linkage: have a point in common
    1. because, mm, separation of this union must have a point in 1 subspace & something else in the other, & something else must contain the point, so welp
1. adding limit points to a connected subspace leaves it connected
    1. hum, why again
        1. the subspace must lie in one of separation, so the other must contain limit points only
        1. ....and then other limit points _cannot exist_ because the subspace-containing half of separation must be closed wrt, and so cannot have limit points
    1. I'm playing too loose here, let's be more formal
        1. so let's have a connected subspace A and its extension with some of its limit points B
        1. reminder that a limit point of A is a point any neighbourhood of which intersects A
        1. and then we have a separation C|D of B
        1. now, A is connected and is in C, and D consists entirely of limit points of A
        1. in X, they have only neighbourhoods that intersect A; restricting them all to B does not change that fact
        1. so, any B-neighbourhood of a point of D intersects A, so D intersects C, absurd.
1. image of a connected is connected
    1. uh, if it wasn't, backprojecting the separation of the image would constitute a separation of the preimage
1. finite product of connected is connected
    1. we're unioning over cross-shaped sections drawn through every point
    2. Or more precisely:
        1. we have a product X×Y
        1. let's fix an x:X and iterate over y:Y.
        1. consider T-shaped spaces x×Y \cup X×y.
        1. every such space is connected because it's glued from two connected over the point (x,y)
        1. all of them contain (x, y0) (in the first component), so we can union over them and get a connected space.
        1. That union is the whole X×Y because any (x', y') is contained in the X×y component when y:=y'.
    1. ....this was a proof for binary products, but it extends intuitively for finite products.
1. Now, about infinite products.
    1. first: R^\omega in box topology.
        1. it is separable into C|D of bounded and unbounded    sequences
        1. the first is open as such: we take a side=2 cube around any point (which is open in box) and union those over bounded sequences.
        1. if we add ±1 to a bounded sequence, it stays bounded, so we only get bounded points, but get all bounded points. So.
        1. Likewise for unbounded. So.
    1. Second: R^\omega in product topology
        1. I think the first step is to do eventually 0 sequences, and then closure them into the whole R^\omega
        1. we do the first by unioning R^n×0 over the 0 as a common point
        1. then, it's enough to show that any point only has neighbourhoods that have an eventually-0 point
        1. Like so: take a neighbourhood; it has only finitely many finite dimensions and contains everything in the rest.
        1. "everything" includes 0, so this neighbourhood does contain eventually-0 sequences. Done.
1. Aaaaand done.

---

1. ok, exercises we skipped last time.
    1. 6, 8, 10, 11, 12.
1. 6:
    1. We have an A \subset X and C, connected subset of X.
    1. C intersects both A and its complement.
    1. Then it intersects its boundary.
    1. So: this is equivalently "C intersects, but is not contained in A"
    1. Note that Bd A is ~~the set of limit points of A.~~
        1. .......uh, remind me again if this is how it works
        1. ah, it's closure minus interior
        1. and equivalently closure intersected with Cl Co A
        1. so, set of limit points of both A and Co A, cool
    1. -----oh, hum, I have some idea about restricting A and complement to C itself.
    1. they can't be both closed, because that'd separate C.
    1. if one is not closed, then the other contains some of its limit points, and those are in closures of both (limit of the first, contained in the second)
    1. so, well, we're done!

1. 8: Is R^\omega connected in uniform topology?
    1. recall that it has as balls not-quite-cubes made of unioning cubes of all radii \delta < \epsilon
    1. (which excludes sequences whose limit is epsilon)
    1. (because the ball is in fact about sup over distances being < \epsilon)
    1. I think this is in fact sufficient to do the same trick as with box
    1. any bounded sequence is only close to bounded sequences; any unbound only to unbound ones
    1. And we're done here, huh
1. 10: arbitrary product is connected
    1. hints:
    1. we pick a point `a`
    1. we construct a family of subspaces X_K indexed by the finite subset of dimensions K; they're w/e on K-dimensions and `a` on everything else
    1. a) we show that X_K is compact.
        1. I think because it's isomorphic to K-indexed finite product of relevant Xs?
        1. ok, isomorphism is a bijection in which preimages of open sets are open
        1. bases are enough
        1. points are bijected as (tuple) <~> (tuple) ++ rest of `a`
        1. basis of finite product is: products of open sets
        1. basis of X_K is basis of teh whole X restricted to X_K, which is: finitely finite products
        1. which I think restricts to...well, the rest of `a` is the same in any of these, and the smallest they get is just the same finite product of open sets over K
        1. So I think we're good
    1. b) Union Y of all X_K is compact
        1. because they all contain `a`.
    1. c) closure of Y is the whole space, and so it's also compact.
        1. aka any point is a limit of Y, aka any point only has neighbourhoods intersecting Y
        1. well we pick a neighbourhood Z of any point z, and we pick K to have all finite dimensions of Z.
        1. then Z and X_K have in intersection point z' which has z's coordinates on K and `a`'s coordinates elsewhere
        1. it's in Z because it's in Z on all its finite coordinates, it's in X_K because it's `a` on all finite coords of X_K.
        1. there, done.
1. p: X -> Y is a quotient. all p^-1({y}) are connected and Y is connected. Goal: X is connected.
    1. Remind what's a quotient? ---mm, right, it's a map such that...it's surjective, and preimage of any neighbourhood of x intersects an open neighbourhood of every point in preimage of x.
    1. Equivalently it's a surjective map to the finest topology that allows that map to be continuous.
        1. (& therefore, any preimage of a neighbourhood of a glued point is open, and so is covered by neighbourhoods of component points of the glued point.)
        1. ---oh, and it has that property where...something something images are connected?
        1. not quite; whenever p^-1(U) is open, U is also open; this is probably good enough
    1. ok, our standard tools are: union over a point, closures, connected-is-inside-separation
    1. ok, so:
        1. we take a separation C|D of X
        1. every preimage of y, being connected, is contained in either C or D
        1. this lets us declare that C and D are preimages of a disjoint split E|F of Y; E and F are then open because quotient, and so form a separation of Y.
        1. absurd. Done.
1.  Let's have Y subset of X, both connected. Let's have A|B separate X–Y.
    1. Goal: Y \cup A and Y \cup B are connected.
    1. ...well, one of those is enough because symmetry.
    1. ok, obviously if Y \cup A is not connected then there's a separation of that, and C contains Y.
    1. ....I think there's something where...if Y \cup A wasn't connected, then we could use that to build a separation of X?
    1. like, if C contained Y then C | D \cup B would for some reason be a separation
    1. ...well, if those two were open or closed wrt X that'd be enough; do we have anything like that?
        1. Y is ?? wrt ??
        1. C and D are clopen wrt Y \cup A
        1. A and B are clopen wrt X – Y = A \cup B
        1. ....so, C does not have limit points of D or vice versa; if that was also true for C and B, then C and D \cup B would be clopen & we'd be good
        1. ...but this does not use Y at all, does it? yeah.
        1. ...well maybe in the construction of C not having limits of D?
        1. ok, can we have C and B not containing each other's limits.
        1. ....hmmmm. well, we could closure Y and get...somewhere...
    1. Huh. I'm stuck.
    1. ok, to heck w/ it, let's go on.