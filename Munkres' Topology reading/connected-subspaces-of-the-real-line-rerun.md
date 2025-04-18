# Connected Subspaces of the Real Line Rerun

1. ok, so we'll be proving that R and its intervals and rays are connected.
    1. ...honestly, any one of these is enough because isomorphism.
1. & then we'll also have path connectedness and balls in euclidean metrics.

1. ok, so we start from linear continua
    1. they're simple orders
    1. they have LUBs: whenever a subset has an upper bound, it also has a _least_ upper bound.
    1. any two nonequal elements have an intermediate element
1. & then there's a theorem: any linear continuum in order topology is connected; intervals and rays within it likewise.
    1. (ok, here do not have isomorphism, so this is additionally useful.)
    1. ok, so, suppose a linear continuum is separated.
    1. so there're disjoint clopen C|D.
    1. I'm....fairly sure that at least one of them must have an upper bound?
    1. ...ok, not obvious how to do that.
    1. we'll go slightly easier & pick a point in either, and have an interval [a, b]. it's closed, so restricting C|D to it leaves them closed, so it's also separated.
    1. Now, it's bounded, so restrictions are bounded. ...let's say that D' contains b, and call the lub of C' x. dunno if x ≠ b yet.
    1. 2 ways: x may be in C' or in D'.
    1. ....I think the thing we want from linear continua is the fact that singletons cannot be open, or something like that.
        1. Lemma: that. suppose a singleton {x} is open. then it's strictcovered by basis sets. then there's a (a, b) entirely contained in {x}. if a >= x or b <= x that's impossible, so a < x < b. by linear continuum there's a < c < d < b. now, c and d must be in x, and yet unequal to x, which doesn't work.
        1. ...note that [a, b] is also a linear continuum, I'm fairly sure.
    1. ---oh, I think the thing is that x is limit of both, and so they can't be both closed
    1. if x is in C', then it's particularly obvious that any neighbourhood of x has _something_ above x, and that something is in D', so x is a limit of D'
        1. linear continuum guarantees us that something, actually; as long as c < x < d, there's a x < e < d, and that e is our something.
    1. now, indeed, x also has something below it, but it's not obviously guaranteed to be in C', we need to pick at it.
        1. so suppose there's a neighbourhood (c,d) of x disjoint from C'.
        1. then I'm fairly sure all of C' is < c, and c≠x is an upper bound of C', contradicting the assumption that x is the lub.
        1. ...there, done. huh.
    1. ......I did not catch all corner cases. let's try that again and more formally now.
    
    1. ok, we have disjoint clopen nonempty A|B separating L.
    1. by nonemptiness we pick a and b from them, by disjointness they're nonequal, by WLOG a < b.
    1. we restrict A|B to [a, b]. they're nonempty because they contain a and b respectively. they're open by restriction. they're disjoint because they were disjoint. they...do constitute a separation.
    1. we pick c = sup A'. it exists because [a, b] is a linear continuum.
    1. split.
    1. c is in B:
        1. then c ≠ a, but it can be intermediate point, or it can be b.
        1. in any case, it is not a limit of A. 
        1. so it has a neighbourhood disjoint from A.
        1. then....it seems obvious that there's a point below c that's a ub of A, and we have a contradiction, but for some reason the textbook is verbose about it. w/e.
    1. c is in A:
        1. then, again, there's a neighbourhood around c, contained in A, not intersecting B
        1. and a point above c that's in A, which contradicts the assumption that it's a sup.

1. ok, so any linear continuum is connected.
    1. corollary: any interval or ray (closed or open) of a linear continuum is connected, itself being a linear continuum.
    1. corollary: R is connected.

1. Generalized intermediate value:
    1. suppose we have a continuous f: X -> Y; X is connected and Y is ordered w/ order topology.
    1. suppose there's an r between f(a) and f(b).
    1. then there's a c s.t. r = f(c).
    1. ...I want to split Y into (, c) and (c, ), backproject them, and observe a separation
    1. ....yeah that's it that's the theorem.

1. Ordered square, a linear continuum that's not R.
    1. I...dunno, lub seems obvious...
    1. but intermediate doesn't& there're no intemediates between—oh, right, there's no such thing as adjacent points
    1. ok, that works then; if two points are on a vertical then there's an intermediate because R-interval
    1. if two points are not on a vertical, then there's an intermediate point horizontally between them
    1. ok, "obvious" probably means "I have no idea how to prove it", so let's try babbling at it (or take notes from the textbook, that's fair too).
    1. any set having _an_ upper bound has _least_ upper bound.
    1. ----ah, they seem to, indeed, to that "obvious" formally
    1. aka: first we consider the supremum of the first (more important) coord.
    1. if there's a point w/ supreme first coord b, then the set intersects b×I, and within that intersection has a lub b×c (because I has lubs), and then b×c will in fact be the lub of the whole set A.
    1. if A does not have points in b×I, then b×0 is its lub; it an ub because it's bigger the the whole A and it's least because any other point would have first coord < b and then A will have points w/ bigger first coord. Done.
1. Example 2: in general, if X is well-ordered then X×[0, 1) is a linear continuum.
    1. Q: what's well-ordered again?
        1. A: ordered, and any subset has a minimum. ..contains its minimum?
    1. ok, lub similarly to the square?
        1. ....but we don't have sup available. that's a bit awkward. ....ok, let's try anyway.
    1. Let's have a set A.
    1. the set of points of X that are > A has a minimum. ....no wait that's not quite right.
    1. Let's project A onto the first coord. _this_ is a subset of X; let's call it A'. X has elements that are > X; _this_ set has a minimum. let's call it b.
    1. A' can contain b or not.
    1. if it does, then we'll intersect X w/ b×[0, 1). if this intersection is bounded, then there's a lub there. if it's not, then (succ b)×0 is.
    1. if A' does not contain b, then b×0 is the lub of X.

1. All right; path connectedness definition.
    1. I'm thinking there should be a continuous map f : I -> X for any two points x, y, mapping 0 to x and 1 to y?
    1. and a path between 2 points is one such map.
1. From path-connectedness connectedness follows: if there's a separation, then 2 points in disjoint sets have a path, and that path is connected, a contradiction.
1. unit ball in R^n is path connected?
    1. ....ah, _unit_ _ball_ centered @ 0 w/ radius 1, not balls in general (although those too, by analogy)
    1. ....well, they use direct paths.
    1. honestly I'd do 2 paths from the center to the point (which is trivially guaranteed, in any pseudoeuclidean metric, to be contain in the ball), and then I'd project first half of I to the first and second to the second
1. ok; punctured euclidean space, R^n–{0}.
    1. path connected above n=1; if 2 points are connected straight you connect them straight; if 2 points are connected through 0 you take a plane and connect in 2 jumps
    1. the unit sphere S^n-1; points of R^n w/ norm 1.
    1. ......because it's a quotient of punctured euclidean under x/||x||.
    1. it's surjective: yes
    1. it's continuous:
        1. restriction of an open ball to the sphere is, uh, section of the sphere
        1. preimage of that is...an open cone from the origin to this section
        1. it's intuitively open?
        1. covered approximately like:
        1. you pick a point in the cone
        1. you find corresponding point in the section
        1. you pick a ball covering it
        1. you move tha ball to the point of the cone, contracting it if necessary
        1. ...you're done, basically
    1. ...then we have a lemma that image of path-connected space is path-connected
        1. well, we pick 2 points in the last space (image), we preimage them (nonempty because image), we pick a point in preimage of either
        1. there's a map from I to these 2; composing it w/ the given map gives us a map from I to the desired 2 points, done
    1. Ordered square is ordered (proven earlier) but not path connected
    1. ....oh, we used intermediate value to observe that the path between 2 points must in fact contain all points between them, huh, cool
    1. suppose it is, & we have a continuous function I -> ((a, b), (c, d)) where a < c
    1. ......they do something surprising; the construct an injection of I into Q
    1. ok, so they path-connect the whole square, from 0×0 to 0×1
    1. then, every vertical interval is backprojected into an open subset of I. .....nonintersecting, I assume. ...yes, because they're preimages of nonintersecting; cool.
    1. then we can pick a rational in every such interval, and thereby embed I into rationals. which is supposed to be impossible. So there.
    1. (and that's impossible by countability; rationals are countable, I is not.)
    1. (and I is uncountable by diagonalization: we list all counted reals and construct a real that's different in ith digit from any of them, and that's still a real, so we're fucked.)
    1. (why is this in fact a real? fuck if I know.)
    1. (I think because we construct a sequence of rational upper and lower bounds on the thing; when we pick the next digit, we effectively say that it is to be >= than rational w/ that digit and <= than same but + 10^-i.)
    1. (and reals by axioms must have limits to these, and so there's a real that's squeezed between these two sequences, and then it is indeed not equal to any of enumerated rationals.)
    1. (cool.)
1. Example 7: let's have a topologist's sine curve; x×sin(1/x) for x in (0, 1].
    1. ...(0, 1] is connected, 1/x is continuous on it, sin is continuous on (0, ∞), so we have a connected space.
    1. .....its closure is also connected. huh.
    1. I assume the closure contains the whole vertical interval 0×[-1, +1]? because the sine vibrates arbitrarily tightly to it?
    1. let's observe that it's not path connected.
    1. well suppose it is! and that there's a map from I to it, starting from 0 and ending somewhere to the left.
    1. ....it can vibrate along the vertical line, but 0×[-1, 1] is closed in R², and therefore in the topologist's sine, and therefore its preimage is closed, and therefore the set of points of I projecting into the vertical is _also_ closed, ...and so it has a maximum. (...? but fine I guess)
    1. then we can restrict f to _start_ from that maximum, so there's exactly 1 point in I that's on the vertical, the first one.
    1. ---actually, let's say that we have time.
    1. the image of t=0 has x-coord 0; the image of t>0 has x>0 and y=sin(1/x) because that is where we're mapping.
    1. then we're gonna construct a sequence of time points that has 0 as a limit, whose y-coords oscillate between ±1; then...f cannot be continuous because continuous functions preserve limits, I'm fairly sure.
    1. well, _that's_ easy.
    1. ....ok, let's recap.
    1. First we find preimage of 0×[-1, 1] closed, and pick a maximum in it, and make I start at the maximum.
    1. Then we decalre that I = [0, 1] actually, and construct a sequence of ever-smaller points of I whose y-coord is ±1.
    1. These points must converge to something @ 0, but they cannot, therefore, f cannot be continuous.

1. ok, exercises from 2 onwards.

1. Exercise 2.
    1. there's a map from a circle to R, continuous.
    1. There's a point x of circle s.t. f(x) = f(–x).
    1. hmmmmmmm.
    1. I think I want to start from something intermediate, like the fact that any point beside min and max has at least 2 in preimage
    1. or maybe not
    1. there's that thing where R is in the order, and so intermediate value applies
    1. moreover, it applies to any closed sector of S^1
    1. so let's cut the circle in two by the x=0 line; intermediate value applies to both halves, so both upper and lower semicircle map onto the (a, b) (although maybe not exclusively onto it)
    1. .....if they were monotonous that'd be easy, but, nope, continuous only
    1. ----although actually, y'know, mmmm, 
    1. how about we map from I to either semicircle, clockwise both times, and then to R
    1. And then construct a function that's "second minus first"
    1. if this function is 0 at the start, we have our pair
    1. otherwise it starts at (b-a) and ends at (a-b) and so by intermediate has value 0 somewhere, and that somewhere is exactly the two opposite points of a circle which we mapped to each other
    1. splendid~
1. All right! 3.
    1. let's have f: [0, 1] -> [0, 1].
    1. Goal: It has a fixed point x = f(x).
    1. Like so: `id` is a continuous function; g = f(x)–x is also one.
    1. observe that g(0) = f(0) >= 0, and g(1) = f(1)–1 <= 0.
    1. As long as they're not equal, we have intermediate value theorem, and therefore a point where g(r) = 0, so f(r) = r.
    1. whereas if they're equal, they are both 0, and so f(0) = 0 and f(1) = 1 both.
    1. ----this works because [0, 1] is connected, and also in order, and also...uh, does contain 0 and 1?
    1. ---yeah, because intermediate value theorem wants 2 points that are in fact in the source, and if we take not 0 and 1 themselves, there're epsilon-sized gaps, so.
1. 4: X is ordered and connected. Goal: it's a continuum.
    1. continua have 2 properties: lub and intermediate.
    1. intermediate: suppose 2 points a < b do not have an intermediate. then the space is separable upon that; (, b) and (a, ) constitute a separation.
    1. lub: suppose some set has an upper bound but no least upper bound; any upper bound has a lower upper bound.
    1. ...so then we have points in that set, then above them, upper bounds, then, somehow between, some kind of bullshit.
    1. ok, let's take a union of bottom rays of points of this set. that's an open set w/o a lub.
    1. ...let's take a union of upper rays of upper bounds.
    1. that's also an open set.
    1. I assume there cannot be any points between those two: any point not in the first is above it, and so is an upper bound, and so has a lower upper bound, and so is union'd.
    1. so we have a separation which cannot be. done.
1. 5: which of those are linear continua?
    1. Z_+ ×[0, 1)
        1. I'm fairly sure this is just R^+, so, yes
    1. [0, 1)×Z_+
        1. (0, 0) and (0, 1) do not have anything between them, so, nope
    1. [0, 1)×[0, 1]
        1. intermediate works I think?
        1. for verticals yes because I, for nonverticals yes because horizontal
        1. lub: hm, if we approach (1, 1) we will not in fact have _any_ bound
        1. ----aren't they both (w/ the next one) ordered and connected?
        1. ---idea: every T-shaped — wait, no, or, um, wtf
        1. —I mean, yeah! pick any point, draw a T-shaped subspace through it; everything to the left is below, everything to the right is above
        1. ------but! if verticals are not closed, we get a separation!
        1. so _this_ one is in fact a linear continuum
    1. [0, 1] × [0, 1)
        1. but this one ain't
        1. because a sequence whose limit is (0, 1) has upper bounds (\eps, 0) but no lub
        1. and equivalently, we can cut this space at any topmost point and get a separation

1. 6: if X is well-ordered, X×[0, 1) is a linear continuum
    1. shown above
1. 7:
    1. a) X and Y are ordered; f: X -> Y is monotonous and surjective; therefore, it's an iso.
        1. Huh!
        1. ok, there're three parts here: inversion, continuity one way, continuity other way
            1. tho I think the third one is derivable from first two, because we just have a function Y -> X which is all that, so
        1. ok, monotonous aka order-preserving: a < b => f(a) < f(b)
            1. ....there's something about intermediate value theorem here, isn't it? though X needs to be connected which it need not be, so nah.
        1. ok, let's try to invert.
            1. let's take preimage of any point of Y.
            1. if it has 2 points in it, then everything breaks: f(a) = f(b) instead of <.
            1. it is in fact nonempty because surjection.
            1. so we have a bijection, nice.
        1. now, continuity.
            1. let's take preimage c of any point in f(a) < f(c) < f(b).
            1. c must be a < c < b, because if it's below then f(c) must be below, and if it's above then f(c) must be above.
            1. so preimage of (f(a), f(b)) is inside (a, b).
            1. but also any point between a and b projects inside (f a, f b), so preimage of (f a, f b) is exactly (a, b).
            1. so it's open, as desired.
            1. ---except for openings of rays?
            1. ---no, rays are unnecessary for a basis, I think. we get them from unioning intervals. ok, cool.
        1. Aaaaand done. huh.
    1. b: let's be in R_+. goal: x^n is order preserving and surjective; therefore, it and its inverse x^1/n are continuous.
        1. order-preserving: ......yes? y^n–x^n = (y–x)(polynomial w/ positive terms entirely), and so is positive whenever y–x is positive, so, yeah.
        1. surjective: ....yeah, roots exist? I think formal proof of this is grounded in rationally approximating them? And I don't want to rebuild that argument here.
    1. Let's be in (–∞, –1) \cup [0, ∞). and let's have a function from this to R, +1 in the first half and id in the second. it's order preserving and surjective. is it an iso?
        1. .......uh
        1. I think it's not supposed to be, because it's separable and R isn't
        1. ok, it is in fact order-preserving: it is if both are below –1, if both are above 0, and if one is below –1 and one above 0
        1. ------oh! is it not in order topology?
        1. in order topology [0, ∞) I think would not be open because there's no previous element to the 0
        1. yeah, and that explains it.
1. 8:
    1. a) is product of path connected path connected?
        1. you'd think so!
        1. if we have a binary product, then I think we can path-connect 2 points (a, b) and (c, d) by going first to (a, d) in Y and then to (c, d) in X.
        1. Same w/ finite products.
        1. for infinite products I dunno?
        1. ---well, lemma about union of connected subspaces on a point holds, I think? we go from 1 subspace to the point, and then from the point to the other subspace, and we're cool.
        1. lemma about closures I dunno, but if it did, then infinite products would also work.
        1. ----oh, huh
        1. so we can lift componentwise paths from I to X_i into....an entire path. because product. yeah, I'm dumbing here.
    1. b) lemma about closures; if A \subset X is path connected, then Cl A also is
        1. originally this works because.....the separation of the closure must have A and yet not contain any limit points of A on the other side, which is nonsensical
        1. ---oh!
        1. topologist's sine before closure is path-connected, and after, isn't. so there.
        1. 
    1. c) if f is continuous then f(X) is path connected if X is, yes? we proved that above??
    1. d) is just lemma about union upon a point, it holds I think???
1. 9: we're given that R is uncountable and A is a countable subset of R². then R² is path-connected.
    1. also we're given a hint that through any point of R² uncountably many lines pass.
    1. We need to show path-connectedness of R²–A.
    1. ok, so basically we start from a straight line between 2 points. at most countably many points on it are in A.
    1. Then we intend to patch it locally.
    1. ...uh. zooming in doesn't quite work if we have countably many holes, does it.
    1. .......worse, countably many holes means they can be _dense_ in R². think rationals.
    1. in any case: we could, at any such point, cut away a small disk, and, I dunno, choose a direction to continue the curve (in the same semiplane) in which it's continuable?
    1. -------oooooooh I see
    1. we take 2 points and a semiplane on one side of them
    1. then we start scanning directions from these points for a direction in which _there are no holes at all_
    1. we pick those two nonparallel directions (we can do nonparallel because that's only 1 additional direction), and we connect them with straight lines there and back. and we're done. Huh!
1. 10: if U is in R², open, and connected, then it's path connected.
    1. also, hint: if we pick a point x in U, then points that can be joined to x through a path in U form a set clopen wrt U.
    1. ....ooooookay.
    1. let's start with the hint.
    1. ok, uh. set of points (of U) reachable from x by a path lying in U.
    1. it should be closed in U.
        1. to prove that it's enough to show that any limit point of such set (that's in U) lies within it.
        1. so suppose we have a point y of U, any neighbourhood of whose (wrt U) contains a point reachable by path from x.
        1. .....U is open and strictcoverable, so we pick a ball around y that's small enough to be in U entirely.
        1. that ball then has a point which _is_ reachable from x, and, as balls are path-connected, we have a path from x to y, as desired.
    1. now open.
        1. so the set of points (of U) *un*reachable from x through U must also be closed.
        1. again, we pick a limit point y (of U) of such a set and a tiny ball around it, contained in U.
        1. it has a point unreachable from x.
        1. now if y was reachable, then x would also, through the ball; therefore, y is unreachable.
        1. so there.
    1. And, assuming those two are nonempty, we have a separation of U! into path-connected nonintersecting subsets, of points path-reachable and path-unreachable from a point x!
    1. which obviously cannot happen because U is connected.
    1. the set of points reachable from x is _definitely_ nonempty, because it contains x itself. therefore, there are no unreachable points.
    1. And then we can connect 2 arbitrary points through x, and so we have our path-connectedness. awesome.

1. 11: Suppose A \subset X is connected. Is Int A connected? Is Bd A? conversely?
    1. Nope to all of those; there're uncomplicated 4-point counterexamples
    1. For A => Int A: 4 points, open sets are a and b, A is abc.
    1. for A => Bd A: actually, open interval works
    1. for Int A & Bd A => A: I forget but it's not _hard_ ok

1. 12: about the long line
    1. a) Lemma: if X is ordered and a < b < c, "[a, c) has order type of [0, 1)" <=> "both [a, b) and [b, c) have order type of [0, 1)"
        1. well
        1. "has order type" means "there's an order-preserving isomorphism between"
        1. given (order-preserving) isomorphism f: [a, c) ~> [0, 1) we can find the point r = f b; then we have isomorphisms [a, b) ~> [0, r) and [b, c) ~> [r, 1), which are uncomplicatedly isomorphic to [0, 1).
        1. Conversely, given order types of 2 parts, we can glue them into an order type into [0, 2)
        1. (isomorphism is obvious, order-preservation is true when 2 points are in first half or second half, and is also true when they're one per)
    1. b) same lemma, but we have increasing sequence and its sup.
        1. if we have order type of the whole [x_0, b), then for any i we observe [x_i, x_{i+1}) to map into an interval [d, e) which is obviously etc.
        1. if we have order type of every interval, we glue them into the line [0, ∞), which is slightly less trivially but still order-preservingly isomorphic to [0, 1).
        1. (inversion is again obvious, order is similar: if 2 points of X are within the same interval, monotonicity carries; if they're from different, then the smallest is mapped into smallest integer-offset, & we're good)
    1. c) let's have $\omega_1 × [0, 1)$. for any a of \omega_1, let's observe that $[0×0, a×0) \sym [0, 1)$.
        1. Hint: transfinite induction; a either has a previous or is a limit of an omega-sized sequence.
        1. Case 1: a is 1. then [0×0, a×0) ≈ [0×0, 0×1) ~ [0, 1).
        1. Case 2: a has a previous for which the thing holds.
            1. then [0×0, a×0) = [0×0, a'×0) + [a'×0, a×0) ≈ [a'×0, a'×1), and we have the lemma to glue them.
        1. Case 3: a is an omega-sized limit.
            1. So we have [0×0, a_i×0) ~ [0, 1).
            1. First step: we split every one of them into the previous and the last chunk [a_i×0, a_{i+1}×0), and acquire order type for every such chunk
            1. Second step: those chunks constitute sufficient material for the (b)-lemma, and there we have it.
    1. d) L is path-connected
        1. it's enough to construct a path between any point and epsilon (0×\epsilon)
        1. we do this like so:
        1. if the point is in the 0×[0, 1) or 1×[0, 1), the path is obvious
        1. if the point is elsewhere, we split the path into 3 parts: [\epsilon, 1), [1, a), [a, a + \epsilon]
        1. the first is [0, 1), the second (by (c)) is [0, 1), the third is [0, 1]; gluing them all together, we get a [0, 1], as desired.
    1. e) any point of L has a neighbourhood homeomorphic w/ R. well, with open interval.
        1. any not-0 point obviously has this.
        1. any (a×0)-point...has 2 cases: it can have a previous or it can have an ascending chain.
        1. if it has previous, (a-1×0, a+1×0) works
        1. if it has an ascending chain, we know that [a_0×0, a+1×0) is [0, 1); we delete a_0×0 from it and we have our (0, 1), as desired.
    1. f) L cannot be imbedded in R^n. Hint: any subspace of R^n has a countable basis.
        1. Uh.
        1. I guess we need to prove the hint.
        1. ok, statement: if R^n has countable basis, then any of its subspaces also has a countable basis.
            1. because we can take a countable basis of R^n, restrict it to the subspace, and get a countable basis for it.
        1. Statement 2: R^n has countable basis.
            1. R itself: {(n–1, n+1) | integer n} is countable.
            1. R^n: n-ple product of that w/ itself is a finite power of a countable set which is countable. and is also a basis, this fact was proved somewhere above when we were about R^n.
        1. Statement: L cannot have a countable basis.
            1. suppose it has one.
            1. let's strictcover an epsilon-neighbourhood around every element of \omega_1 × 0.
            1. there's at least 1 open set covering such a neighbourhood; all of them disjoint.
            1. thereby, we have an injective map from (uncountable) \omega_1 into (countable) basis of L. absurd. done.
        1. aaaaand done.

1. (when I did 12*, I was somewhat nonplussed at the *. what's unusually complicated about this?! there are hints everywhere!)