Observables and Debye Model
==========================================



Observables & Equilibrium
---------------------------


Average of an observable is

.. math::
   O = Tr(\hat O \rho)

where :math:`\rho` is the "probability matrix". In QM, this is

.. math::
   \rho = \frac{ e^{-\beta H} }{\mathrm{Tr} ( e^{-\beta H} ) }


If a system of QM comes to equilibrium, that means

1. :math:`\rho  = \frac{ e^{-\beta H} }{\mathrm{Tr} e^{-\beta H} }`;
2. :math:`\rho` is diagonal in energy eigen space.




.. _gibbs-mixing-paradox:

Gibbs Mixing Paradox
----------------------



As we already know, from math of classical statistical mechanics, free energy

.. math::
   A  = -k_B T N ( \ln V - 3 \ln \lambda )

Suppose we have two systems, one with :math:`N_1` and :math:`V_1` the other with :math:`N_2` and :math:`V_2`. Now we mix them. Our physics intuition would tell us that the free energy of this new system should be :math:`A = A_1 + A_2`. However, from the free energy equation, we get

.. math::
   A = \cdots - k_B T \ln (V_1^{N_1} V_2^{N2})

This is different from the result we thought of

.. math::
   A = \cdots - k_B T (N_1 + N_2) \ln (V_1 + V_2) = \cdots - k_B T \ln \left(  (V_1 + V_2)^{N_1+N_2}  \right)

That is, free energy becomes neither intensive nor extensive in our derivation.


The fairly simple way to make it extensive is to **divide V by N**. Now a new term will appear in our free energy, namely :math:`N\ln N`. Recall that in Sterling approximation, :math:`\ln N! = N\ln N -N`. So in a large system, we can create some kind of free energy definition which makes it extensive.

.. note::
   We can't just pull out some results from statistical mechanics and apply them to a small system composed of several particles. In stat mech we use a lot of approximations like Sterling approximation which is only valid when particle number is huge.

.. math::
   A = - k_B T N ( \ln(V/N!) - 3 \ln \lambda)

which is to say

.. math::
   Z_N = \frac{Z_1^N}{N!}

This definition "solves" the Gibbs mixing paradox. The physics of this modification requires QM.



Interacting Particles
------------------------


Statistical mechanics starts from a given energy spectrum. With energy spectrum solved, we can do statistics.

For an interacting system, we need to solve the energy spectrum first then calculate the partition function. Usually we would have coupled equations for interacting systems. For example, in a coupled HO system with N oscillators. Image of two HO example is given here.

.. image:: images/Coupled_Harmonic_Oscillator.png
   :align: center

Our equations of motion are

.. math::
   m \ddot x_i + k( x_i -x_{i-1} + x_i - x_{i+1}) =0

with i go from 2 to N-1.

A transformation :math:`x_q = \sum x_m e^{i m q}` will dissociate these equations,

.. math::
   m \ddot x_q + k' x_q =0

We would have normal modes. :math:`w_q ~ \sin|q/2|`.

In some sense, Debye theory is an many Einstein theory.

.. math::
   C_{\mathrm{Debye}} = \int C_{\mathrm{Einstein}} (\omega) g(\omega) d \omega


In Einstein model, every particle is identical and have the same frequency. However, this theory shows a result of Boltzmann factor behavior, which is

.. image:: ../_static/voc/boltzfactor.png
   :align: center

We got sleeping slope at very low temperature where experiments show that this wrong.





So the Debye theory is composed of two steps.

1. Calculate the energy spectrum of N coupled particle system by finding out a decouple transformation;
2. Evaluate the heat capacity integral.



Once we find the energy spectrum, we will know the dispersion relation, which is different from Einstein's model.

.. image:: images/DebyeModelkSpace.png
   :align: center

(Taken without permission from `here <http://griffin.ucsc.edu/teaching/08Q1-155/download/Lecture%2006%20-%20Phonon%20Dynamics.pdf>`_ .)

What did Debye do is to use a linear approximation, :math:`w= c k` for dispersion relation.

.. image:: images/DebyeModelApprox.png
   :align: center

(Taken without permission from `here <http://griffin.ucsc.edu/teaching/08Q1-155/download/Lecture%2006%20-%20Phonon%20Dynamics.pdf>`_ .)


Through a calculation, we show that

.. math::
   g(\omega) = \frac{V \omega^2}{2\pi^2 c^3}

for a 3D lattice.

So average energy is

.. math::
   E = \frac{3V}{2\pi^2 c^3 \hbar^3} (k_B T)^4 \int_0^{x(\omega_m)} \frac{x^3}{e^x - 1} d x

Heat Capacity is

.. math::
   C = 9 N k_B \left(\frac{T}{\Theta_D}\right)^3 \int _ 0 ^{x(\omega_m)} \frac{x^4 e^x}{(e^x - 1)^2} d x

where :math:`x(\omega_m) = \Theta_D/ T` and :math:`\Theta_D = \hbar \omega_D/k_B`.


.. note::
   What's amazing of Debye theory is that the low temperature behavior is independent of cut off frequency. At low temperature, :math:`x(\omega_D)` becomes infinite and it becomes an integration from 0 to infinity thus we do not need to know the cut off temperature to find out the low temperature result and it agrees with experiments well.

.. important::
   We start for an Einstein theory and reaches a non sleeping model. What happened when we integrated over all DoS in Debye model? Work this out in details.

   .. hint::
      This has something to do with density of states dispersion relation.

   This is because our density of states :math:`g(\omega)\propto \omega^2` at low temperature tells us that we would have more states at a certain energy as :math:`\omega` increases. That is to say the system need more energy to increase temperature, identically the heat capacity line becomes steeper.


.. important::
   Why is the # of modes important in Debye model? The degree of freedom is finite in an system. If we don't cut off the frequency, that means we would have infinite degree of freedom because we have made an approximation that dispersion relation is a straight line :math:`\omega = c k`. That would certainly lead to infinite heat capacity and infinite total energy.





Beyond Debye Model
----------------------

Debye model is simple yet classic. Generally we can not find the right transformation that decouples the particles. For example we have the Ising model,

.. math::
   H = \sum_i \mu \sigma B - \sum _ {i,j} J^{ij}\sigma_i \sigma _ j

with :math:`J^{ij} = J (  \delta _ i \delta _ {j-1} +\delta _ i \delta _{j+1} )` as an simple model.

.. hint::
   The reason that we can decouple the simple coupled HO system is that the coupling constant are the same and each HO is identical. In that case the system is just a homogeneous chain such that the normal modes are sin or cos waves depending on the boundary condition. If the system is inhomogeneous, there is no way that we can use simple plain waves on the chain as normal modes.
