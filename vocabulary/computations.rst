Computations
===============


Most problems in stat mech have similiar procedures. This page is for the programs of solving problems.


Monte Carlo
-----------------------


The steps of Monte Carlo of Metropolis.

1. Initialize
2. Change
3. Transition probability
4. Random number
5. Compare
6. Update states


Detail balance is the key to the update rule,

.. math::
   P(S_i)P(S_i \to S_j) = P(S_j) P(S_j\to S_i),

which can be rewritten as

.. math::
   \frac{P(S_i\to S_j)}{P(S_j\to S_i)} = \frac{ P(S_j) }{ P(S_i) }.

For Boltzmann distribution, we have

.. math::
   \frac{ P(S_j) }{ P(S_i) } = e^{ - (E_j - E_i)/k_B T}.
