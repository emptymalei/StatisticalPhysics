Ensembles
============


The problem in statistical mechanics is that we can only use partial information of the system, thus we could expect partial results to be obtained sometimes. In the language of statistics, we have been using a lot of assumptions on the population as well as the samplig methods.

From a macroscopic point of view, thermodynamic observables do not tell us about the microstates. We using the contimiuum in the phase space, aka, the phase space distributions, to represent the internal stuctures of the system. Apart from the question of why equilibrium even exists, equilibrium tells us that this density doesn't change. In Boltzmann's theory, we are using equal-a-prior probability as the probability of the microstates and most probable distribution to calculate our thermodynamic observales. With this, we are assuming that the system to dynamically moving in the phase space but is close to most probable distribution most of the time. With this assumption, we will observe little fluctuations of macroscopic observables since the most probable distribution is a delta-like distribution.

On the other hand, we could also use ensemble methods. Instead of collecting statistical sampling on the microstates in time dimension, we make virtual copies of the system so that we sample among these virtual copies.

.. admonition:: Ensemble Methods in Machine Learning
   :class: note

   In the field of machine learning, ensemble methods have been quite popular. They reduce the problems to the very fundations of statistics which makes them generalizable.


.. index:: Ensemble

Ensemble
----------------

Gibbs' idea of ensemble is to create copies of the system with the same thermodynamics quantities.

The question is how the copies are created. Are they in different time of the system or simply different systems?

We can create a huge amount copies of the system and imagine that they are at different place. Then we have all the possible states of the system.

We can also wait infinite long time and all possible states will occur, at least for some system, which is called ergodic. Ergodic means the system can visit all possible states many times during a long time. This is rather a hypothesis than a theorem.

The problem is, not all systems are ergodic. For such systems, of course, we can only do the ensemble average.


.. note::

   **Cons**

   1. Not possible to prove ensemble average is the same as time average. In fact some systems don't obey this rule.
   2. Not possible to visit all possible states on constant energy surface in finite time.
   3. Even complicated systems can exhibit almost exactly periodic behavior, one example of this is `FPU experiment <https://en.wikipedia.org/wiki/Fermi%E2%80%93Pasta%E2%80%93Ulam_problem>`_ .
   4. Even the system is ergodic, how can we make sure each state will occur with the same probability.


   Here is an example of non ergodic system:

   .. image:: images/non-ergodic.png
      :alt: An example of non ergodic system
      :align: center


   This is a box of absolutely smooth with balls collide with walls perpendicularly. Then this system can stay on some discrete points with same values of momentum components.

   Another image from `Wikipedia <https://commons.wikimedia.org/wiki/File:Ergodic_hypothesis_w_reflecting_rays.jpg>`_ :

   .. image:: images/Ergodic_hypothesis_w_reflecting_rays.jpg
      :alt: ergodic system
      :scale: 90%
      :align: center



.. note::

   **Pros**

   1. `Poincaré recurrence theorem <https://en.wikipedia.org/wiki/Poincar%C3%A9_recurrence_theorem>`_ proves that at least some systems will come back to a state that is very close the the initial state after a long but finite time.
   2. Systems are often chaotic so it's not really possible to have pictures like the first one in Cons.


.. admonition:: Poincare Recurrence Theorem
   :class: note

   There is a very interesting paper regarding the recurrence theorem.

   `Dyson, F. J., & Falk, H. (1992). Period of a Discrete Cat Mapping. The American Mathematical Monthly, 99(7), 603. <https://doi.org/10.2307/2324989>`_



We already have Liouville density evolution

.. math::
   \frac{\partial}{\partial t} \rho = \{ H, \rho \}

Von Neumann equation

.. math::
   i\hbar \frac{\partial}{\partial t} \hat\rho = [\hat H, \hat\rho ]

In all, they can be written as

.. math::
   i \frac{\partial\rho}{\partial t} = \hat L \rho

where :math:`\hat L` is the Liouville operator.


We have mentioned that ensembles have the same thermodynamic quantities. In the language of math,

.. math::
   \avg{o} = \mathrm{Tr} \rho O

All we care about is the left hand side. So as long as :math:`\rho` is not changed, we can stir the system as crazy as we can and keep the system the same.

.. hint::
   Only one trace in phase space is true. How can we use ensemble to calculate the real observables?

   Actually, what we calculated is not the real observable. What we calculated is the ensemble average. Since we are dealing with equilibrium, we need the time average because for equilibrium system, time average is the desired result. (Fluctuations? yes but later.) As we discussed previously, for ergodic systems, ensemble average is the same as time average.


Equilibrium
-------------

What does equilibrium mean exactly?

.. math::
   \frac{\partial}{\partial} \rho  = 0

or equivalently,

.. math::
   \{ H, \rho \} =0

Obviously, one possible solution is

.. math::
   \rho \propto e^{-\beta H}




Ensembles, Systems
------------------------------


.. table:: Ensembles and systems

   =================================  ======================================  ======================================  ======================================
     Systems                             Ensembles                               Geometry in Phase space                 Key Variables
   =================================  ======================================  ======================================  ======================================
     Isolated                            Microcanonical                          Shell; :math:`\rho = c'\delta(E-H)`    Energy :math:`E`
     Weak interacting                 Canonical
     Exchange particles                  Grand canonical
   =================================  ======================================  ======================================  ======================================




.. index:: Microcanonical Ensemble

Isolated System - Micro-canonical Ensemble
------------------------------------------

.. image:: images/microcanonical.png
   :alt: UML of micro-canonical
   :align: center

.. math::
   \rho(p;q;0) = \delta(H(p;q;0) - E)

That is the system stays on the energy shell in phase space. Also we have for equilibrium system,

.. math::
    H(p;q;t) = E

.. hint::
   Is it true that ensemble average is equal to the actual value of the system?

   Not for all classical systems. (But for ALL quantum systems? Not sure.)



Ergodic Hypothesis Revisited
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

For ergodic systems, ensemble average is equal to time average.

.. important::
   How about state of the system moving with changing speed on the shell? Then how can we say the system is ergodic and use ensemble average as time average?



Micro canonical ensembles are for isolated systems.

.. math::
   \rho \propto \frac{1}{\text{No. of states on the ensemble surface}} \equiv \frac{1}{\Omega (E)}


To calculate the entropy

.. math::
   S = k_B \ln \Omega



.. index:: Canonical Ensemble

Canonical Ensemble
--------------------------

.. image:: images/canonicalEnsemble.png
   :alt: Canonical Ensemble
   :align: center



For a system weakly interacting with a heat bath, total energy of the system is

.. math::
   E_T = E_S + E_R + E _{S,R}

where the interacting energy :math:`E` is very small compared to :math:`E_1\ll E_2`. So we can drop this interaction energy term,

.. math::
   E_T = E_S + E _R

A simple and intuitive derivation of the probability density is to use the theory of independent events.

1. :math:`\rho_T d\Omega_T`: probability of states in phase space volume :math:`d\Omega_T`;
2. :math:`\rho_S d \Omega_S`: probability of states in phase space volume :math:`d\Omega_S`;
3. :math:`\rho_R d \Omega_R`: probability of states in phase space volume :math:`d\Omega_R`;

We assumed weak interactions between system and reservoir, so (approximately) the probability in system phase space and in reservoir phase space are independent of each other,

.. math::
   \rho _ T d\Omega_T = \rho _S d\Omega_S \cdot \rho _R d \Omega_R .

Since there is no particle exchange between the two systems, overall phase space volume is the system phase space volume multiplied by reservoir phase space volume,

.. math::
   d\Omega_T = d\Omega _S \cdot d\Omega_R .

Obviously we can get the relation between the three probability densities.

.. math::
   \rho_T = \rho_R \rho_S .

Take the logarithm,

.. math::
   \ln\rho_T = \ln\rho_R + \ln\rho_S .

**Key: :math:`\rho` is a function of energy :math:`E`. AND both :math:`\rho` and energy are extensive. The only possible form of :math:`\ln \rho` is linear.**

Finally we reach the destination,

.. math::
   \ln \rho = - \alpha - \beta E

i.e.,

.. math::
   \rho = e^{-\alpha} e^{-\beta E}

which is called **canonical distribution**.

.. warning::
   This is not an rigorous derivation. Read R.K. Su's book for a more detailed and rigorous derivation.




.. index:: Grand Canonical Ensemble

Grand Canonical Ensemble
---------------------------

Systems with changing particle number are described by grand canonical ensemble.

.. image:: images/grandCanonical.png
   :alt: Grand Canonical Ensemble
   :align: center




Note that the partition function of grand canonical ensemble really is

.. math::
   Z = \sum _ n \sum_N  e^{-\beta E_n - \mu N} = \sum_N \left( \sum _ n e^{- \beta E _ n}  \right)\left(e^{-\mu}\right)^N = \sum _ N Z \left(Z^f\right)^N




.. index:: Identical Particles

Identical Particles
--------------------

If a system consists of N indentical particles, for any state :math:`n_i^\xi` particles in particle state i, we have the energy of the system on state :math:`\xi` is

.. math::
   E^\xi = \sum_i \epsilon_i n_i^\xi

where the summation is over all possible states of particles.

The value of energy is given by ensemble value

.. math::
   \avg{E} = \frac{\sum _\xi e^{-\beta E^\xi} E^\xi}{\sum _\xi e^{-\beta E^\xi}}

:math:`\xi` is the ensemble summation.

.. hint::
   How to calculate the average number of particles on a particle state i?




Three Ensembles Cont'd
----------------------------------------------




The three ensembles are the same when particle number N is really large, :math:`N\rightarrow 0` .

The reason is that

1. when N becomes really large, the interaction between system and reservoir becomes really negligible. The variance of Gaussian distribution is proportional to :math:`1/\sqrt{N}`.
2. :math:`dE_S+dE_R=dE` and we know :math:`dE=0` so when the energy of the system increase that of reservoir drop. Professor Kenkre have a way to prove that the energy of the system is peaked at some value. However I didn't get it.

.. warning::
   Ask him why the value is peaked.


Most Probable Distribution
---------------------------

Quite different from Gibbs' ensemble theory, Boltzmann's theory is about most probable distribution.

1. Classical distinguishable particles :math:`a_l = w_l e^{-\alpha -\beta e_l}`;
2. Bosons :math:`a_l = w_l \frac{1}{e^{\alpha+\beta e_l} - 1}`;
3. Fermion :math:`a_l = w_l \frac{1}{e^{\alpha + \beta e_l} + 1}`.

.. image:: images/mostProbableDistribution.png
   :alt: most probable distribution
   :align: center

This image tells us that the three lines converge when the factor :math:`\alpha + \beta e_l` becomes large. Also Fermions have less micro states than classical particles because of Pauli exclusive principle.


:math:`\alpha + \beta e_l` being large can have several different physical meanings.

1. Temperature low;
2. Energy high;
3. Chemical coupling coefficient :math:`\alpha` large.


We have several identical conditions for the three distribution to be the same.

.. math::
   \alpha + \beta e_l \gg 1 \Leftrightarrow \alpha \gg 1 \Leftrightarrow 1/\exp(\alpha + \beta e_l) \ll 1 \Leftrightarrow a_l / w_l \ll 1

where the last statement is quite interesting. :math:`a_l/w_l \ll 1` means we have much more states then particles and the quantum effects becomes very small.

.. warning::
   One should be careful that even when the above conditions are satisfied, the number of micro states for classical particles is very different from quantum particles,

   .. math::
      \Omega_{B.E} = \Omega_{F.D.} = \Omega_{M.B.}/N!  .

   This will have effects on entropy eventually.



Recall that thermal wavelength :math:`\lambda_t` is a useful method of analyzing the quantum effect. At high temperature, thermal wavelength becomes small and the system is more classical.

.. hint::
   1. Massive particles :math:`\lambda_t = \frac{h}{p} = \frac{h}{\sqrt{2m K}} = \frac{h}{\sqrt{ 2\pi m k T }}`
   2. Massless particles :math:`\lambda_t = \frac{c h}{2\pi^{1/3} k T}`


**However, at high temperature, the three micro states numbers are going to be very different. This is because thermal wavelength consider the movement of particles and high temperature means large momentum thus classical. The number of micro states comes from a discussion of occupation of states.**




.. important::

   What's the difference between ensemble probability density and most probable distribution? What makes the +1 or -1 in the occupation number?

   Most probable distribution is the method used in Boltzmann's theory while ensemble probability density is in ensemble theory. That means in ensemble theory all copies (states) in a canonical ensemble appear with a probability density :math:`\exp(-\beta E)` and all information about the type of particles is in Hamiltonian.

   Being different from ensemble theory, Boltzmann's theory deals with number of micro states which is affected by the type of particles. Suppose we have *N* particles in a system and occupying :math:`e_l` energy levels with a number of :math:`a_l` particles. Note that we have a degeneration of :math:`w_l` on each energy levels.

   .. image:: images/BoltzmannVSGibbs.png
      :alt: Boltzmann theory vs Gibbs theory
      :align: center

   (Gliffy source `here <_images/BoltzmannVSGibbs.gliffy>`_ .)

   For Boltzmann's theory, we need to

   1. Calculate the number of micro states of the system;
   2. Calculate most probable distribution using Lagrange multipliers;
   3. Calculate the average of an observable using the most probable distribution.

   .. admonition:: Calculation of number of micro states

      Calculation of the number of micro states requires some basic knowledge of different types of particles.

      For classical particles, we can distinguish each particle from others and no restrictions on the number of states on each energy level. Now we have :math:`w_l^{a_l}` possible states for each energy level. Since the particles are distinguishable we can have :math:`N!` possible ways of exchanging particles. But the degenerated particles won't contribute to the exchange (for they are the same and not distinguishable) which is calculated by :math:`\Pi_l a_l!`.

      Finally we have

      .. math::
         \Omega _{M.B.} = \frac{N!}{\Pi_l a_l !} \Pi_l w_l^{a_l}

      as the number of possible states.

      With similar techniques which is explicitly explained on Wang's book, we get the number of micro states for the other two types of particles.

      .. math::
         \Omega _{B.E.} = \Pi_l \frac{(a_l+w_l-1)}{a_l!(w_l -1)!}

      is the number of micro states for a Boson system with a :math:`\{a_l\}` distribution.

      .. math::
         \Omega _ {F.D.} = \Pi _ {l} C_{w_l}^{a_l} = \Pi _ l \frac{w_l!}{a_l!(w_l - a_l)!}

      is the number of micro states for a Fermion system with a distribution :math:`\{a_l\}`. We get this because we just need to pick out :math:`a_l` states for :math:`a_l` particles on the energy level.







The Exact Partition Function
-------------------------------


DoS and partition function have already been discussed in previous notes.




Is There A Gap Between Fermion and Boson?
-------------------------------------------


Suppose we know only M.B. distribution, by applying this to harmonic oscillators we can find that

.. math::
   \avg{H} = (\bar n + 1/2)\hbar \omega

where :math:`\bar n` is given by

.. math::
   \bar n = \frac{1}{e^{\beta \hbar \omega} - 1}

which clearly indicates a new type of Boson particles.

So classical statistical mechanics and quantum statistical mechanics are closely connected not only in the most micro state numbers but also in a more fundamental way.

.. hint::
   Note that this is possible because energy differences between energy levels are the same for arbitrary adjacent energy levels. Adding one new imagined particle with energy :math:`\hbar\omega` is equivalence to excite one particle to higher energy levels. So we can treat the imagined particle as a Boson particle.
