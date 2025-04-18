# 24: connected subspaces of the real line

1. let's have an order with LUB (all lubs exist) and all intermediates (any x < y have an x < z < y)
    1. We'll call these *linear continuums*

1. Theorem: linear continua in order topology are connected; likewise, their intervals and rays.
    1. I think lower rays and intervals do not have exactly one upper bound? for sequences converging to their, well, upper bound.
        1. ....actually, those don't count, I think; all subsets of an interval _bounded wrt interval_ have a lub.
    1. But anyway.
    1. They recurse into "any convex subset of a linear continuum is connected"
        1. which means: for any a, b it contains, it also contains [a,b] entirely
    1. OK, let's assume we have a separation A + B of a convex subset of a line X.
    1. We can pick a pair of points from each half & have an interval of those lie in X.
    1. let's form a set of points in [a,b] that are in A. it has a lub, let's call it c.
    1. either A or B contain C. 
    1. ---hint: restriction of A and B to [a,b] separates [a,b] itself. cool.
    1. hint: all previous steps were the right direction!
    1. ok, so the goal now is to forbid c from being in either.
    1. ---we can union A_0 w/ (a, c) and get an open [a, c]. [a, c] + (c, b] constitutes a separation, so it's enough to refute that.
    1. ----and, oh, right, [a,c] cannot be open because it's not strictcoverable because any open basis containing c would also contain epsilon above c.
    1. ok, now let's assume B has c.
    1. I...think...there should be a way to get to "[b,c] is open" but I don't see how yet.
    1. ---(hint) oh, there's a thing where c should be coverable by a (d, c]. In any case, d is a smaller upper bound on A, so we have a contradiction.
1. ok, there it goes.
1. Intermediate value theorem: later

1. Definition: path connectedness
    1. a path p : x ~> y is a continuous function from I to X, starting at x and ending at y.
    1. a space is path connected if there's a path between any two points of it.
1. Lemma: all path connected spaces are connected
    1. I think the path itself is connected by some lemma, & therefore must lie inside a separation, but cannot because we chose its points to be on different sides of the separation

1. I should do examples, probably

---

1. Exercises!
    1. (0,1), (0, 1] and [0, 1] are not homeomorphic
        1. because, lemme guess, removing any point from the first makes it unconnected, removing a point from second either makes it unconnected or makes it into the first, and ditto for the third?
    1. two spaces may be imbeddable and yet not homeomorphic
        1. I and R, e.g.
    1. R^n and R are not homeomorphic
        1. removing a point from R makes it unconnected, from R^n, not so much.
    1. 2: let's project a circle into the line. there's a point of the circle that projects into the same point as its opposite.
        1. well, one thing I know is that removing any point from the circle does not make it unconnected.
        1. ---oh hey, let's make a continuous map that first maps the circle into opposites pointwise (rotating by \pi is continuous) and then applies f.
        1. 