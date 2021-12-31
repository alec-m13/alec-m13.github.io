---
layout: post
category: tictactoepology
title:  "Reference Grids"
---

# Overview

Tic-Tac-Toe is played on a rectangular grid (i.e. tiles are squares). So is chess and checkers. But not all games are played on these grids: Chinese checkers has a hexagonal grid. Should this engine be able to accomodate those games too? Certainly. I love Chinese checkers. Hence we should not restrict ourselves to rectangular grids. Enter the reference grid.

The reference grid defines the base tile structure. It is the trivialized space used as the setting for a board in the same way that Euclidean space is used as a setting for manifolds. They are abstract algebraic entities and they are defined with a few algebraic data.

We can get into the formal details later but the point is to have a coordinate system with a total order and a translation function. There is a distinguished position called the origin with special properties related to translation. Translation is a function which takes two positions A and B and returns the position to which B moves under the same translation which takes A to the origin.

The total order allows for use of SortedSets to power the underlying machinery, offering an exponential increase in time efficiency over unsorted sets because of binary searches.

Tiles have neighbors and these are declared by use of the unit sphere. The unit sphere is all positions which are adjacent to the origin. It can also be thought of as the set of directions. It must be closed under negating: any direction has an opposite direction which is itself a direction and hence a position in the unit sphere. It's theoretically possible to define the unit sphere in terms of a distance function, but for copmutational simplicity we require that the end user provides the unit sphere directly when constructing a ReferenceGrid. This induces a distance: the magnitude of a point is the miniimal number of translations it takes to get to that point following directions in the unit sphere.

Translation (and the information extractable from its structure) defines the shape of tiles, at least theoretically. Tiles also have orientations, but how are these declared?

Orientations are functions which take positions to positions and directions to directions. There are some technical requirements related to loss of information: orientations are reversible. Also orientations must respect translations. Again, formal details postponed for later.

It is not possible to check that all the conditions hold for all inputs: groups are usually infinite in size. Some care is taken to check the conditions on key points but for the most part the onus is on the user to create a consistent coordinate system.

# Example: The Rectangular Grid

The rectangular grid is the canonical example of a reference grid. Positions are given as pairs (x, y) of integers representing a position in the plane. This is a group under the action (x, y) + (a, b) = (x+a, y+b).

The origin is the point (0, 0). Note that it does not change values of other points when added to them.

Translation is given by T((a, b), (c, d)) = (c-a, d-b). This moves the point (c, d) the same amount as it takes to move (a, b) to the origin, namely by (-a, -b).

The unit sphere is all neighbors of the origin. That consists of (0, 1), (1, 0), (0, -1), and (-1, 0). Note each direction's opposite is also a direction.

There are 8 orientations we can choose from, but only two main ones. The first is rotation, (x, y) -> (y, -x). This rotates the plane counter-clockwise by a quarter turn. Repeating it multiple times gives all 4 rotations of the plane.

The other main orientation is the reflection (x, y) -> (x, -y). This can be composed with the four rotations to give four flipped orientations, or eight total orientations. This is exactly the symmetry group of the square.

# Abstract Requirements

The structure here is exactly that of a group. I'm choosing to use group terminology here.

Call the set of coordinates G. The user can't define G since it might be an infinite set. Instead the user provides the origin (some element of G) and the translation function T from G x G to G (mnemonically (a, b) -> b-a). Restrictions on T come from the following requirements:

- Define the unary operation - on G by -a := T(a, 0). It must be that -(-a) = a for all a in G.

- Define the binary operation + on G x G by a + b := T(-a, b). It must be that G is a group under + with identity 0.

The unit sphere is defined as a set of coordinates. It must be a (monoidal) generating set of G under + and it must be closed under -. That is, 1) every element of G (except the origin) must be representable as a sum x1 + x1 + ... + xn where each xi is in the unit sphere and 2) for each x in the sphere -x must also be in the sphere.

The sphere induces a distance on G (via magnitudes): The magnitude of an element is the minimal length of the generating sum expression over elements from the unit sphere. In other words, the magnitude is the minimal number of steps it takes to reach that element from the origin going in the directions of the unit sphere.

The full group of orientations is the group of automorphisms of G. Necessarily they fix the unit sphere. The orientations presented by the user must be a subgroup of the full group of orientations. Why subgroup instead of just all of them? In case the user doesn't want to allow for reflections or something like that.

Finally G must have a total order, a.k.a. a comparator. This is unrelated to the group structure.
