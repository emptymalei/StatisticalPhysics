Gas Revisted
====================

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


