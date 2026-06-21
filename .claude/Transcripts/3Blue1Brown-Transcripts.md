## EXEMPLAR EXTRACT — not full transcripts. Kept only passages that best demonstrate a teaching beat; cut repetition, sponsor reads, and tangents. Source: 3Blue1Brown (2 videos).
### Contains: Problem/exposition setup · Analogy anchor · Structural mapping · Analogy breakdown · Deeper question

---

## Video 1: How Wiggling Charges Give Rise to Light

### Problem/exposition setup (one driving question stated up front, then deliberately deferred)

In the last video, you and I looked at this demo here, where we shine linearly polarized light through a tube full of sugar water, and we saw how it rather mysteriously results in these colored diagonal stripes... Namely, why does sugar water twist the polarization direction of light? Why does that twisting rate depend on the color of the light? And why, even if you understand that this twist is happening, would you see any evidence of it when viewing the tube from the side, with no additional polarizing filters? Here, I'd like to begin with the very fundamental idea of what light is, and show how the answer to these questions can emerge from an extremely minimal set of assumptions.

### Analogy anchor (Coulomb's law introduced by the question it answers, before the correction term)

In some sense, the fundamental question of electricity and magnetism is how the position and motion of one charged particle influences that of another... charges with the same sign tend to repel each other. And the strength of this force depends a lot on the distance between them... the important fact is that you've got this 1 divided by r squared term, where r is the distance between them. So for example, if the distance between them increases by a factor of 3, the force that they're applying to each other goes down by a factor of 9.

I bring up Coulomb's law to emphasize that it's not the full story. There are other ways that charges influence each other. For example, here's a phenomenon that this law alone could not explain. If you wiggle one charge up and down, then after a little bit of a delay, a second charge some distance to its right will be induced to wiggle up and down as well.

### Structural mapping (building the radiating field, object by object, from one law)

The important factor I want you to notice is how the force also depends on the distance between the particles, but instead of decaying in proportion to r squared, it only decays in proportion to r. So over long distances, this is the force that dominates, and Coulomb's law is negligible. And then finally, it depends on the acceleration of that first particle, but it's not the acceleration of that particle at the current time, it's whatever that acceleration was at some time in the past. How far in the past depends on the distance between the particles and the speed of light... any form of influence can't propagate any faster than this speed, c.

This component of the field is only ever non-zero when our first charge is moving somehow, when it has an acceleration vector on it. And because of this delay term, the effects on this field tend to radiate away from the charge... This radiating influence is light, or more generally, electromagnetic radiation, including things like radio waves and x-rays and all that good stuff.

For example, if I set that charge oscillating up and down in the z direction... you see these circular propagations of equal strength in all directions... At points that are far enough away from the charge, which is where this component of the field is what dominates anyway, the wiggling in the field is essentially parallel to the wiggling in the charge, which is why when we think about light waves, we're safe to think about the wiggling direction as being perpendicular to the propagation direction.

But notice what happens if I take a whole row of charges, say oriented along the y axis, and I have them all start wiggling up and down in the z direction... The effects of all these charges interfere destructively along the y direction, but they interfere constructively along the x direction. This is what it looks like for a beam of light to be concentrated along just one dimension.

### Analogy breakdown (pushing "light bouncing off things" until the billiard-ball picture fails and a better one replaces it)

Sometimes when people talk about light bouncing off of things, the implied mental image is a projectile ricocheting off of some object, heading off in some random direction. But the better mental image to hold in your mind is that when the propagating light waves caused by some wiggling charge reach some second charge causing it to wiggle, that secondary wiggle results in its own propagation... If you have some concentrated beam of polarized light interacting with some charge, causing it to wiggle up and down, then these resulting second-order propagations are most strong in the directions perpendicular to the direction of polarization. In some sense, you could think of light as bouncing off of that charge, but the important point is that it doesn't bounce in all directions equally.

So suppose the observer was looking at a point like this one, where the polarization direction happens to be straight up and down. Then the second-order propagations resulting from wiggling charges at that point are most strong along the plane where the observer is, so the amount of red that they see at that point would look stronger. By contrast, if they were looking at a different point in the tube like this one, where the wiggling direction is closer to being parallel to the line of sight, then the direction where the scattering is strongest is not at all aligned with the observer, and the amount of red they see is only going to be very weak.

As an analogy, imagine there was a ribbon going down the tube, always aligned with the polarization direction for this color, then putting yourself in the shoes of the observer, when you look at points where the ribbon appears very thin, you're going to see very little red light, whereas if you scan your eyes over to points where the ribbon appears thicker, you're going to see more red light.

### Deeper question (the answer reveals a harder, still-open piece of the original question)

And now at last let's turn to the heart of the matter and try to explain why interactions with sugar would make light twist like this in the first place... the relevant property of sucrose here is that it's what's called a chiral molecule, meaning it's fundamentally different from its mirror image... It turns out that the amount this chiral molecule slows down, say, left-handed circularly polarized light is different from the amount that it slows down right-handed circularly polarized light. Effectively, there's not one index of refraction, but two.

Notice how it's possible to express this vector as a sum of two rotating vectors, one of them rotating at a constant rate counterclockwise, and the other one rotating clockwise... if the circularly polarized light wave represented by that left vector gets slowed down a little bit every time it runs across a sugar molecule... the effect on the sum is to slowly rotate the direction of linear polarization.

I'll call this a partial answer to our question number one, because it still leaves us wondering why there's an index of refraction in the first place, and how exactly it might depend on the polarization of the light, not just the material it's passing through... At this point I think we've covered quite enough for one video, so I'll pull out a discussion covering the origins of the index of refraction to a separate video.

---

## Video 2: A Tale of Two Problem Solvers | Average Cube Shadow Area

### Problem/exposition setup (the puzzle exists to illustrate two ways of seeing it)

I should say that the point of this video is not exactly the puzzle per se, it's about two distinct problem-solving styles that are reflected in two different ways that we can tackle this problem. In fact, let's anthropomorphize those two different styles by imagining two students, Alice and Bob, that embody each one of the approaches. So Bob will be the kind of student who really loves calculation... Alice on the other hand is more inclined to procrastinate the computations... she prefers to get a nice high-level general overview of the kind of problem she's dealing with, the general shape that it has before she digs into the computations themselves.

Now the puzzle that both of them are going to be faced with is to find the average area for the shadow of a cube... As a first step, and this is really independent of any particular problem solving style, just any time you find a hard question, a good thing that you can do is ask, what's the simplest possible, non-trivial variant of the problem that you can try to solve?

### Structural mapping (Bob's path: angle to cosine to formula, derived rather than guessed)

Bob looks at this, and he wants an actual formula for that shadow. And the way he might think about it is to consider the normal vector perpendicular off of that face. And what seems relevant is the angle that that normal vector makes with the vertical... when theta is equal to zero, the area of that shadow is the same as the area of the shape itself... And if theta is equal to 90 degrees, then the area of that shadow is zero.

If we consider the plane that passes through the vertical as well as our normal vector... we can focus our attention on a two-dimensional variant of the problem... we can think about the cosine of that angle, theta, which remembers the adjacent over the hypotenuse. It's literally the ratio between the size of the shadow and the size of the slice. So, the factor by which the slice gets squished down in this direction is exactly cosine of theta.

### Analogy breakdown (Alice's reframe: the same fact, stripped of what doesn't matter, until it generalizes)

What Alice knows from one of her favorite subjects, linear algebra, is that if you take some shape and you consider its area, then you apply some linear transformation, then the area of that output looks like some constant times the original area of the shape... the thing that she writes down is how this proportionality constant between our original shape and its shadow does not depend on the original shape. We could be talking about the shadow of this cat outline, or anything else, and the size of it doesn't really matter.

Keep in mind, this would not at all be true if we were dealing with the harder case that has a closer light source. In that case, the projection is not linear... Alice is keeping an eye out for what properties of the problem are actually relevant because that helps her know how much she can generalize things. Does the fact that we're thinking about a square face and not some other shape matter? No, not really. Does the fact that the transformation is linear matter? Yes, absolutely.

She says, actually, if we think about the whole cube, not just a pair of faces, we can conclude that the area of the shadow for a given orientation is exactly one half the sum of the areas of all of the faces... for a particular ray of light that would go from the sky and eventually hit a point in the shadow, that ray passes through the cube at exactly two points. There's one moment when it enters and one moment when it exits... our cube, because it's convex, between the first point of entry and the last point of exit, it has to stay entirely inside the cube by definition of convexity.

Instead of saying add up the areas of the cubes at all the different orientations, we could say just add up the average shadows for the six different faces and divide the total by one half... In short, the average of the sum of the face shadows is the same as the sum of the average of the face shadows.

The significance of this result right here is not merely that these two values are proportional. It's that an analogous fact will hold true for any convex solids, and, crucially, the actual content of what Alice has built up so far is that it'll be the same proportionality constant across all of them.

The magic of what Alice has done is that she can take this seemingly specific fact that the shadow of a sphere has an area exactly 1 fourth its surface area and use it to conclude a much more general fact that for any convex solid out there, its shadow and surface area are related in the same way... she can go and fill in the details of the particular question about a cube and say that its average shadow area will be 1 fourth times its surface area, 6 s squared. But the much more memorable fact that you'll go to sleep thinking about is how it didn't really matter that we were talking about a cube at all.

### Deeper question (the slick proof versus the calculation — which one is actually how math gets discovered)

It's easy for this contrast of Alice and Bob to come across like a value judgment, as if I'm saying, look how clever Alice has managed to be, she insightfully avoided all those computations that Bob had to do. But that would be a very misguided conclusion... if you look at the history of this problem, it was proved by Cauchy in 1832, and if we paw through his handwritten notes, they look a lot more similar to Bob's work than Alice's work... So if we were asking the question which of these two mindsets correlates with the act of discovering new math, the right answer would almost certainly have to be a blend of both.

The irony of being biased to show insights that let us avoid calculations is that the way people often train up the intuitions to find those insights in the first place is by doing piles and piles of calculations. All that said, something would definitely be missing without the Alice mindset here... how sad would it be if we solved this problem for a cube and we never stepped outside of the trees to see the forest and understand that this is a super general fact, it applies to a huge family of shapes.

As a final thought... there is still one unanswered question about the very premise of our puzzle. What exactly does it mean to choose a random orientation?... The case with Bob is relatively straightforward, but the point at which Alice locks down some specific distribution on the space of all orientations is not at all obvious. It's actually very subtle.
