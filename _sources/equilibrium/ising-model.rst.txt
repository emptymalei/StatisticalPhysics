Ising Model
====================

Ising model is a simple and powerful model in magnetism. Given its simplicity, Ising model has been expanding to other fields of science.

As an example, we use the Ising model to describe ferromagnetic materials. It's Hamiltonian is as simple as

.. math::
   \mathscr H = - J \sum_{\langle i,j \rangle} \sigma_i \sigma_j - \mu B \sum_{i} \sigma_i.

where :math:`- J \sum_{\langle i,j \rangle} \sigma_i \sigma_j` is energy of the magnetic moment self-interactions, and the second term :math:`- \mu B \sum_{i} \sigma_i` is the energy of the magnet moments and the external field :math:`B`.

With the above Hamiltonian, we can write down the partition function from which we derive all the thermodynamic observables, in principle. For example, we are quite interested in solving the order parameters such as the average spin :math:`\langle s \rangle` so we could infer from this the phase transitions.

Ising model can be analytically and exactly solved in 1D easily and in 2D with some tricks. However, it becomes hard to solve exactly in 3D. We turn to approximations and numerical methods for help. One example of approximations is the :ref:`mean-field-theory`, while the Monte Carlo method is the famous numerical method.


Monte Carlo Method for Ising Model
----------------------------------------

The idea behind the Monte Carlo method is to fake a system that obays a specific distribution. In our case, we would like to have the system stay close to the Boltzman distribution,

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





Refs & Notes
---------------

1. Reichl, L., A Modern Course in Statistical Physics.
2. `Murthy, K. P. N. (2001). An Introduction to Monte Carlo Simulation of Statistical physics Problem. <http://arxiv.org/abs/cond-mat/0104167>`_