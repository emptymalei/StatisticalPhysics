Equilibrium Statistical Mechanics Summary
================================================

Here is the framework of lectures for the first six weeks. This part is a review of equilibrium statistical mechanics.


Review of Thermodynamics
--------------------------------------------------

1. Description of States: thermodynamics quantities;
2. Kinematics: Equation of state; `Thermodynamic potential <../vocabulary/vocabulary.html#thermodynamic-potentials>`_

   .. figure:: ../vocabulary/images/thermodynamicPotentials.png
      :align: center
      :width: 100%

      The relationship between different thermodynamic potentials. There are three different couplings and five different potentials. For more details please read vocabulary :ref:`thermodynamical-potentials` .

3. First principles: `The laws of four <../vocabulary/vocabulary.html#the-laws-of-four>`_
4. Dynamics: Phase transition; Stability; Response


The Two Approaches of Statistical Mechanics
---------------------------------------------

Two approaches utilize most probable distribution and ensemble respectively. However they have something in common.

1. Phase space
2. Liouville equation


.. figure:: images/BoltzmannVSGibbs.png
   :align: center
   :width: 100%

   A UML modeling of the two theories. Refer to `Important box in week 6 <week6.html#most-probable-distribution>`_


Boltzmann Statistics
~~~~~~~~~~~~~~~~~~~~~~~


1. Two postulates: One is about state occurrence in phase space; The other is about which state will the equilibrium system stay at.
2. Boltzmann factor (which is kind of derived from Gibbs micro-ensemble theory)
3. Partition function

   1. Density of state :math:`g(E)` ;
   2. Partition function :math:`Z = \int g(E) \exp(-\beta E) \mathrm dE`; Variable of integration can be changed;
   3. Systems of 3N DoFs :math:`Z = Z_1^{3N}`.

4. Observable

   0. Assumptions about free energy :math:`A = - k_B T\ln Z`; Combine this with thermodynamics potential relations we can calculate entropy then everything.
   1. Internal energy :math:`U = \avg{E} = - \partial_\beta \ln Z`; All quantities can be extracted from partition function except those serve as variables of internal energy.
   2. Heat capacity :math:`C = \partial_T U`



Gibbs Ensemble Theory
~~~~~~~~~~~~~~~~~~~~~~~~~


1. Ensembles
2. Density of states; Liouville equation; Von Neumann equation
3. Equilibrium
4. Three ensembles
5. Observables


Boltzmann Factor
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Boltzmann factor appears many times in thermodynamics and statistical mechanics. In Boltzmann's most probable theory, ensemble theory, etc.



Applications of These Theories
-------------------------------

Oscillators
~~~~~~~~~~~~~~~~~~

Theories of chains of oscillators in different dimensions are very useful. In fact the fun thing is, most of the analytically solvable models in physics are harmonic oscillators.

A nice practice for this kind of problem is to calculate the heat capacity of diatom chain. A chain of N atom with alternating mass M and m interacting only through nearest neighbors.

The plan for this problem is

1. Write down the equation of motion for the whole system;
2. Fourier transform the system to decouple the modes (by finding the eigen modes);
3. Solve the eigen modes;
4. Calculate the partition function of each mode;
5. Sum over each mode.

Problem is, we usually can not solve the problem exactly. So we turn to Debye theory. Debye theory assumes continuous spectrum even though our boundary condition quantizes the spectrum. So we need to turn the summation into integration using DoS using any of the several ways of obtaining DoS. Finally we analyze the different limits to get the low temperature or high temperature behavior.



.. hint::
   Here are several methods to obtain DoS. **To do!**




Heat Capacity
~~~~~~~~~~~~~~

1. Classical theory: equipartition theorem;
2. Einstein theory: all modes of oscillations are the same;
3. Debye theory: difference between modes of oscillations are considered.


Gibbs Mixing Paradox
~~~~~~~~~~~~~~~~~~~~~

:ref:`gibbs-mixing-paradox` is important for the coming in of quantum statistical mechanics.



Mean Field Theory
~~~~~~~~~~~~~~~~~~

:ref:`mean-field-theory` is the idea of treating interaction between particles as interactions between particles and a mean field.



Van der Waals Gas
~~~~~~~~~~~~~~~~~~

:ref:`van-der-waals-gas` can be derived using Mayer expansion and Leonard-Jones potential.
