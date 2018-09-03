---
layout: post
title:  "A model of nondeterministic computation inspired by biology"
<!-- date:   2018-07-30 20:00:00 -0400 -->
categories: complexity algorithms
permalink: /nondeterminstic-computation-and-biology/
math: true
---

### Motivation

The complexity class $$NP$$ is the set of decision problems that can be
efficiently solved by a nondeterministic Turing machine (NTM).
Attempts to motivate this formal definition usually present $$NP$$ as a
[metaphor for human creativity](http://www.math.ias.edu/~avi/PUBLICATIONS/MYPAPERS/AW09/AW09.pdf),
capturing everything from proving theorems to composing symphonies.
But in stark contrast to the flamboyance of this metaphor, the way that problems in $$NP$$
are "solved" by NTMs is decidedly uninspired - given an instance of a problem in $$NP$$,
an NTM nondeterministically produces a correct solution,
verifies that this solution is correct, and that's that (see figure 1).

{%
  include figure.html
  name="figure_1_naive_ntm"
  caption="Figure 1. A generic NTM for a problem in NP."
%}

If you believe that $$NP$$ represents human creativity this model can feel dissatisfying,
because it hides that
creativity within the impenetrable black-box of the nondeterministic
solution creator. It begs the question - what's going on in there?

To be clear, the question of "how" is irrelevant to computational complexity theory,
where the abstraction of
nondeterminism intentionally sidesteps unanswerable questions about how hard problems are
"actually" solved, and instead shifts the focus to the idea that their
solutions, however they may be produced, are easy to verify.
This approach is correct in the most meaningful empirical sense because it has yielded
such a rich and successful theory (NP-completeness, inapproximability via PCPs, etc.).
So fixating on the "how" of nondeterminism is admittedly naive.

That said, in the decades since the invention of the Turing machine, we've
significantly increased our understanding of the mechanics of the human brain
as well as other miraculously complex natural phenomena. So embracing our
naivet&eacute; for the moment, we can ask whether it's possible to narrow
the gap between the abstraction of nondeterminism and the reality of the
natural world.

Adopting a biologically inspired perspective on computing is not a new idea,
and has proven fruitful in distributed systems and computer security.
In this post, we'll explore an attempt to bring this perspective to bear
on the theory of computation as well.










### Emergent Behavior



### Conclusion


### Scratch pad

TODO prior art. biological inspiration. actor model.



Now, the truth is we don't _really_ know how a human brain proves a theorem
or composes a symphony. And more importantly

Of course, we have no idea _how_ this happens, how a human brain proves a theorem or composes a symphony.
And arguably the point of nondeterminism is to sidestep this ignorance with an abstraction
that says "it just does". In this traditional treatment of nondeterminism we ignore unanswerable questions
about how hard problems are "actually" solved, and focus instead on the idea that their
solutions, however they may be produced, are easy to verify. This approach is correct in the most meaningful
empirical sense because it has yielded such a rich and successful theory of computational
complexity (NP-completeness, inapproximability via PCPs, etc.).

In light of this, fixating on the "how" of nondeterminism is naive. But
embracing this naivet&eacute; for the moment we can ask whether it's possible to
narrow the gap between the abstraction of nondeterminism and reality. This post is
an attempt to frame nondeterministic computation in a way that aligns it slightly
better with our emerging understanding of how the most impressive problem-solving
in our physical world takes place.
