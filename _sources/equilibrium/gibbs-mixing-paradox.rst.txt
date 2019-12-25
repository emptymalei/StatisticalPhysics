.. _gibbs-mixing-paradox:

Gibbs Mixing Paradox
==================================


Gibbs Mixing Paradox
----------------------

As mentioned in :ref:`partition_function_and_density_of_states`, we reach a paradox when mixing the many non-interacting classical particles. In classical statistical mechanics, the free energy as derived in :eq:`gibbs-mixing-paradox-free-energy-thermal-wavelength` is

.. math::
   A  = -k_B T N ( \ln V - 3 \ln \lambda_T )
   :label: gibbs-mixing-paradox-free-energy-thermal-wavelength-copy

Imagine we have two systems, one has :math:`N_1` particles and volume :math:`V_1` while the other has :math:`N_2` particles and volume :math:`V_2`. Now we mix the two systems. Our physics intuition would tell us that the free energy of this new system should be :math:`A = A_1 + A_2` since they are non-interacting particles. However, the free energy shown in :eq:`gibbs-mixing-paradox-free-energy-thermal-wavelength-copy` tells us that

.. math::
   A_{\text{mixed}} = \cdots - k_B T \ln (V_1^{N_1} V_2^{N2})

which is different from the result we expect, i.e.,

.. math::
   A = \cdots - k_B T (N_1 + N_2) \ln (V_1 + V_2) = \cdots - k_B T \ln \left(  (V_1 + V_2)^{N_1+N_2}  \right)

That is, free energy becomes neither intensive nor extensive in our theory.


To make the free energy extensive, we could choose to **divide volume by the particle number**. Then a new term will appear in the epression for free energy, i.e., :math:`N\ln N`. On the other hand, we have :math:`\ln N! = N\ln N -N` from Sterling approximation. In large systems, we can define the free energy in the following way

.. math::
   A = - k_B T N ( \ln(V/N!) - 3 \ln \lambda)

which is equivalent to

.. math::
   Z_N = \frac{Z_1^N}{N!}

This definition "solves" the Gibbs mixing paradox. The explanation of this modification requires quantum mechanics.

.. warning::
   We can't just pull out some results from statistical mechanics and apply them to a small system of a few particles. In stat mech we use a lot of approximations like Sterling approximation, many of which are only valid when particle number is huge.


