---
layout: post
title:  "A model of nondeterministic computation inspired by biology"
<!-- date:   2018-07-30 20:00:00 -0400 -->
categories: complexity algorithms
permalink: /nondeterminstic-computation-and-biology/
math: true
---

### Motivation

The
[complexity class $$NP$$](https://en.wikipedia.org/wiki/NP_(complexity))
is the set of decision problems that can be
efficiently solved by a
[nondeterministic Turing machine (NTM)](https://en.wikipedia.org/wiki/Non-deterministic_Turing_machine).
Attempts to motivate this formal definition usually present $$NP$$ as a
[metaphor for human creativity](http://www.math.ias.edu/~avi/PUBLICATIONS/MYPAPERS/AW09/AW09.pdf),
capturing everything from proving theorems to composing symphonies.
But in stark contrast to the flamboyance of this metaphor, the way that problems in $$NP$$
are "solved" by NTMs is decidedly uninspired - given an instance of a problem in $$NP$$,
an NTM nondeterministically produces a correct solution,
verifies that this solution is correct, and that's that (see figure 1).

{%
  include figure.html
  name="figure_1"
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
such a rich and successful theory
([NP-completeness](https://en.wikipedia.org/wiki/NP-completeness),
[inapproximability via PCPs](https://en.wikipedia.org/wiki/PCP_theorem),
etc.).
So fixating on the "how" of nondeterminism is admittedly naive.

That said, in the decades since the invention of the Turing machine, we've
significantly increased our understanding of the mechanics of the human brain
as well as other miraculously complex natural phenomena. So embracing our
naivet&eacute; for the moment, we can ask whether it's possible to narrow
the gap between the abstraction of nondeterminism and the reality of the
natural world. In other words, can we frame nondeterministic computation
in a way that aligns slightly better with our emerging understanding of
the naturally occuring phenomena that it is meant to represent?

Adopting a biologically inspired perspective on computing is not a new idea,
and has proven fruitful in
[distributed systems](http://people.idsia.ch/~luca/eccs05.ver2.pdf),
[optimization](https://www.amazon.com/Ant-Colony-Optimization-MIT-Press/dp/0262042193),
and
[computer security](https://www.cs.unm.edu/~forrest/publications/cacm96-final.pdf)
(some good general introductions to biologically inspired computing
can be found
[here](https://queue.acm.org/detail.cfm?id=1016985)
and
[here](https://www.nap.edu/read/11480/chapter/10)).
In this post, we'll explore a biologically
inspired model of nondeterminstic computation.


### Emergent Behavior

Nature runs on [emergence](https://medium.com/sfi-30-foundations-frontiers/emergence-a-unifying-theme-for-21st-century-science-4324ac0f951e);
complex systems of interacting entities that
give rise to sophisticated collective behavior.
Ants form colonies, cells form organisms, and neurons form brains that give rise to conciousness.
[Many other examples abound](https://www.nature.com/scitable/topicpage/biological-complexity-and-integrative-levels-of-organization-468),
all the way down to chemical and physical phenonmena and all the way up to the level of human populations.
More interesting discussions of emergence in biology are
[here](https://www.ncbi.nlm.nih.gov/pubmed/18166390)
and
[here](https://www.wired.com/2008/02/complexity-theo/).
In the world of computing,
[Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life)
is probably the most famous toy model of emergence.

The hallmark of emergence is a system of entities that
on the individual level

1. are very simple (relative to the complexity of their collective behavior),
and

2. possess only local knowledge of the system.

Sophisticated emergent behavior is born out of the _interactions_ between
these simple, myopic actors.

The rest of this post is an attempt to imagine nondeterminsitic computation
in these terms; as a system of simple,
myopic computational entities where the "magic" of nondeterminism is not in
the entities themselves but in their interactions.


### Biomorphic Nondeterminism

{%
  include figure.html
  name="figure_2"
  caption="Figure 2. A network of interacting deterministic verifiers."
%}

{%
  include figure.html
  name="figure_3"
  caption="Figure 3. Biomorphic determinism with a global verifier is equivalent to classical nondeterminism."
%}







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
