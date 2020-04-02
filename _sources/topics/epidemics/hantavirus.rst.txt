.. role:: highlit

Tempo-spatial Epidemic Models
==================================================

We will use the Hantavirus as an example [Abramson2002]_.

The vector of Hantavirus is mice. The population of mice :math:`M` has two components, the infected population :math:`M_I` and the susceptible population :math:`M_S`. We take the SI model with demography,

.. math::
   \frac{dM_S}{dt} &= \lambda M - \mu M_S - a M_S M_I, \\
   \frac{dM_I}{dt} &= -\mu M_I + a M_S M_I,
   :label: eqn-mice-si-with-demography

where :math:`M = M_I + M_S`, :math:`\lambda` is the natural birth rate per population, :math:`\mu` is the natural death rate per population, :math:`a` is the rate of the mouse being infect on contact.

Summing up the two equations, we get the equation for :math:`M`,

.. math::
   \frac{dM}{dt} = (\lambda - \mu) M,

which has an exponential solution

.. math::
   M = M_0 e^{(\lambda -\mu)t}.

This is a trivial solution. As the birth rate and death rate becomes the same, the population becomes stable.

However, the population should also be limited by the natural resources they consume,

.. math::
   \frac{dM}{dt} = (\lambda - \mu) M - f(M, t) M,

where :math:`f(M, t)M` describes the competitions for resources.

.. admonition:: :math:`f(M, t)`
   :class: note

   Suppose we have a bunch of resources :math:`K` and each mouse requires :math:`k` to survive on average. The more mice we have, the more competitive,

   .. math::
      f(M,t) = \frac{kM}{K}.

   Suppose we have equal birth rate and death rate, the population is governed by

   .. math::
      \frac{dM}{dt} = \frac{kM}{K}M.

   For simplifity, we define :math:`\kappa=k/K`,

   .. math::
      \frac{dM}{dt} = (\lambda - \mu) M - \frac{M}{\kappa} M.


Following [Abramson2002]_, we introduce the competition term

.. math::
   \frac{dM_S}{dt} &= \lambda M - \mu M_S - a M_S M_I {\color{blue}- \frac{M}{\kappa} M_S}, \\
   \frac{dM_I}{dt} &= -\mu M_I + a M_S M_I {\color{blue}- \frac{M}{\kappa} M_I}.


The vector, deer mice, is quite mobile. The spatial distribution becomes important. To describe the spatial component, we add a diffusion term

.. math::
   \frac{\partial M_S}{\partial t} &= \lambda M - \mu M_S - a M_S M_I {\color{blue}- \frac{M}{\kappa} M_S} {\color{red}+D_S \nabla^2M_S}, \\
   \frac{dM_I}{dt} &= -\mu M_I + a M_S M_I {\color{blue}- \frac{M}{\kappa} M_I}  {\color{red}+D_I \nabla^2M_I}.


References
----------------------

.. [Abramson2002] `Abramson, G., & Kenkre, V. M. (2002). Spatiotemporal patterns in the Hantavirus infection. Physical Review E - Statistical Physics, Plasmas, Fluids, and Related Interdisciplinary Topics, 66(1), 1–5. <https://doi.org/10.1103/PhysRevE.66.011912>`_