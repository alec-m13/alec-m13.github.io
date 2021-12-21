---
defines: tictactoepology
title: 'Tic-Tac-Toe-pology'
description: 'Playing board games by applying local Turing machines to topological manifolds.'
inventor: me
---

I wanted to learn front end development by learning Angular, but I didn't want it to be too simple. I wanted a project I could be proud of. So I came up with Tic-Tac-Toe-pology. Now it's exploded to be very not-simple, well beyond the point of reasonableness. But it's just too fun to resist.

The original idea was to play Tic-Tac-Toe but with one extra rule: open tile edges can be glued together to allow for topological nontriviality. There are plenty of posts elsewhere online about playing the game on a torus (or a Mobius strip, Klein bottle, projective space, etc). My idea was to turn the board into one of these spaces mid game with a special kind of move a player can execute.

In order to do this the logic has to be built into place. And asking myself to build logic for something cool is a recipe for an explosion of antisimplicity. Does the board have to be a 3x3 grid? Does it even have to be a rectangle? Why restrict to Tic-Tac-Toe? Can't checkers work just as well? My answer: invent discrete manifolds to encode boards and local Turing machines to encode board game player moves and then define these games through those. Cool, cool. Super fun but not particularly simple. I tabled the local Turing machine idea as too complicated and I am hoping I can get a playable Tic-Tac-Toe-pology game before coming back to it (that means no checkers ... for now).

But before that happens, what is a board? My answer: discrete manifolds. Each tile has its own small piece of standard-looking board and the pieces glue according to certain transformation rules. That part actually came together pretty well, I got a proof of concept working in a week or so. Too easy. Next question: why squares? Don't hexagonal board games sound just as fun? My answer: generalize the xy plane into an algebraic structure constructed from some monoid generators and relations so that a board's reference plane (which defines the shape of the tiles) can be automatically computed by a few small configuration data. That's pretty cool. It's not incredibly simple, though, but I can see how it would work and I believe I can build it before running out of steam.

This project is getting pretty big so I branched it off as its own API. When (and if) finished it will be super easy to define board games on topological spaces with it. The API will compute all the stuff, all it takes is a few defining characteristics and a rendering technique. It's going to be awesome but I'm acutely aware of the danger that it may never be finished because it's too complicated. Time will tell...