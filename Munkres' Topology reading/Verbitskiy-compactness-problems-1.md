# Verbitskiy Compactness Problems 1

1. see http://verbit.ru/MATH/UCHEBNIK/Verbit-topology-in-problems-and-theorems.pdf
## compactness of I
1. Fragment that we do understand: we can work w/ (a, b) basis
    1. because any unfinitizable cover implies existance of unfinitizable basis cover?
    1. because....we can split any cover into a basis cover, and in the meantime we won't introduce any finiticity
    1. because if the result has a finite subcover then we can call back original sets & those form a finite subcover & this is disallowed by assumption
    1. ok, cool

1. another fragment: we can take any cover & reduce it to a cover that does not have strict subsets
    1. we can just filter that set by an uncomplicated predicate?
    1. ....actually, it is slightly complicated (because it's not trivially obvious that it works in 1 filter step, & fixpoint of filter is complicated)
    1. but I think it does work in 1 step: we take the cover \mathcal C, & we take from it only those sets that do not have strict supersets among \mathcal C
    1. we still have a cover of any point because.......the collection of sets covering a point will not be filtered entirely, because any filtered set has a superset which also covers the point, right.

1. anyway, we have an assumption: an infinite cover of I which has no finite subcover
    1. we want to derive either a finite subcover explicitly, or a contradiction in general
    1. vague idea: exhaust the I explicitly
        1. we didn't yet manage to show impossible or grind to completion
        1. the basic idea is to get some restrictions from the fact that.....there are limits
            1. that any (qualifier) sequence _does_ have a limit and this prevents some unfinitizable covers
        1. ok, let's push this idea somewhere
        1. we can build series of finite subcovers that cover strictly increasing segments of I
            1. e.g. like this: pick any set that covers 0; pick any set that covers the upper point of the previous (it's well-defined), repeat
        1. the assumption says that none of these finite subcovers are a total cover
        1. this implies that there's a set of points not covered by this
        1. conversely, union of those has an upper point that's never covered
        1. this....implies....that the sequence of upper bounds of those intervals...has a limit inside I
        1. I _think_ lower bounds also must have the same limit?
            1. nope; they can start very slowly higher but converge very low
        1. ....how about we choose the next set instead to "start highest and reach furthest"
            1. the one that starts furthest and the one that reachest furthest are in fact the same one if we reduced the cover to do-not-contain-others
            1. because if one that starts highest does not reach furthest, it is entirely contained in the one that reaches furthest, and therefore was removed upon filtering; a contradiction
        1. ok, what implications "start furthest" have
            1. it demands that the starting point of nth set is above the ending of n-2th
            1. because otherwise n-1th and nth have a conflict: the highest-starting of them must have been chosen to be n-1, & the other chosen never
        1. ok, that _is_ enough to make starting points converge to the limit of ending points; they're pointwise higher and lower, & so by sandwitch
        1. but then I think we can build a contradiction yet again
            1. we will pick a neighbourhood of the limit point in the cover
            1. & it will contain cofinitely many sets that we picked, because their lower and high ends are x-\eps < _ < x.
        1. ....aaaaand that's it; we have a contradiction everywhere.
1. ok, Mike thinks this is basically a fine proof. cool. let's summarize it.
    1. first reduction: we can consider covers made of intervals.
        1. (because irreducible cover can be covered by intervals, & that new cover too must be irreducible, or else we can follow it back)
    1. second reduction: we can impose "no strict subsets" onto the cover
    1. third: we'll start from any covering 0 and pick the highest-and-furthest intersecting-the-previous as next (:= (a_i, b_i))
        1. those are the same because of the second reduction
        1. consequence: a_n > b_n-2
    1. fourth: if this does not produce a cover in finite steps, a_n and b_n have a limit c (in I)
        1. then a neighbourhood of c covers cofinitely many of (a_n, b_n), a contradiction!

1. Note that the fourth step is secretly nontrivial and the only one that requires I
    1. the "c is in I" in particular doesn't work if c=1

1. note that the textbook proof uses closure properties of the set of "points s.t. [l, x] is coverable with a finite subset of \mathcal A"
    1. we somewhat want to analyse tools/tricks/techniques used in this proof but maybe later

## more 5.1
1. when is discrete topology compact?
    1. ..............whenever?
    1. no, wait, wrong
    1. ok, do explicit: compactness means that any cover has a finite subcover
    1. if we have a disjoint cover, it has no nontrivial subcovers; if it then infinite topology is not compact
    1. so: infinite discrete topologies are not compact like that
    1. conversely, finite discrete topologies are compact because all finite are
1. when is codiscrete topology compact?
    1. remind me wtf is that 
        1. ncatlab says it's the coarsest topology
        1. it also says that discrete and codiscrete spaces can be thought of being built by functors left and right adjoint to the forgetful Top -> Set
        1. which: _not touching that yet_
        1. but fucking cool
    1. so, in codiscrete, only empty and whole are open
    1. then, the only cover is from the whole, & it's finite
    1. so any codiscrete is compact
    1. cool

## 5.2*
1. let's have an M with a cofinite topology. classify compact subspaces of M.
1. hooooooo boy.
1. ok.

1. all finite subspaces are compact as usual. looking at infinite.
1. the whole is compact:
    1. take any 1 in a cover; it covers cofinitely many points
    1. then the finite rest can be covered finitely pointwise

1. .....any subspace has cofinite topology itself, & so is compact by above
    1. why: for any finite subset of a subspace, there's an open set in the original space complementing that finite subset
    1. when cutting to subspace, it becomes a complement of that finite subspet wrt subspace
    1. done!
1. Q: why the fuck this is a *-question

## 5.3–5.7
1. :D
1. they're pretty similar (80% identical) to what we already did on compactness!

1. 5.3 is "closed subspace of compact is compact"
1. 5.4 is different actually

1. 5.5 is "compacts in Haus are closed"
1. 5.6 is "compacts in Haus have separations"
1. 5.7 is "compact Haus has T4", aka any 2 closeds are separated
    1. they're compact because superspace is compact
    1. they're separated because lemma about compacts in Haus
    1. done

## 5.4
