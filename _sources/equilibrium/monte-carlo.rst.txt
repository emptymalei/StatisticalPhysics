Monte Carlo Method
======================

We use Monte Carlo method to "fake" a system that obays a specific distribution so that we could use it as samples of such a distribution.


Monte Carlo Method for Ising Model
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
---------------------------------------


