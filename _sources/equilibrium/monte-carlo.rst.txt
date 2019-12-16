.. _monte-carlo-method:

Monte Carlo Method
======================

We use Monte Carlo method to "fake" a system that obays a specific distribution so that we could use it as samples of such a distribution.

Why Not Just Randomly Sample from All States
----------------------------------------------------

In statistics, the `curse of dimensionality <https://en.wikipedia.org/wiki/Curse_of_dimensionality>`_ has been haunting us. In Ising model, the number of dimension is the number of spins. In such a high dimensional system, sampling the representative states requires a huge sample.

.. admonition:: Curse of Dimensionality: Volume of 20D Ball
   :class: toggle

   It can be shown with a simple random sampling method to calcuate the volume of a 20 dimensional ball of unit length diameter.

   To calculate the volume of this 20D ball, we construct a 20D box that contains the ball. Then we place random points in the box. Suppose we have :math:`N_b` points out of :math:`N` points falling inside the ball, the volume of the ball can be approximated by :math:`N_b/N`.

   It may sound simple. However, one would realize that a good approximation requires a huge amount of sample points.


For our Ising model, randomly sampling the states means we are have a very high temperature that the probability of all enegy states are of no difference. Instead of such random sampling, we could make use of our theoretical knowledge of the Boltzman distribution and sample according to the Boltzman distribution, which is importance sampling in statistics.


Metropolis Algorithm for Ising Model
----------------------------------------

To solve the classical Ising model on a 2D grid, we would like to force the system to stay close to the Boltzman distribution,

.. math::
   P(E) = \frac{e^{-E/k_B T}}{Z} \propto e^{-E/k_B T},

where :math:`E` is the energy and :math:`Z` is the partition function.

On a 2D grid, the energy :math:`E` of all the spin is determined by the configuration of the spins (the microstates) :math:`\mathscr M`, i.e., :math:`E =  E(\mathscr M)`.

Given all the possible configurations of Ising model, we calculate observable in the following way,

.. math::
   \langle O \rangle   = \frac{ \sum_{\mathscr M} O(\mathscr M) \frac{e^{-E(\mathscr M)/k_B T}}{Z} }{ \sum_{\mathscr M} \frac{e^{-E(\mathscr M)/k_B T}}{Z} }.

For a Ising model with :math:`N` spins, we have :math:`2^N` possible configurations for the spins. It quickly becomes an impossible mission as the number of spins increases.

In statistics, we could estimate the average of quantities using sampling methods. There is no need to exhaust the whole population. W randomly choose some configurations, :math:`\{\mathscr M_i\}` and calculate the observables using this sample.

.. admonition:: Importance Sampling
   :class: warning

   There is always a catch. We also have the curse of high dimensions. Random sampling becomes inefficient in high dimensions. To achive a reasonably good result, we have to sample a huge amount of configurations. To solve this problem, the glory importance sampling was invented.

In Monte Carlo method, we will generate some configurations and use those configurations to calculate our ensemble average of observables.


State Transitions and Markov Chain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To simulate the system, we will construct a series of history independent transitions between the states,

.. math::
   \cdots \to \sigma_i \to \sigma_{i+1} \to \sigma_{i+2} \to \cdots

We will use a lowest order approximation and require the transition probability :math:`P(\sigma_{i+1} \vert \sigma_i)` to the next state :math:`\sigma_i` only depends on the current state :math:`\sigma_{i+1}`.

Imagine we force a rule upon the transition probabilities, the states will be close to a path that is defined by the rule. This rule shall be the Boltzman distribution.

Metropolis Algorithm
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Metropolis algorithm is a Monte Carlo method for sampling. We will calculate the energy :math:`\langle E \rangle` and magnetization :math:`\langle M \rangle` of the equilibrium Ising model. The specific heat and magnetic susceptibility can be calculated using the energy and magnetization.


To demonstrate the algorithm, we use a 2D N by N lattice of magnetic spins.

.. figure:: images/metropolis-algorithm-flowchart.png
   :alt: Metropolis algorithm
   :align: center

   Metropolis algorithm

.. admonition:: Flowchart Code
   :class: toggle

   `Here <https://mermaidjs.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZ3JhcGggVERcbkFbSW5pdGlhbGl6ZSBsYXR0aWNlIHNwaW5zIHJhbmRvbWx5XSAtLT4gQihyYW5kb21seSBmbGlwIGEgc3BpbilcbkIgLS0-IEN7XCJJcyDiiIZFIDwgMCA8YnI-IG9yIDxicj4gZXhwKC3iiIZFL2JldGEpID4gcmFuZG9tIG51bWJlciBbMCwxXVwiIH1cbkMgLS0-fFRydWV8IEQoQWNjZXB0IGZsaXApXG5DIC0tPnxGYWxzZXwgRihSZWplY3QgZmxpcClcbkQgLS0-IEp7XCJJcyBlcXVpbGlicml1bVwifVxuRiAtLT4gSntcIklzIGVxdWlsaWJyaXVtXCJ9XG5KIC0tPiB8RmFsc2V8IEJcbkogLS0-IHxUcnVlfCBLW1wiQ29sbGVjdGVkIGRhdGEgYW5kIGNhbGN1bGF0ZSBvYnNlcnZhYmxlc1wiXVxuXG4iLCJtZXJtYWlkIjp7InRoZW1lIjoibmV1dHJhbCJ9fQ>`_ `is <https://mermaidjs.github.io/mermaid-live-editor/#/view/eyJjb2RlIjoiZ3JhcGggVERcbkFbSW5pdGlhbGl6ZSBsYXR0aWNlIHNwaW5zIHJhbmRvbWx5XSAtLT4gQihyYW5kb21seSBmbGlwIGEgc3BpbilcbkIgLS0-IEN7XCJJcyDiiIZFIDwgMCA8YnI-IG9yIDxicj4gZXhwKC3iiIZFL2JldGEpID4gcmFuZG9tIG51bWJlciBbMCwxXVwiIH1cbkMgLS0-fFRydWV8IEQoQWNjZXB0IGZsaXApXG5DIC0tPnxGYWxzZXwgRihSZWplY3QgZmxpcClcbkQgLS0-IEp7XCJJcyBlcXVpbGlicml1bVwifVxuRiAtLT4gSntcIklzIGVxdWlsaWJyaXVtXCJ9XG5KIC0tPiB8RmFsc2V8IEJcbkogLS0-IHxUcnVlfCBLW1wiQ29sbGVjdGVkIGRhdGEgYW5kIGNhbGN1bGF0ZSBvYnNlcnZhYmxlc1wiXVxuXG4iLCJtZXJtYWlkIjp7InRoZW1lIjoibmV1dHJhbCJ9fQ>`_ the mermainjs link.

   .. code-block:: text

      graph TD
      A[Initialize lattice spins randomly] --> B(randomly flip a spin)
      B --> C{"Is ∆E < 0 <br> or <br> exp(-∆E/beta) > random number [0,1]" }
      C -->|True| D(Accept flip)
      C -->|False| F(Reject flip)
      D --> J{"Is equilibrium"}
      F --> J{"Is equilibrium"}
      J --> |False| B
      J --> |True| K["Collected data and calculate observables"]



`This GitHub repository <https://github.com/emptymalei/ising-model>`_ is my working example of this algorithm for Ising model.




References
--------------------------

1. `Monte Carlo Simulations in Statistical Physics -- From Basic Principles to Advanced Applications by Janke, Wolfhard. <https://ui.adsabs.harvard.edu/abs/2013odca.book...93J/abstract>`_