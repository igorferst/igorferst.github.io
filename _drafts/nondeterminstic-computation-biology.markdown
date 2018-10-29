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
is the set of [decision problems](https://en.wikipedia.org/wiki/Decision_problem) that can be
efficiently solved by a
[nondeterministic Turing machine (NTM)](https://en.wikipedia.org/wiki/Non-deterministic_Turing_machine).
Attempts to motivate this formal definition usually present $$NP$$ as a
[metaphor for human creativity](http://www.math.ias.edu/~avi/PUBLICATIONS/MYPAPERS/AW09/AW09.pdf),
capturing everything from proving theorems to composing symphonies.
But in contrast to the flamboyance of this metaphor, the way that problems in $$NP$$
are "solved" by NTMs is decidedly uninspired - given an instance of a problem in $$NP$$,
an NTM nondeterministically produces a correct solution,
then verifies that this solution is correct (see figure 1).

{%
  include figure.html
  name="figure_1"
  caption="Figure 1. A generic NTM for a problem in NP."
%}

If you believe that $$NP$$ represents human creativity this model can feel dissatisfying,
because it hides that
creativity within the impenetrable black-box of the nondeterministic
solution creator. The solution creator simply produces the correct solution, and that's that.
The question of how a correct solution is actually generated has no place.

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
increased our understanding of the mechanics of miraculously complex natural
phenomena, including the human brain. So embracing our
naivet&eacute; for the moment, we can ask whether it's possible to narrow
the gap between the abstraction of nondeterminism and our emerging understanding of the
natural phenomena it is meant to model.

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
You can find informative descriptions of emergence in biology
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

The rest of this post is an attempt to frame nondeterminsitic computation
in these terms; as a system of simple,
myopic computational entities where the "magic" of nondeterminism is not in
the entities themselves but in their interactions.


### Biomorphic Nondeterminism

We want to design a nondeterminstic Turing machine that exhibits the properties described above.
Imagine that we're solving some [decision problem](https://en.wikipedia.org/wiki/Decision_problem), in other
words given some input we want our NTM to answer a yes/no question about it by either accepting or rejecting
the input, respectively.
At a high level, our NTM will consist of a network of deterministic verifiers that can communicate
with each other, where each only has access to a small piece of the input.
Instead of nondeterminism being used to produce a solution in a black-box
fashion as in figure 1, nondeterminism will only be used to decide which
deterministic verifiers communicate with each other - see figure 2.

{%
  include figure.html
  name="figure_2"
  caption="Figure 2. A network of interacting deterministic verifiers. The choice of which verifiers can communicate is made nondeterministically. "
%}

Let's attempt a more formal definition.
Borrowing language from [this survey](https://queue.acm.org/detail.cfm?id=1016985),
we'll describe the biologically-inspired formulation sketched above as _biomorphic_.

A biomorphic nondeterministic Turing machine (BNTM) for a decision problem
works as follows for a problem instance $$X$$:
1. The BTNM instantiates a set of verifier nodes $$V = (v_1, v_2, ..., v_n)$$, each
a deterministic Turning machine, and a set $$E$$ of directed edges on $$V$$;
we'll call $$(V, E)$$ the _base graph_.
2. The BTNM distributes a constant-sized piece $$X_i$$ of the problem instance
to each verifier node $$v_i$$.
3. The BNTM nondeterministically selects a subset $$E^* \subseteq E$$;
we'll call $$(V, E^*)$$ the _message graph_.
4. Each verifier $$v_i$$ performs a computation on $$X_i$$ and sends the
result to every $$v_j$$ where $$v_i \to v_j$$ is an edge in the message graph.
5. Each $$v_i$$ performs another computation on all messages it receives,
and sends the result again along all edges in the message graph that extend from $$v_i$$.
6. After repeating step 5 for some number of rounds, each $$v_i$$ performs a final
computation that determines whether it accepts or rejects. The problem instance
$$X$$ is accepted if the number of accepting verifiers exceeds a certain threshold.

To restate less formally, a BNTM for a decision problem works by instantiating
a base graph
whose nodes are deterministic local verifiers that only have knowledge of a
constant-sized piece of the problem instance. The BNTM nondeterministically
chooses a subset of edges, which defines a subgraph of the base graph
(the message graph). The local verifiers send messages to each other
along the the edges in the message graph. The local verifiers perform (deterministic) computations
on their local piece of the problem instance as well as the messages received
from other verifiers. After a few rounds of computation and communication,
each verifier accepts or rejects, and the problem instance is accepted if
enough verifiers accept individually.

Before giving some examples of BNTMs, a few comments on the definition.

notes: nondeterminism isolated; oblivious messages; polynomial size; local knowledge; sync vs async; threshold



{%
  include figure.html
  name="figure_3"
  caption="Figure 3. Biomorphic determinism with a global verifier is equivalent to classical nondeterminism."
%}









### Examples





### Final Thoughts

Prior art: Nick's class, actor model

Reflection on Google team dynamics study


### Appendix: 3SAT



### ** Scratch pad **

