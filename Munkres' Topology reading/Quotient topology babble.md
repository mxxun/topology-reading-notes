# Quotient topology babble

_(About: quotient topology, a little bit of cattheory that someone definitely developed elsewhere)_

So, suppose we have three sets: the main one X, its subset S, and its quotient Q, containing as points/objects equivalence classes of some partition of X. (In the name of intuition, I'll pretend that Q _is_ X with some subsets glued into a single point each, and other points left untouched.)

There're natural/associated functions S -> X -> Q; injection/inclusion that maps points of the subset into themselves in the original, and surjection/?? (quotient?) that maps points of X into their equivalence classes (glued points get mapped into their resulting agglomeration, unglued points into themselves).

Now let's lift this picture from the category of sets to the category of topological spaces.

Let X have a topology T; some collection of its subsets that are called "open", among them empty subset and X itself, closed under finite intersections and arbitrary unions. Then, what topologies should S and Q have? Let's look at "natural" constraints for them possibilities.

Arrows of Top are "just" functions between underlying spaces, except they need to be continuous — preimages of open sets of destination topology must be open in the source topology. We'd rather have the same inclusion/quotient functions between sets to act as arrows S -> X -> Q in Top; this requires topologies of S and Q to be compatible with their continuity.

In particular, any preimage of an open set of X under the inclusion function must be open; such preimages are just those subsets of X intersected by/restricted to S, so a desired topology on S must have at least all of these.

To specify possible open sets of Q, an equivalent definition of continuity is useful: f : X -> Q is continuous iff for any point x and open subset V of Q containing f(x), there's an open subset U of X containing x s.t. f(U) is contained in V. Or, plainer, whatever the open subset V we project a point into, there should be an open neighbourhood of that point that projects into V.

For subsets of Q that it shares with X — consisting entirely of unglued points — we can see that to be open in Q they must also be open in X. Indeed, for every point of such an open subset U of Q, there must exisst an open neighbourhood of this point in X that fits into U. Taking a union over those, we acquire no less and no more than U itself, and as a union of open subsets of X it must be open in X.

