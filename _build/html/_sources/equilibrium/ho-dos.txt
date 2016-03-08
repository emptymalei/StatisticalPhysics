Harmonic Oscillator and Density of States
================================================





Quantum Harmonic Oscillator
----------------------------

Quantum HO tells us the eigen energy

.. math::
   E_n  = \left(n + \frac{1}{2}\right)\hbar \omega

where :math:`\omega = \sqrt{ k/m }`.

Partition function

.. math::
   Z = \sum_n e^{-\beta E_n} = \frac{e^{-\frac{1}{2} \hbar \omega }} { 1 - e^{- \beta \hbar \omega} } = \frac{1}{2}  \sinh(\beta \hbar \omega/2)

Energy

.. math::
   \langle E \rangle = -\frac{\partial}{\partial\beta} \ln Z =  \hbar \omega \left( \frac{1}{2} + \frac{1}{\exp(\beta\hbar\omega) - 1} \right)

Specific heat

.. math::
   C = \frac{\partial}{\partial T} \langle E\rangle = k_B (\beta \hbar \omega)^2 \frac{\exp(\beta \hbar \omega)}{ (\exp(\beta \hbar \omega) - 1)^2 }


This specific heat behaves like this.

.. image:: images/shQHO.png
   :align: center

Though we have infinite energy levels, the specific heat won't blow up because the probability of a high energy level state is very small.




Density of States
-----------------------



.. note::
   Free energy

   .. math::
      A = U - T S

   In another way,

   .. math::
      A = - k_B T \ln Z

   As long as we find out partition function, all thermodynamics quantities are solved, including entropy.

   .. math::
      S = -k_B \beta  \left(T \ln Z - \frac{\partial}{\partial \beta} \ln Z \right)



Specific heat is very different in 1D, 2D, 3D even for similar Hamiltonian. In the case of dipole systems, this is because for 1D, there discrete energy levels, for 2D and 3D energy levels fill up the gap. But what's the difference between 2D and 3D? Obviously the degeneracies are different.

Generally,

.. math::
   Z = \int g(E) e^{-\beta E}\mathrm d E

where :math:`g(E)` is the density of states.


.. admonition:: Discussion of Partition Function  -  Lingfei, Qian-yuan, Lei
   :class: discussion

   1. :math:`Z` is an average of :math:`g(E)` under Boltzman distribution;
   2. :math:`Z` is the Laplace transform of :math:`g(E)`.



Calculation of DoS
~~~~~~~~~~~~~~~~~~~~


QM free particle in a 2D box.

In the momentum (wave number) space, all possible states are distributed on a grid.

.. image:: images/2DDoS.png
   :align: center

How do we calculate the DoS? For a given E, we have :math:`k_x^2 + k_y^2 = \mathrm{Constant} E`. The # of states between :math:`E ~ E + \mathrm d E` is just the area of it divided by the area of each grid box.

.. math::
   N = \frac{d V_k}{d V_0} = \frac{2\pi k d k}{\frac{2\pi}{L_x} \frac{2\pi}{L_y} } \equiv g(E) d E


DoS :math:`g(E)` is

.. math::
   g(E) = \frac{ 2\pi k }{\frac{d E}{d k}} \frac{L_x L_y}{(2\pi)^2}

In the laguage of physics,

.. math::
   g(E) = \frac{\mathrm{area of } E ~ d E}{|\nabla_k E|} \frac{\mathrm{Volume of the box} }{(2\pi)^d}

where :math:`d` is the dimension of the system or box.

Gradient of energy gives us the spread out or dispersion.

To sum up, the quantities that determines the DoS are,

* :math:`E(k)`
* :math:`n`: dimension
* :math:`V`: volume of the box (important in QM because this sets the boundary conditions)


Examples of DoS
~~~~~~~~~~~~~~~~~~~


1. 2D free particle in a box with length :math:`L`

   .. math::
      \frac{d E}{d k} = \frac{d}{d k}\left( \frac{\hbar^2 k^2}{2m} \right) = \frac{\hbar^2 k}{m}

   Thus we have,

   .. math::
      g(E) = \frac{2\pi k }{\frac{\hbar^2 k}{m}} \frac{L^2}{(2\pi)^2} = (\frac{1}{2\pi} \frac{m}{\hbar^2})L^2

2. 3D free particle in a box with length :math:`L`

   .. math::
      \frac{d E}{d k} = \frac{\hbar^2 k^2}{2m}

   DoS

   .. math::
      g(E) = \frac{m}{\hbar^2} \frac{L^3}{2\pi^2} k

   This is :math:`k` dependent.

3. 1D

   .. math::
      g(E) = \frac{1}{k} \frac{m L}{2\pi \hbar^2}


.. note::
   These results are so different. For 1D system, the higher energy of the system is, the small DoS is. 2D DoS doesn't depend on energy. 3D is proportional to the square root of energy.

   DoS is very important in quantum systems because quantization can make strange DoS. In classical systems without quantization, DoS is always some kind of constant.




Partition Function and DoS
----------------------------


Thermal wavelength is defined as

.. math::
   \lambda_T = \frac{\hbar}{ \sqrt{ 2\pi m k_B T } }

For 1 particle in 3D box,

.. math::
   Z_1 = \frac{V}{\lambda_T^3}


It's obvious that for a N particles system without interaction between particles, :math:`Z_N  = (Z_1)^N`. Free energy

.. math::
   A = -k_B T \ln (Z_N) = -k_B T N \ln Z_1 = -k_B T N (\ln V - 3\ln \lambda_T)

.. note::
   This quantity is neither intensive nor extensive! If we combine two exactly same system, then we won't have twice of the free energy. It's called Gibbs mixing paradox.




   Phase Space of Quantum Partition Function
   ------------------------------------------

   This is a physical idea of how do we get the quantum partition function from Classical Mechanics.

   Classically, the partition function

   .. math::
      Z = \int d^3 x \int d^3 p e^{-\beta p^2/2m} = V \left( \sqrt{\frac{ 2m \pi }{\beta} } \right)^3

   We can see from this that thermal wave length is :math:`1/\sqrt{\frac{ 2m \pi }{\beta}}` classically. In quantum, partition function is a summation,

   .. math::
      Z = \sum_i e^{-\beta E_i}

   If we are going to write this into some integration, which is something like

   .. math::
      Z = \int d^3 x\int d^3 p e^{ -\beta p^2/2m }

   which is problematic because it has a different dimension with the summation definition. So we need to put some quantity which has a dimension :math:`[p\cdot x ]^3`, and it got to be :math:`h^3`. So the integration form of partition function is

   .. math::
      Z = \frac{1}{h^3} \int d^3 x\int d^3 p e^{ -\beta p^2/2m }

   .. note::
      :math:`h^3` is the smallest phase space volume in quantum mechanics.


   .. warning::
      Here we used phase space of :math:`{q_i;p_i}` which is not a good choice for quantum mechanics. So this might be a problem. Should check books for a more rigorous method.





Phase Space of Quantum Partition Function
------------------------------------------

This is a physical idea of how do we get the quantum partition function from Classical Mechanics.

Classically, the partition function

.. math::
   Z = \int d^3 x \int d^3 p e^{-\beta p^2/2m} = V \left( \sqrt{\frac{ 2m \pi }{\beta} } \right)^3

We can see from this that thermal wave length is :math:`1/\sqrt{\frac{ 2m \pi }{\beta}}` classically. In quantum, partition function is a summation,

.. math::
   Z = \sum_i e^{-\beta E_i}

If we are going to write this into some integration, which is something like

.. math::
   Z = \int d^3 x\int d^3 p e^{ -\beta p^2/2m }

which is problematic because it has a different dimension with the summation definition. So we need to put some quantity which has a dimension :math:`[p\cdot x ]^3`, and it got to be :math:`h^3`. So the integration form of partition function is

.. math::
   Z = \frac{1}{h^3} \int d^3 x\int d^3 p e^{ -\beta p^2/2m }

.. note::
   :math:`h^3` is the smallest phase space volume in quantum mechanics.


.. warning::
   Here we used phase space of :math:`{q_i;p_i}` which is not a good choice for quantum mechanics. So this might be a problem. Should check books for a more rigorous method.
