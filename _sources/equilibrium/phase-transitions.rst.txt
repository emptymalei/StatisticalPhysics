Phase Transitions
========================



Phase Transitions
------------------

Phase transitions are singularities of thermodynamic quantities. There exists many different orders of singularities:

1. First order: discountinuities in of thermodynamic quantities;
2. Second order: discountinuities in the first order derivatives of thermodynamic quantities.
3. ...

Phase transitions only exists in systems with infinite particles.


.. [Leo P. Kadanoff] `Kadanoff's PI Lectures <http://jfi.uchicago.edu/~leop/TALKS/Perimeter%20Stat%20Mech%20Lectures/lectures%20in%20PDF/Part%207%20Mean%20Field%20Theory.pdf>`_

.. admonition:: Phase Transitions in Other Fields
   :class: toggle

   If we are looking for well defined phase transitions in other fields, such as our society, it would be the best if we could all agree on which observables to use, aka, order parameters.

   For example, in social science, there is the model called Schelling's model which models the segregation of races. The model is fairly simple yet is able to match the data.

   The idea is that we have several races scatter on a grid. Each individual is more satistifed if the individual can live nearby a predefined percentage of population of races. If the individual is not satistifed, then the individual will move to another place.

   For better understanding, checkout this web app I wrote: `Schelling's segeration model <http://schelling.openmetric.org/>`_.

   Just like the Ising model, domains might appear. But domains might not appear for some certain parameters. This change is drastic. There is a phase transition. To be precise, we have to define the order parameter in Schelling's model. For example, we define the average size of the communities as our order parameter.

   1. For very low similarity requirements, our agents will be quite satistifed with whatever neighbours they have initially. Very little will change in this case. This is the so called frozen state. In this case, average size of the communities are small but the satisfactions are high.
   2. For very large similarity requirements, our agents is very hard to please. They will relocate all the time and remain not satisfied. This is the mixed state. Or average size of communities is small.
   3. In between, agents will move to live close to their own ethical groups. Domains will form. This is the segreged state. The average size of communities is large.

   There are also other parameters to consider but a phase diagram can be calculated.



   References:

   1. `Schelling’s Segregation Model, I <https://medium.com/@jxxcarlson/schellings-segregation-model-i-43e612241b62>`_
   2. `Schelling's Segregation Model | Model Thinking <https://www.coursera.org/lecture/model-thinking/schellings-segregation-model-1qEBU>`_
   2. `DT&SC 7-11: Schelling's Segregation Model @ YouTube <https://www.youtube.com/watch?v=AZlWOykGzYg>`_
   3. `Gauvin, L., Vannimenus, J., & Nadal, J. P. (2009). Phase diagram of a Schelling segregation model. European Physical Journal B, 70(2), 293–304. <https://doi.org/10.1140/epjb/e2009-00234-0>`_

.. _mean-field-theory:

Mean Field Thoery
-------------------

More is the same.

We take Weiss theory as an example. Weiss theory is a theory of ferromagnetism. In his theory, each molecule in the material serves as a small magnet.

To make it easy to understand, we assume the small magnets are arranged on a 2D grid.

.. figure:: images/weiss-theory-grid.png
   :alt: Weiss Theory Magnets Grid
   :align: center

   Magnets on a 2D grid. The red magnet :math:`s` is surrounded by four neighbours, :math:`s_1`, :math:`s_2`, :math:`s_3`, and :math:`s_4`.

The Hamiltonian for the magnet :math:`s` is

.. math::
   \mathscr H_s = - s ( J \sum_{i} s_i + H),

where :math:`\sum_i s_i` is summing over all the neighbours, i.e., 1,2,3,4 in our example, :math:`H` is the external magnetic field.

There are two key ideas in Weiss mean field theory.

The first idea is to think of the neighours being an average magnetic field :math:`m`. Thus each neighbour can be decomposed into the average magnetic field and the difference, :math:`s_i = m + (s_i - m)`.

.. math::
   \mathscr H_s =& - s ( J \sum_{i} s_i + H) \\
   =& -s ( J \sum_{i} (m + (s_i - m) ) + H) \\
   = & -s ( 4 J m - J\sum_i (s_i - m) + H ) \\
   = & -s ( 4 Jm + H ) + s J \sum_i (s_i - m) \\
   = & \mathscr H_{mf} + \mathscr H_{flu},

where

.. math::
   \mathscr H_{mf} = -s ( 4 Jm + H )

is the mean field Hamiltonian and

.. math::
   \mathscr H_{flu} = s J \sum_i (s_i - m)

is the fluctuations.

The second key idea is to assume translational symmetry on the grid. On this homogenous grid, each spin is no different from other spins. Thus the fluctuations :math:`\mathscr H_{flu}` must be averaged to 0, otherwise the translational symmetry is broken.

The translational symmetry also tells us that the average magnet field for each magnet should be the same and they should all be :math:`\langle s \rangle = m`.

On the other hand, statistical mechanics tells that the average should be calculated as

.. math::
   \langle s \rangle =& \frac{ \sum_s s e^{-\beta \mathscr H_{mf} } }{ \sum_s e^{-\beta \mathscr H_{mf} } } \\
   =& \frac{ e^{\beta ( 4 Jm + H ) } - e^{ - \beta ( 4 Jm + H ) } }{ e^{\beta ( 4 Jm + H ) } + e^{ - \beta ( 4 Jm + H ) } } \\
   =& \tanh( \beta (4Jm + H) ).

The two different views of the average magnetic field for a magnet should be the same, i.e.,

.. math::
   \tanh( \beta (4Jm + H) ) = m.
   :label: eq-weiss-theory-equation

This equation can be understood using graphical solutions.

.. figure:: images/weiss-theory-graphical-solutions.png
   :alt: Weiss Theory Magnets Grid
   :align: center

   Examples of solving equation :eq:`eq-weiss-theory-equation` graphically.

In the example, we are solving the case for :math:`H=0`. For :math:`4\beta J=0.5`, the left side of the equation becomes :math:`\tanh(0.5 m)`. On the right hand side, we have :math:`m`. The value of :math:`m` must be determined by the interceptions of the left hand side and the right hand side. However, we only find :math:`m=0` which is paramagnetic. For :math:`4\beta J=2`, we do find two other solutions for :math:`m`. In fact, due to the slope of the hyperbolic tangent at origin, we only have 3 solutions if :math:`4\beta J>1`. This is interesting because this corresponds to a phase transition at different :math:`\beta`, i.e., :math:`1/k_B T`.




.. admonition:: Why is this an approximation
   :class: note

   Why is this an approximation?
   Because translational symmetry doesn't really hold all the time and the fluctuations are not necessarily 0. But it captures the primary feature of such a system.

This Weiss mean field theory also predicts phase transitions for 1D which is wrong. There is no phase transitions in 1D Ising model. What's more, the theory also predicts the critical temperature wrong. The reason behind it is related to the fact that the fluctuations will be significant around critical points. That being said, mean field theory is not precise enough for phase transition in some low dimensional systems. Just like in statistics, more neighbours will make our standard deviations smaller thus we reach a better approximation by using the mean field.

.. admonition:: Why does mean field theory even work?
   :class: important

   Why does mean field theory even work? From the view of mathematics, any continuous potential function can be Taylor expanded at the mean value of the magnetic field.

   The generic form of the Hamiltonian for magnets on a grid is

   .. math::
      \mathscr H = - \sum _{\langle i,j \rangle} J^{ij} \sigma_i \sigma_j - \mu \sum_i h^i \sigma_i

   Mean field treatment is

   .. math::
      H = - \sum _{\langle i,j \rangle} J^{ij} \sigma_i \sigma - \mu \sum_i h^i \sigma_i

   where :math:`\sigma = \sum_i \sigma_i/N` is the average spin configuration.

   In this approximation, we take the 0 order of spin configuration expansion. We can also include the second order if we need, but it brings in the fluction term.



.. note::
   Susceptibility is a parameter that shows how much an extensive parameter changes when an intensive parameter increases. Magnetic susceptibility is

   .. math::
      \chi(T)= \frac{\mathrm d M(T)}{\mathrm T}


.. important::
   What makes the phase transition in such a system? Finite system has no phase transitions because finite continuous function can only make up continuous function by addition. Phase transition happens when the correlation length becomes infinite. It is all about correlations.


References
~~~~~~~~~~~~~~~~~~~~~~~

1. `Kochmański, M., Paszkiewicz, T., & Wolski, S. (2013). Curie-Weiss magnet - A simple model of phase transition. European Journal of Physics, 34(6), 1555–1573. <https://doi.org/10.1088/0143-0807/34/6/1555>`_

.. _van-der-waals-gas:

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


.. admonition:: From continuity equation to Liouville theorem
   :class: toggle

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
   \langle O \rangle = \int O(p_i; q_i;t) \rho(p_i;q_i;t) \sum_i dp_i dq_i dt

where :math:`i=1,2,..., 3N`.

