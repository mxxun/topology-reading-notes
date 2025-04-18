# 23: connected spaces

1. A separation of a space is a disjoint split of a space into 2 (nontrivial) open sets.
1. A space is called connected if it cannot be separated.
1. ....another surprisingly obvious equivalent: space is separated iff it has no nontrivial clopen sets.

1. About subspaces:
    1. if we're in a subspace Y of X, its separation is a split into two (nontrivial) _sets_ which do not contain each other's limits.
    1. The implication being that if they contain each other's limits they will not be both open in Y, and if they're both open in Y, they will not contain each other's limits?
    1. Oh, a good hint: if two sets are a separation, they're both clopen! (in Y)
    1. so they both contain their own limits (in Y), and so cannot contain limits of another.
    1. Um. Let's maybe try this again.
        1. Suppose Y is a subspace of X, and A and B are a separation of Y.
        1. Then they're both clopen in Y.
        1. Then (...using hints...) A contains all its limit points that are in Y. And B cannot contain them, because disjoint.
        1. All other limit points of A B cannot contain because they're outside of Y, actually. Ok, cool.
    1. Conversely, suppose A and B are disjoint and form Y and do not contain each other's limits.
    1. Then any limit of A is either inside Y and then inside A, or outside of Y. Then A is closed in Y, and so is B, and voila.
1. Examples from 2 perspectives: disjoint-open and do-not-contain-limits wrt superset.
    1. two points in indiscrete: yeah, nothing to split here
    1. [-1, 0) \cup (0, +1]
        1. those two halfs are open wrt the subset, so
        1. conversely, they do not in fact contain each other's limit points (-1, 0, 0, 1)
    1. [-1, 1] and any point splitting it into [] and (]
        1. the first will not be open
        1. and first will have the limit of the second
    1. Rationals I'll steal because it's very memorable: we can split any rational interval upon an irrational point in it into two _open_ sets not containing the irrational point
    1. subspace of R²: rightmost part of xy=1, and also the line y=0.
        1. neither contains a limit of another, huh?
        1. I suppose only limits of either line are points of that line itself?
        1. .....which is the same thing as "they're closed" which directly implies not-connectedness of a subset made of them both.
1. Lemmas about connections.
    1. if C and D separate X, and Y \subset X is connected, then Y is entirely in one of these.
        1. Well suppose it isn't.
        1. Then we cut it apart by C and D, and voila, they also form its separation.
    1. union of connected subspaces that share a point is connected.
        1. _huh._
        1. ok, suppose it isn't!
        1. so we need to cut it apart.
        1. the point will be in exactly one of separating sets.
        1. then some subspace of the union will be cut apart by separating sets, because the point will be in 1, and some other parts of the set in 2, because 2 is nonempty & intersects _something_ in the union
        1. separating sets are open, so they'll cut that subspace into open subsets, so yeah.
        1. Adjunction: This can in fact be stacked; if we have a chain of connected open sets linked to the next by a point, then that is also enough for connectedness
            1. trivially in finite case
            1. in infinite case we sort linking points into separating sets
            1. then we sort sets by whether their linking points are entirely in 1, 2, or some are in either
            1. if some subset is in either, it's cut apart & we're done
            1. if all sets' linking points are in 1, then, uh, we find a set intersecting 2 and we're done
    1. adjoining limit points to a connected subspace leaves it connected
        1. Hum!
        1. ok, suppose there's a separation given some adjoined points.
        1. restricting it back to the original set must leave it a non-sepearation, so at least one set should consist of adjoined limits entirely.
        1. then the other is closed wrt the superset & contains A, & so closure of A is in the other, so the first is empty. Done.
        1. ----even easier; A is connected & so should lie in one of them entirely by the lemma above.
    1. image of a connected space is connected (assuming continuity)
        1. if it isn't then preimaging the separation gives us a separation of the original space.
    1. Finite cartesian product of connected spaces is connected.
        1. Well, binary product should be enough.
        1. I....think there should be something about projections? if we have a separation of the product, won't we have a separation of either one under projection?
        1. ...they're doing something weird but cool: they union, pointwise, X- and Y-shaped slices through the space. (a, b) ~> X×b \cup a×Y. both of those are connected by isomorphism to X and Y, their union is connected by lemma (they have plenty of common points), and union of everything, X×Y itself, is again connected by lemma.
    1. Apparently, arbitrary product of connected is connected!
        1. Construction for R^\omega:
        1. first do all finite restrictions to a particular point, e. g. 0. So, R×0[1..], R²×0[2..], etc.
        1. Their union of eventually-that-point sequences is connected because they have the point in common.
        1. Then you show that closure of this union is the whole set.
        1. how: you pick arbitrary basis around arbitrary point, then observe that it's finite in only finitely many dimensions, then pick an R^n such that this cobox is infinite in nth and everything above. this cobox intersects R^n at point[..n]×origin[n..].
            1. (so, any open neighbourhood of the point intersects the R^∞, and so it's in the closure.)
    1. But R^\omega under box isn't.
        1. demonstration: bounded and unbounded sequences are a separation
        1. a cube around an unbound sequence is made of unbound sequences, and likewise for bound
        1. so unions of those boxes are open, so "all bound sequences" is open, and etc.

1. Exercises!
    1. 1: connectedness in a finer topology implies connectedness in a coarser, because coarsing _removes_ possible separations.
    1. 2: A chain of connected subspaced w/ nonempty intersection of adjacent is connected when union'd: we did that above!
    1. 3: same but they're linked through a single connected subspace: ....well, duh? I mean: 
        1. pick a separation; A goes into one, some A' into another; they cannot intersect and yet they must, a contradiction.
    1. 4: infinite sets are connected in finite complement.
        1. you see, intersection of two open sets in finite-complement can't actually be _empty._
    1. 5: totally disconnected: only connected subspaces are one-point sets.
        1. discrete are totally disconnected.
            1. Well, duh! whenever there are at least two points, we have a separation into one point and everything else.
        1. Q: if a space is totally disconnected, is it discrete?
            1. so, any 2-point subspace is disconnected.
            1. so any 2 points have disjoint open neighbourhoods. that's merely half of hausdorffity, not discreteness.
            1. ok, let's phrase it again: can we have a separation for any subset, but not open singleton for every point?
            1. .....I don;t see why not so let's try to construct an example.
            1. if we're in 2-point topology, then disconnection does imply discreteness.
            1. if we're in 3-point, then the full set is cleavable & so one of the points has an open singleton & two others have an open around them
                1. we need the rest 2-point to be disconnected, & withing 3-point this is achieavable through...some not necessarily open wrt 3-point open sets, but they will be open wrt 2-point
                1. & as we know the only way to have disconnected 2-point is to have it discrete, so we get discrete again
            1. Ok, so any _finite_ disconnected space is discrete; let's go for infinites
            1. ....oh right Q is totally disconnected but not discrete! any interval can be cleaved by a point inside-not-inside it, but single points are not in fact open.
    1. 6: let's have a subset A and connected subspace C of X. Assume that C intersects both A and not-A. Goal: C intersects boundary of A, aka its limits.
        1. 
    1. 7: Is R_l connected?
        1. In which [a, b) are open
        1. Nope, any [a, b) can be split into [a, c) \cup [c, b), both open
        1. ....that's an answer to a different question
        1. But it can also be split into (-∞, a) \cup [a, +∞), so
    1. 8: is R^\omega connected in uniform topology?
        1. I'm guessing not for the same reasons as in box, but might need to check boxes carefully
    1. 9: X and Y are connected, A and B are their proper subsets. X×Y – A×B is connected.
        1. I'm thinking we take the union of T-shaped subspaces over (X–A)×(Y–B).
        1. ....and, after drawing an image, I think this in fact should be enough.
    1. 10: arbitrary products of connected spaces
        1. well, it's basically laid out for us, isn't it?
    1. 11: about quotient maps, later
    1. 12: let Y be a connected subspace of connected X. Let A and B separate X–Y; then, Y \cup A and Y \cup B must be connected.
        1. we can note that Y \cup A is closed and not open.
        1. 


---

1. Note: I notice that navigating this subtheory of topology requires slightly different subskills / microhammers / mental motions. I think? Maybe?

1. Another note: this is in fact much less boring that metrics! Or maybe I'm in a better mood & slightly more willing to cheat and babble. But nothing ever matters, onwards!