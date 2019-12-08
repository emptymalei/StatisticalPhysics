.. _most-probable-distribution:

Most Probable Distribution
==================================

.. admonition:: Applications of Most Probable Distribution
   :class: note

   Application of most probable distribution is discussed in :ref:`summary-boltzmann-statistics`.

In Boltzman distribution, one of the key ingredients is the most probable distribution. First things first, the most probable distribution is indicating the distribution that is most probable. On the other hand, we also talked about the probability of the microstates. It is crucial to understand the difference between distribution and microstates.

Microstates describes the configurations of the system which is the most detailed view of the system in statistical physics. However, a distribution of the system describes the number of particles on each energy levels of the particle.



.. _equal-a-prior-probability:

Equal A Prior Probability
------------------------------------


.. admonition:: Equal A Prior Probability
   :class: warning

   For systems with enormous number of particles, we observe their macroscopic properties such as energies, pressure in experiments. But we have very limited information about the internal structure. The principle proposed by Boltzmann is that all these different possible configurations of microstructure are equally distributed, a.k.a., principle of equal *a prior* probabilities.


An Example of Calculations
----------------------------

.. admonition:: This is Only an Example for the Calculation
   :class: warning

   This example is not exactly an statistical physics problem since we do not have enough particles to make it statistically significant. For example, we use Sterling's approximation but this doesn't hold in this case.

The equal a-priori principle can be illustrated using a two-magnet system. For simplicity, we will ignore the interactions between the magnets. In the example, we use :math:`a_i` to denote the number spins on the different states,

.. math::
   \begin{cases}
   a_1 \qquad \text{Number of spins pointing downward}, \\
   a_2 \qquad \text{Number of spins pointing upward}
   \end{cases}

.. figure:: images/equal-a-prior-probability.png
   :align: center

   A simple system of 2 magnets in an external magnetic field. The external magnetic field is pointing upwards. The energy of the system is labelled as :math:`E` and the distributions are labelled on the right. *In principle, we could also have multiple possible distributions for the same energy of the whole system. In our case, it is simply a coincidence that we only have on distribution corresponding to each energy of the system.*

With an external magnetic field, the energy of the system is determined by

.. math::
   (s_1  + s_2) B,

where :math:`s_i=\pm 1`.

Each of the possible configuration of the the two magnets is considered as a **microstate**. That being said, the equal a-prior principle tells us that the probabilities of the four different configurations are the same. This is an effort of least information assumption.


Probabilities of Distributions
----------------------------------

In such a system, we have the following possible distributions.

.. math::
   \begin{cases}
   a_1  = 0, & \qquad \text{particles at single particle energy state } \varepsilon_1 = -\mu B \\
   a_2  = 2, & \qquad \text{particles at single particle energy state } \varepsilon_2 = \mu B
   \end{cases}

which has total energy of :math:`2\mu B` and number of microstates :math:`\Omega = 1`.

.. math::
   \begin{cases}
   a_1  = 1, & \qquad \text{particles at single particle energy state } \varepsilon_1 = -\mu B \\
   a_2  = 1, & \qquad \text{particles at single particle energy state } \varepsilon_2 = \mu B
   \end{cases}

which has total energy of :math:`0` and number of microstates :math:`\Omega = 2`.

.. math::
   \begin{cases}
   a_1  = 2, & \qquad \text{particles at single particle energy state } \varepsilon_1 = -\mu B \\
   a_2  = 0, & \qquad \text{particles at single particle energy state } \varepsilon_2 = \mu B
   \end{cases}

which has total energy of :math:`-2\mu B` and number of microstates :math:`\Omega = 1`.

According to equal a priori principle, we will have to conclude that the second distribution is the most probable distribution. Thus the observed energy of an equilibrium system of such components should be 0.


.. admonition:: Full Calculation without the Equal A-priori Principle
   :class: warning

   This result also agrees with the full calculation using the equal a-priori principle

   .. math::
      \langle E \rangle = \frac{2 \mu B + 2\times 0 - 2 \mu B}{4} = 0.

   But this is simply a coincidence.