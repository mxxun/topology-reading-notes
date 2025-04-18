# Meditations on covering space of S²

1. ----at the very least we can now comprehend how to map S² n-foldly on itself & why this is cont (S² is a disk w/ upper & lower identified. now cut the disk into n disks horizontally, map them separately, and by pasting lemma that's cont because they all agree on the seams.)
2. _and_ this gives us the fact that.....[S², S²] has at least ℤ distinct maps? because uh
    1. well at least the idea of the fact. I think it's because these maps can also be path-homotopic, and they & their path homotopies also lift, & their end..points? are distinct just like in S¹.
3. ......ok, Q: we could maybe conceptualize ℝ as a...natural ω-point of the covers zⁿ. like, it's....a gluing not of n ~~circles~~ intervals-mapped-to-circle, w/ the last going back, but of ω of them, going infinitely both ways.
    1. ......right, yeah, ℝ _is_ ω×I w/ (n, 1) ~ (n+1, 0).
4. so.....why don't we just. _construct_ an analogous covering space for S². ω many squares, upper identified with lower, left & right contracted to points.
5. it is _like_ a vertical strip of the plane, but w/ left & right boundaries contracted to points.
6. wait, it's also not a covering space? and S² are not covers either? because preimage of a pole-neigh is a single point? yyyyeah. annoying!!
7. and if we try to not identify the n cusps & leave them distinct....uhhhh. their neighs will fail to be disjoint, I think?
8. ....drawing another kinda-covering & I'm not sure?
    1. like: draw 2 squares horizontally glued, identify their upper sides towards the center and separately their lower sides likewise and leave the seam. well, and ×ω.
    2. anything not on the seam gets a disjoint open-disk preimage in every square, no problem. in every sphere-with-a-seam, even.
    3. everything in the seam but not on 2 seam endpoints gets a sensible treatment.
    4. seam-endpoints.......hm. I think regardless of whether we identify their copies, we get weird bullshit in the preimage of a small disk, because it is...path connected. so, no disjointness.
9. .....I kind of feel like I could describe _why_ this obstacle happens for S² but not S¹?
    1. smth smth boundary of I is {0, 1}, and _points_ do not have a boundary
    2. but boundary of a sphere-with-seam is the seam I (2, actually), and....?
    3. ...well, ok, we could say that the boundary of a "normal" point of the seam is...."disjoint" "from the other side"??
    4. ....no, yeah, that's exactly right: _preimage_ of an ordinary seam-point's neigh in any single seamed segment splits in 2 disjoint pieces. therefore, we can rearrange their joins like we do w/ I and S¹.
    5. preimage of a neigh @ seam-boundary, however, is connected in any segment, & so will stay connected after. bad.
10. could we....avoid this somehow?
11. ......actually, maybe not because....if we had a PC covering space for S², then preimages of basepoint would generate loops in S², and there's exactly 1 loop in S² so no multiple-fold cover can be valid?
    1. because a path between basepoint preimages in the cover is a loop in S² that can't be homotopic to the trivial one.
12. ....and quick google suggests that proofs that S² is SC in fact work like we'd expect, mostly.
    1. i.e. like this:
    2. it suffices to move p away from a point, & then SLH it to constant.
    3. pick a point x; consider a small open disk around it & a complementary open disk excluding x. that's an open cover of S², (which is compact?), & by Lebesgue Number Lemma, we can cut I into segments whose images are lie in 1 of these 2.
    4. now consider segments that go through x & lie in the small open disk around it. open disk is contractible, so any of them individually is SLH to a segment not going through x.
    5. now move these away sequentially, and we're done.
        1. or maybe in parallel, doesn't really matter.
    6. 