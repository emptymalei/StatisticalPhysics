Ising Model
====================

Ising model is a simple and powerful model in magnetism. Given its simplicity, Ising model has been expanding to other fields of science.

As an example, we use the Ising model to describe ferromagnetic materials. It's Hamiltonian is as simple as

.. math::
   \mathscr H = - J \sum_{\langle i,j \rangle} \sigma_i \sigma_j - \mu B \sum_{i} \sigma_i.

where :math:`- J \sum_{\langle i,j \rangle} \sigma_i \sigma_j` is energy of the magnetic moment self-interactions, and the second term :math:`- \mu B \sum_{i} \sigma_i` is the energy of the magnet moments and the external field :math:`B`.

With the above Hamiltonian, we can write down the partition function from which we derive all the thermodynamic observables, in principle. For example, we are quite interested in solving the order parameters such as the average spin :math:`\langle s \rangle` so we could infer from this the phase transitions.

Ising model can be analytically and exactly solved in 1D easily and in 2D with some tricks. However, it becomes hard to solve exactly in 3D. We turn to approximations and numerical methods for help. One example of approximations is the :ref:`mean-field-theory`, while the Monte Carlo method is the famous numerical method.

Phase Transitions
----------------------

Ising model is simple to solve numerically yet it provides insights in terms of many thermodynamical phenomona. Phase transitions in Ising model is one of the examples. During the phase transition, we could explicitly see the correlation length of the spins becomes infinily, or simply large in finite systems. Many techniques have been used to investigate such behaviors such as scaling, numerical methods, etc.

We will be discussing the numerical methods in the next section :ref:`monte-carlo-method`.


Refs & Notes
---------------

1. Reichl, L., A Modern Course in Statistical Physics.
2. `Murthy, K. P. N. (2001). An Introduction to Monte Carlo Simulation of Statistical physics Problem. <http://arxiv.org/abs/cond-mat/0104167>`_