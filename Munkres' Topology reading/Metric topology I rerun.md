# Metric topology I rerun

1. ok, so: metrics
    1. d(x,x) = 0, positively defined, symmetric, triangle
    1. aka d x y + d y z <= d x z
1. balls around the point
1. epsilon-balls, for all epsilon, define a topology
    1. I'll ignore the proof because I did it before
1. metrization of topologies
    1. there's Urysohn's theorem but eh
    1. there're metrizations of $\R^n$ and $\R^\omega$
1. Bounded sets
    1. I'd say offhand "coverable by balls", but "distance within the set is bounded" is equivalent
    1. Diameter: the sup of that
1. standard bounded metric
    1. in which we rebuild the metric to become 1 above 1
    1. equivalently, we metaphorically remove all balls above d>1; they become the whole set
    1. properly one should check that it's still a metric but I'm somewhat bored by that
    1. .....ok, so triangle is the only nontrivial, & I think I did check that earlier
    1. (note that this induces the same topology)
1. ok, metrization of R^n
    1. euclideanly
    1. or rectangularly
    1. or octagonally
    1. so w/_e_
1. metric comparison lemma:
    1. if one induced topology is finer, then its metric produces smaller balls; for any point & any diameter of a ball in the coarser metric, there's a smaller (included) ball in the finer
1. Same, but for $\R^\omega$
    1. as a matter of fact, distance is not required to converge anymore
    1. however, we can do bounded square, & that _is_ guaranteed to have a sup
    1. which produces a uniform topology, whih is, surprisingly, finer than product and coarser than box
1. ok, let's attempt to figure things about this topology
    1. ---actually, zeroth of all, how is the distance computed again
        1. we go over coords, take absolute difference, bound it by 1, take sup over all that
    1. then what are balls here
        1. epsilon-ball has all dimensions less than epsilon, and is cubical
    1. ....aha, right, you can't do that in product, in product you can only do balls that are finitely finte, & this one is infinitely finite
    1. and a thing you can do in product but not here is hilbert's, because....
    1. ...because it can contain no cube, right.
1. .....and that's it? huh.