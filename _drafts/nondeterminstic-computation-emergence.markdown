---
layout: post
title:  "A model of nondeterministic computation inspired by emergence"
<!-- date:   2018-07-30 20:00:00 -0400 -->
categories: complexity algorithms
permalink: /nondeterminstic-computation-and-emergence/
math: true
---

The complexity class $$NP$$ is the set of decision problems that can be
efficiently solved by a nondeterministic Turing machine (NTM). This definition
can feel a little dissatisfying. That's because when students of complexity are
invited to develop intuition about $$NP$$, this class is presented as a
[metaphor for human creativity](http://www.math.ias.edu/~avi/PUBLICATIONS/MYPAPERS/AW09/AW09.pdf),
capturing everything from proving theorems to composing symphonies.
But in stark contrast to the flamboyance of this metaphor, the way that problems in $$NP$$
are "solved" by NTMs is decidedly uninspired - given an instance of a problem in $$NP$$,
an NTM nondeterministically produces a correct solution,
confirms that this solution is correct, and that's that.

If you believe that $$NP$$ represents creative activity in our physical world,
this is a bit lacking. After all, in the real world, we aren't just handed solutions
to hard problems - we mere mortals actually do the solving! Of course, we have no idea
_how_ this happens, how a human brain proves a theorem or composes a symphony.
And the whole point of nondeterminism is to sidestep this ignorance with an abstraction
that says "it just does".

This approach is correct in the most meaningful
empirical sense because it has yielded such a rich and successful theory by ignoring
unanswerable questions about how hard problems are "actually" solved, and focusing
instead on the idea that their solutions, however they may be produced, are easy to verify.
In light of this fact, fixating on the "how" of nondeterminism is naive. But
embracing this naivete for the moment we can ask whether it's possible to
narrow the gap between the abstraction of nondeterminism and reality. This post is
an attempt to frame nondeterministic computation in a way that aligns it slightly
better with our emerging understanding of how the most impressive problem-solving
in our physical world takes place.

{%
  include figure.html
  name="figure_1_naive_ntm"
  caption="Figure 1. A generic NTM for a problem in NP."
%}
