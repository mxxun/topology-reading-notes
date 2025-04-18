# 25 Components and Local Connectedness

1. ok, connected components are cool!

1. Let's have a topological space X.
1. We'll define an equivalence relation ~; x ~ y iff there's a connected subspace containing both.
    1. Proof that this is an equivalence:
    1. reflexivity: {x} is connected
    1. symmetry: obvious from definition
    1. transitivity: subspace joining x ~ y and subspace joining y ~ z can be glued on y, and thereby join x ~ z.
    1. Done.
1. Theorem: those equivalence classes are connected, disjoint, union to X, and any connected subspace intersects exactly 1.
    1. disjoint and union to follows from equivalence relation.
    1. connected: any class is nonempty and so has an `x`; any other point `y` has a connected subspace joining x to y; unioning them all on x yields the whole class and its connectedness.
    1. any connected subspace intersects exactly 1: if it intersected 2, those 2 would be the same equivalence class.

1. Another: same, but path components.
1. equivalence relation proof:
    1. reflexive: constant path is a path
    1. symmetry: invert the path
    1. transitive: glue (paste) two paths from [0, 1] and [1, 2] together; they agree on the intersection (point) so their pasting is continuous.
1. same theorem for path components
    1. path-connected: any class is nonempty; any point is connected to a given one by a path; ergo, any 2 points are path-connected
    1. any path-connected subspace intersects exactly 1: well if it intersected 2 it'd make them the same 1 wouldn't it

1. Statement: eacho component is closed in X
    1. because its closure is also connected & so it must contain its closure & therefore must be closed.
    1. ....if there are finitely many components, then they're also all open, for obvious reasons
1. this is not generally true of path components.

1. Example 1: Q as a subspace of R
    1. any interval of it is splittable, only singletons are connected (and are closed but not open)
1. Example 2: topologist's sine:
    1. it's connected & so has 1 component
    1. it's said that the sine itself & the vertical are both path-connected, so, 2 path components
    1. V is closed and S is open?? (in S + V)
        1. yeah I can see V as closed; any point to the right has a tiny neighborhood not intersecting V
        1. conversely, S is not closed: any point of V has any neighborhood intersect its arbitrarily tight waves.
        1. ok.
    1. ....worse: let's remove all points of V whose y-coord is rational.
    1. Statement: this still has 1 component, and now, uncountably many path components.
        1. fucker
        1. ...ok, I think any attempt to split V on a rational point leads to all splitting sets  intersecting connected S and not being able to split it, so
        1. now, any 2 nonequal reals have a rational between them, so........path components of V have become points, of which there are indeed uncountably many.
        1. ok, _fine_

1. Other properties: local connectedness and path connectedness
    1. A space is locally connected at x if any neighborhood has a smaller neighborhood which is connected.
    1. locally path connected if any neighborhood has a smaller one which is path connected.
1. Examples: 
    1. intervals and rays of R are both of those.
        1. (...because we can cover any point w/ the basis, a tiny sphere, which is path connected.)
    1. [-1,1]–{0} is...not connected but locally path connected, I think?
        1. the textbook for some reason only states local connectedness not path connectedness, but w/e
    1. topologist's sine is connected but not locally
        1. I think points of V should violate local connectedness
        1. but, uh, tired atm, let's do this later
    1. Q is neither