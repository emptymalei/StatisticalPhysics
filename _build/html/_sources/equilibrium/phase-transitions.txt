Phase Transitions
========================



Phase Transitions
------------------

a link `here <http://jfi.uchicago.edu/~leop/TALKS/Perimeter%20Stat%20Mech%20Lectures/lectures%20in%20PDF/Part%207%20Mean%20Field%20Theory.pdf>`_.

Phase transitions are properties of infinite systems.



.. mean-field-theory::

Mean Field Thoery
-------------------

More is the same.


.. note::
   Why is this an approximation?
   Because the actual magnetic field for example is often not the average of all the magnetic dipoles.

Mean field theory often fails at the critical points that is mean field theory is not precise enough for phase transition in some low dimensional systems. This gives us a very interesting thought.

.. important::
   Why does mean field theory work? From the view of mathematics, potential can always be expanded at some value which is exactly the mean value of the field. For an Hamiltonian,

   .. math::
      H = - \sum _{\langle i,j \rangle} J^{ij} \sigma_i \sigma_j - \mu \sum_i h^i \sigma_i

   Mean field treatment is

   .. math::
      H = - \sum _{\langle i,j \rangle} J^{ij} \sigma_i \sigma - \mu \sum_i h^i \sigma_i

   where :math:`\sigma = \sum_i \sigma_i/N` is the average spin configuration.

   This looks just like we take the 0 order of spin configuration expansion. And we can also include the second order which means add the interaction of just two spins.





.. note::
   Susceptibility is a parameter that shows how much an extensive parameter changes when an intensive parameter increases. Magnetic susceptibility is

   .. math::
      \chi(T)= \frac{\mathrm d M(T)}{\mathrm T}


.. important::
   What makes the phase transition in such a system? Finite system has no phase transitions because finite continuous function can only make up continuous function by addition. Phase transition happens when the correlation length becomes infinite. So this is all about correlations.


.. important::
   Why is mean field theory an approximation? Because the actual spin is more or less different from the average of spin configuration. Fluctuations in the spin makes the difference.


.. van-der-waals-gas::

Van der Waals Gas
------------------------

Ideal gas is the simplest. Van de Waals model considers the correction in pressure and volume.

.. math::
   (P + a n^2/V^2)(V- n b) = n R T

for n mole gas.

1. :math:`nb` is because molecules are not point particles, they take up space. In Lenard-Jones potential model, b is 4 times the size of all molecules.
2. :math:`a n^2/V^2` is because in this model molecules will attract to each other when they get too close. This attractive force makes it possible to have phase transition, condensation of gas molecules.

This models, is basically a kind of mean field theory which treats the corrections as a mean field. More specifically, we write the original Hamiltonian

.. math::
   H = \sum \frac{\vec p_i^2}{2m} + \sum _ {\langle i,j \rangle} \phi(r_{ij})

as

.. math::
   H = \sum \frac{\vec p_i^2}{2m} +  \sum _ {\langle i,j \rangle} \phi(r)

in which :math:`\phi(r)` is the average of potential and all particles interaction have the same value.


Onnes used series to write the equation of state,

.. math::
   P = \frac{n R T}{V} \left[ 1 + \frac{n}{V} B(T) + \left(\frac{n}{V}\right)^2 C(T) + \cdots \right]

This can be derived using Mayer function and cluster expansion.


Ensemble
----------------

A standard procedure of solving mechanics problems, said by Prof. Kenkre which is don't really accept, is

Initial condition / Description of states -> Time evolution -> Extraction of observables


States
~~~~~~~~~~~~~~~~~~~~~~~

**Density of states in phase space**

Continuity equation

.. math::
   \partial _ t \rho + \nabla \cdot (\rho \vec u) =0

This conservation law can be more simpler if dropped the term :math:`\nabla\cdot \vec u = 0` for incompressibility.

Or more generally,

.. math::
   \partial _ t \rho + \nabla \cdot \vec j = 0

and here :math:`\vec j` can take other definitions like :math:`\vec j = - D \partial_x \rho`.


This second continuity equation can represent any conservation law provided the proper :math:`\vec j`.


.. important::
   From continuity equation to Liouville theorem:

   We start from

   .. math::
      \frac{\partial}{\partial t} \rho + \vec \nabla \cdot (\rho \vec v)

   Divergence means

   .. math::
      \vec \nabla \cdot  = \sum_i \left( \frac{\partial}{\partial q_i} + \frac{\partial}{\partial p_i} \right) .

   Then we will have the initial expression written as

   .. math::
      \frac{\partial}{\partial t} \rho + \sum_i \left( \frac{\partial}{\partial q_i} (\rho \dot q_i) + \frac{\partial}{\partial \dot p_i} \right) .

   Expand the derivatives,

   .. math::
      \frac{\partial}{\partial t} \rho + \sum_i \left[  \left( \frac{\partial}{\partial q_i} \dot q_i + \frac{\partial}{\partial p_i} \dot p_i\right) \rho +  \dot q_i \frac{\partial}{\partial q_i} \rho  + \dot p_i \frac{\partial}{\partial p_i} \rho  \right]   .

   Recall that Hamiltonian equations

   .. math::

      \dot q_i  = \frac{\partial H}{\partial p_i}

      \dot p_i = - \frac{\partial H}{\partial q_i}

   Then

   .. math::
      \left( \frac{\partial}{\partial q_i} \dot q_i + \frac{\partial}{\partial p_i} \dot p_i\right) \rho  .

   Finally convective time derivative becomes zero because :math:`\rho` is not changing with time in a comoving frame like perfect fluid.

   .. math::
      \frac{d}{d t} \rho \equiv  \frac{\partial}{\partial t}\rho + \sum_i \left[ \dot q_i \frac{\partial}{\partial q_i} \rho  + \dot p_i \frac{\partial}{\partial p_i} \rho \right] =0




Time evolution
~~~~~~~~~~~~~~~~~~~~~

Apply Hamiltonian dynamics to this continuity equation, we can get

.. math::
   \partial_t \rho = \{H, \rho\}

which is very similar to quantum density matrix operator

.. math::
   \mathrm i \hbar \partial_t \hat \rho = [ \hat H, \hat \rho ]


That is to say, the time evolution is solved if we can find out the Poisson bracket of Hamiltonian and probability density.


Requirements for Liouville Density
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. Liouville theorem;
2. Normalizable;

   .. hint::
      What about a system with constant probability for each state all over the phase space? This is not normalizable. Such a system can not really pick out a value. It seems that the probability to be on states with a constant energy is zero. So no such system really exist. I guess?

      Like this?

      .. image:: images/sandiaPeaks.png
         :scale: 90%
         :align: center

      Someone have 50% probability each to stop on one of the two Sandia Peaks for a picnic. Can we do an average for such a system? **Example by Professor Kenkre.**



And one more for equilibrium systems, :math:`\partial_t \rho =0`.




Extraction of observables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

It's simply done by using the ensemble average

.. math::
   \avg{O} = \int O(p_i; q_i;t) \rho(p_i;q_i;t) \sum_i dp_i dq_i dt

where :math:`i=1,2,..., 3N`.
