Computations
===============


As one of the pilars of the modern physics, computation serves as an important role in statistical phyiscs.


Monte Carlo
-----------------------

The idea of Monte Carlo is to simulate a system with certain probability distributions.

For example, as we flip coins, we might get heads or tails. To find out the probability of getting heads, we could simply flip it a lot of times. With the help of computers, this process is even more convenient.

In statistical physics, we are interested in calculating the ensemble average of obervables. To achieve that, we generate a system with a reasonable probability distribution that is approaching the physical system. For example, we would require it to have a Boltzmann distribution.

The most popular algorithm to simulate such a system is to use Markov chain. There are many Markov chain processes that is ergodic so that it can be used in statistical physics. One of such is the Metropolis algorithm.

The steps of Monte Carlo of Metropolis.

1. Initialize the system with random states, we denote the state of the system as :math:`\mathscr S_{t}`.
2. Calculate the energy of the system, :math:`E_{t}`.
3. Change the state of one of the particles, so that the state of the system becomes :math:`\mathscr S'_{t}`.
4. Recalculate the energy of the system, :math:`E'_{t}`.
5. If the energy of the new state is lower, :math:`E'_{t}<=E_{t}`, we accept the change and say the system evolves to the state :math:`\mathscr S_{t+1} = \mathscr S'_{t}`. If :math:`E'_{t}>E_{t}`, we generate a random number between 0 and 1 :math:`p`. Then we compare :math:`p` with :math:`e^{-E'_{t}/kT}/e^{-E_{t}/kT}`. If :math:`p` is larger, we reject the change.
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
