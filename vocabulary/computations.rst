Computations
===============


As one of the pilars of the modern physics, computation serves as an important role in statistical phyiscs.


Monte Carlo
-----------------------

.. warning::
   More about Monte Carlo simulations will be discussed in the following chapters.

The idea of Monte Carlo is to simulate a system with certain probability distributions.

For example, as we flip coins, we might get heads or tails. To find out the probability of getting heads, we could simply flip it a lot of times. With the help of computers, this process is even more convenient.

In statistical physics, we are interested in calculating the ensemble average of obervables. To achieve that, we generate a system with a reasonable probability distribution that is approaching the physical system. For example, we would require it to have a Boltzmann distribution.

The most popular algorithm to simulate such a system is to use Markov chain. There are many Markov chain processes that is ergodic so that it can be used in statistical physics. One of such is the Metropolis algorithm.

The steps of Monte Carlo of Metropolis.

1. Initialize the system with random states, we denote the state of the system as :math:`\mathscr S_{i}`.
2. Calculate the energy of the system, :math:`E_{i}`.
3. Change the state of one of the particles, so that the state of the system becomes :math:`\mathscr S'_{i}`.
4. Recalculate the energy of the system, :math:`E'_{i}`.
5. If the energy of the new state is lower, :math:`E'_{i}<=E_{i}`, we accept the change and say the system evolves to the state :math:`\mathscr S_{i+1} = \mathscr S'_{i}`. If :math:`E'_{i}>E_{i}`, we generate a random number between 0 and 1 :math:`p`. Then we compare :math:`p` with :math:`e^{-E'_{i}/k_B T}/e^{-E_{i}/k_B T}`. If :math:`p` is larger, we reject the change and set :math:`\mathscr S_{i+1} = \mathscr S'_{i}`. Otherwise, we accept the change and keep the state :math:`\mathscr S_{i+1} = \mathscr S_{i}`.
6. Repeat the process.


Detailed balance is the key to the update rule. When a system reaches equlibrium, we assume a detailed balance rule, i.e.,

.. math::
   P(\mathscr S_i)P(  \mathscr S_j \vert \mathscr S_i ) = P(\mathscr S_j) P(\mathscr S_i \vert \mathscr S_j),

which can be reformulated as

.. math::
   \frac{P(\mathscr S_j \vert \mathscr S_i)}{P(\mathscr S_i \vert \mathscr S_j)} = \frac{ P(\mathscr S_j) }{ P(\mathscr S_i) }.

For Boltzmann distribution, we have

.. math::
   \frac{ P(\mathscr S_j) }{ P(\mathscr S_i) } = e^{ - (E_j - E_i)/k_B T}.

For forcing the transition probability using Metropolis algorithm, we could reach an equlibrium state with Boltzmann distribution.