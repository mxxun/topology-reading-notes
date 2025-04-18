# Metric topology I exercises

1. ok, so: exercise 3
    1. let's have a metric space
    1. first: metric is itself a continuous fucntion from its space squared to R
    1. recall wha'ts continuous: preimage of any open is open
    1. so let's take an open interval in R and preimage it
    1. everything <0 has empty preimage
    1. so let's consider 2 classes of open bases: containing 0 and not
        1. a preimage of [0, a) is: all pairs of of points that are at most a apart
        1. I suggest we cover every such pair by a product of sufficiently balls centered on each of them respectively, and then show that this product has a diameter less than a
        1. say, a/3
        1. ....no, a – (distance between points) / 3, which is > 0
        1. then for any pair of points in these balls there's a path between them, from first to center to other center to second, which is shorter than a altogether
        1. which by triangle means they're closer than a apart
        1. & so, we're done here
    1. Second and third case: (a, b) and (a, +∞)
    1. reduction: preimage of intersection is intersection of preimages, so (a, +∞) is enough, because then we get open preimage of (a, b) as intersection of open preimages of [0, b) and (a, +∞)
    1. ok, so preimage of (a, +∞) is all pairs that are at least a-distant
        1. I think we can again do products of tiny balls, but this time radii are (distance) – a / 3
        1. then the distance between these cannot be less than a, because _that_ would violate triangularity of the of path between centers
    1. ....&&&&we're done w/ a! huh.
    1. b: now, kind of reverse: if d, the metric, on X'² is continuous, then X' shall be finer than X
    1. aka then X' shall have at least all epsilon-balls.
        1. well, let's see: [0, a) shall have as a preimage all pairs of a-less-nearby points; I think this is...a pretty fucked union of ball pairs; but how do I do more specific than that?
        1. also I think if we get any particular product of epsilon-balls open in the product, then we'll have enough, because to produce that X' should have at least X
        1. ....ok, _how_ do we get a particular pair of balls centered at x and y open
        1. .....stumped.
        1. ok, another way: it'd be enough if we could cover X²'s prebasis w/ X'²'s open sets
        1. X²'s prebasis is x,a-ball×X and conversely
        1. the problem is I really have no idea how to get any more specific/constrained open sets of X' than "all pairs closer than a"
        1. .....ok, _can't_ I have a coarser topology? whyever not, what in the continuity of d makes it produce open balls in X?
        1. specific example: let's have X = I (open) w/ standard metric and topology
        1. then the product is an (open) square
        1. then the preimage of (0, eps) is the epsilon-thick diagonal, I think
        1. and of (a, b) would be symmetric strips between a- and b-diagonals
        1. .........ok, so I think the thing I had no idea how to incorporate is that X×X is in fact a product space, and it has some A×A open, and in fact these diagonal stripes must be coverable by some A×A
        1. then it'll be enough to show that to cover those stripes it's in fact necessary to have epsilon-ball-shaped A×A, and then we'll be good
        1. ok, we can state absolutely confidently: for any point a, there's a neighbourhood of a that's contained in an epsilon-ball around a
        1. (because (a, a) is in the preimage of [0, eps), and must be covered by an A×A, and such an A must contain a and nothing >eps-away from a, which makes it fit into the a,eps-ball)
        1. ok, that's not yet it but it's suggestive
        1. .....ah, and then we cover an eps-ball around a by covering every point within it by such a neighbourhood contained in an eps'-ball small enough to not go beyond the eps-ball, & then we're cool
    1. Phew! cool.
1. Ex 4!
    1. Ex 4a: functions from R to R^omega, considered continuous
        1. ok, reminder: function is continuous if preimages of prebases are open
        1. and another reminder: bases of product, uniform, and box are: bricks, cubes, and cofinitely finite bricks
        1. ok, so, first function maps t to (t, 2t, 3t,) etc
            1. What's a preimage of a typical, e.g., cube along that?
            1. uuuuuuh.
            1. if the cube is finite then preimage is probably empty, because this sequence of coordinates is unbound.
            1. Likewise for finite bricks.
            1. Likewise for anything _but_ cofinitely finite bricks.
            1. -----wait, no, not _empty;_ bricks and cubes that contain 0 will have 0 as the preimage, and therefore the function will not be continuous
            1. cofinitely finite bricks will have another thing
            1. given a t and a cf-brick, there will be finitely many dimensions in which the image of t might not fit
            1. so we basically take preimages of f along these dimensions and finitely intersect them and get an open set in R, so, works
            1. .....another much easier (tho more opaque) line of reasoning is that dimensionwise components of f are continuous, and therefore their proper product will also be sox
        1. g maps t to (t, t, t, ...)
            1. I think hilbert's brick successfully fails to contain anything but 0, so also not continuous in box
            1. I think if a cube fits contains t in all dimensions, it also contains t±eps in all dimensions
            1. so suppose we go over all boundaries a cube imposes on t
            1. there're ∞ dimensions for it to be located on, but, uh
            1. ...ok, I think it can be located on (-1+eps/n, eps/n) on even dimensions and on (-eps/n, 1-eps/n) on odd
            1. so 0 is contained, but any other t is eventually cut out by ever-tighter bounds on higher dimensions
        1. h maps t to (t, t/2, t/3, ...)
            1. hilbert's brick _again_ fails to contain anything but 0
                1. no matter how small is t, there's an n at which 2^-n < t/n, & so
            1. uniform is similar, we just crank it up to eps/2^n, & we're cool
    1. So, Ex 4a answers:
        1. all continuous in product, because all three functions are continuous componentwise
        1. f is not cont. in box and uniform, because preimage of 0-centerd brick or cube is 0, because no other image fits into a finite brick or cube
        1. g likewise, because we can make cubes hedge out anything but 0 by making them increasingly close to 0 from either side in alternating dimensions
        1. h likewise
    1. 4b: convergence of sequences
        1. Reminder that a sequence converge if there's ~~exactly~~ at least 1 point any neighbourhood of which contains almost entire sequence
        1. ....are they all hasudorff & therefore have at most 1 convergence points? they...might be...
        1. ok, anyway
        1. w:
            1. 111, 0222, 0033, etc
            1. I think no 1-dimensional epsilon-ball contains any _two_ of these simultaneously, so no limit in any topology
            1. .....except that no, in product any ball around 0 has only finite finite dimensions, & so from the last of it onwards it contains everything
            1. so 0 as a limit in product, & probably nothing in uniform because cubes do not care
        1. x: 111, 01/2, 001/3, etc
            1. in product, 0 should work; eps-ball around it will contain all beyond some n
            1. ~~in uniform, likewise~~
                1. what about a lopsided cube? that's eps/2^n away from 0 in nth dimension?
                1. probably can in fact no do the same thing as w/ hilbert's
            1. in box, hilbert's brick tells us to go fuck ourselves because as dimensions progress it contracts fast enough to hedge out every single point
        1. y: 1000, 1/2 1/2 00, 1/3 1/3 1/3 000
            1. I think even hilbert's brick cannot contract fast enough to avoid all of them being eventually 0
            1. & however small it is in any particular dimension, eventually the sequence get small on it that it fits
            1. what if it... contracts fast enough that any point has _some_ dimensions it doesn't fit on
            1. yeah, fair, no limit in box
            1. in uniform I think same, just w/ lopsided cubes
        1. z: 11000, 1/21/2000, 1/31/30000
            1. uh product obviously 0 because even cubes tiny on first 2 dimensions eventually fit
            1. in uniform 'n box honestly too, because there're only finitely many dimensions to be tight on, & all of them converge, so
1. Ex 5:
    1. let's have R^∞, all sequences that are eventually 0.
    1. or equivalently, points that are nonzero in only finitely many dimensions.
    1. what's the closure of this set under uniform?
    1. ok, reminder: closure is the smallest closest set containing the subject set.
    1. first, what are closed sets in uniform again? closed cubes?
    1. 

1. Uuuugh, Ex6 states that my "cubes are a basis for uniform topology" is wrong as fuck
    1. ok, let's recall how tf uniform works
    1. it imposes a bounded metric on, I dunno, L∞ aka max
    1. so d(x,y) computes like such: take all differences between coords, limit them all to 1, the supremum of that sequence is your distance.
    1. let's take $0<e<1$. then an e-ball around x contains all points all coords of whose are at most e-distant from x's. 
    1. so, uuuuuh, why _isn't_ it the infinite product of intervals?
    1. and why a cube w/ strictly smaller \delta  is not contained in the e-cube entirely?
    
    1. ok, so apparently there should be a point that's closer than e to x, but does not fit in the infinite product of (x_i-e, x_i + e)
    1. the first directly means that the supremum of differences of coords is <e
    1. which implies that all coords are within x_i-e, x_i + e
    1. ugh, what the fuck!

    1. ok, got it
    1. the sequence e - 1/n has e as a sup and so is not in the ball, but is in the cube
    1. union over cubes less than that ensures that any sequence w/ limit $<e$ _will_ be unioned, but those w/ limit exactly e....
    1. but if a sequence has limit e, then it won't fit in any cube of size $\delta<e$, because for any such cube it has dimensions in which it's closer to e than even \delta
    1. yeah, ok, that works

    1. I'll leave (b) as is for now

1. 8.
    1. So let's have actual l² topology on R^\omega. well, on its subset where l² is defined.
    1. a: box is finer than l² is finer than uniform.
        1. ok, so we want to show that any ball of uniform can be covered by balls of l², and of l² by balls of the box.
        1. let's consider a (x, e) ball of uniform and its point y. d(x, y) < e, aka sup (|x_i - y_i|) < e. aka both every dimension and the limit have distances < e.
            1. we want to point a tiny l² ball at y and show that it's entirely in that (x, e) ball.
            1. .......uh, actually, we're also aware that $\sum x²_i$ converges, so limit of any point can be only 0, so any limit distance can be only 0, so really the sup is about bounding in every dimension.
            1. so let's draw an (e-d)/2 l²-ball at y and pick its point z. why is z in uniform-ball (x, e)?
            1. because: we can bind the |y_i - z_i| on _every_ dimension by (e-d)/2, because more than that would automatically exceed the distance which is a root of sum of squares including that one
            1. and then |x_i - z_i| is bound (by the same argument as triangle) by sum of, and |x_i – y_i| is actually <= than _d_, and d + (e-d)/2 < e.
        1. Now, l² by box.
            1. Again, let's have points x, y, z; y is in l² (x, e) ball (actual distance d), z in box (y, ?) ball
            1. given are that $\sum (x_i – y_i)² = d²$ and the goal is $\sum (x_i – z_i)² \lt e²$
            1. we bound $(x_i – z_i)² \le (x_i – y_i)² + (y_i – z_i)²$ like in triangle, and subtract the first equation, and acquire the goal $\sum (y_i – z_i)² \lt e² – d²$
            1. Which is easily satisfied by setting (y_i — z_i)² = (e² – d²) / 2 × 2^-i.
    1. b: 
        1. R^∞, sequences that are eventually 0, are contined in X: trivial.
        1. all four topologies it inherits (box, l², uniform, product) are distinct.
        1. now that's a puzzle!
        1. so there's a box uncoverable by l², l² uncoverable by subcube, subcube uncoverable by w/e happens to cofinitely finite brick.