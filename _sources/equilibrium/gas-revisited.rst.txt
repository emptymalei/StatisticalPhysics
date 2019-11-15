Gas Revisited
====================

Van der Waals Gas
------------------------

The ideal gas model is simple yet not realistic in many cases. Since the ideal gas model ignores the interactions between the gas molecules, it only applies to sparse gas.

The van de Waals model adds two new elements to the ideal gas model: molecules size and interaction potential. It deals with the correction in pressure and volume. The equation of state writes

.. math::
   (P + a n^2/V^2)(V- n b) = n R T

for :math:`n` moles of gas.

1. We have introduced :math:`nb` because molecules are not point particles. In the van der Waals model, we assume that the molecules are incompressible hard balls. Here the variable :math:`b` is related to the size of the molecules. In the Lenard-Jones potential model, :math:`b` is 4 times the size of all molecules.
2. We have the term :math:`a n^2/V^2` because molecules will attract to each other when they get too close. In fact, the attractive potential makes it possible for phase transition, a.k.a., condensation of gas molecules.

The van der Waals model is essentially a mean field theory which averages out the higher orders of potentials. We could expand the van der Waals gas law using Taylor series,

.. math::
   P = \frac{n R T}{V} \left[ 1 + \frac{n}{V} B(T) + \left(\frac{n}{V}\right)^2 C(T) + \cdots \right]

The coefficients can be derived using virial potential or cluster expansion.


.. admonition:: Why is Harmonic Oscillator so Popular in Physics
   :class: note

   More specifically, we write down an abstract Hamiltonian

   .. math::
      \mathscr H = \sum \frac{\vec p_i^2}{2m} + \sum _ {\langle i,j \rangle} \phi(r_{ij})

   as

   .. math::
      \mathscr H = \sum \frac{\vec p_i^2}{2m} +  \sum _ {\langle i,j \rangle} \phi(r)

   in which :math:`\phi(r)` is the average of potential and all particles interaction have the same value.
