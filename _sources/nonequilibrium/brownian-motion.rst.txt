.. index:: Brownian Motion

Brownian Motion
====================

.. role:: highlit

Brownian motion is described by

.. math::
   \frac{d}{dt} v + \gamma v = R(t),
   :label: eqn-brownian-motion-langevin-eqn

where :math:`R(t)` is a random force density which is required to following

.. math::
   \avg{R(t)} &= 0, \\
   \avg{R(t)R(t')} &= C \delta(t-t') .
   :label: eqn-brownian-motion-langevin-eqn-force-req

The first condition enforces the force density to be unbiased and the second condition indicates that the force density is spiking in time. Equation :eq:`eqn-brownian-motion-langevin-eqn` and :eq:`eqn-brownian-motion-langevin-eqn-force-req` form the linear :highlit:`Langevin equation`.

The formal solution to the Langevin equation is

.. math::
   v(t) = v(0)e^{-\gamma t} + \int_0^t dt' e^{-\gamma (t-t')} R(t') .
   :label: eqn-brownian-motion-langevin-eqn-formal-sol


Given the fact that :math:`R(t)` is stochastic, :math:`v(t)` is also stochastic. The statistics of the observables can be derived. The velocity squared is

.. math::
   v(t)^2 = v(0)^2 e^{-2\gamma t} + \int_0^t dt'\int_0^t dt'' e^{-\gamma (t- t')} e^{-\gamma (t - t'')} R(t')R(t'') + \mathrm{Cross Terms}.

Take the average,

.. math::
   \avg{v} &= \avg{v(0)e^{-\gamma t}} + {\color{magenta}\avg{\int_0^t dt' e^{-\gamma (t-t')} R(t') } } \\
   \avg{v^2} &= \avg{v(0)^2 e^{-2\gamma t}} + \avg{\int_0^t dt'\int_0^t dt'' e^{-\gamma (t- t')} e^{-\gamma (t - t'')} R(t')R(t'')} + {\color{magenta}\avg{ \mathrm{Cross Terms}} }

where these magenta colored terms are zero.

.. admonition:: The Liouville equation
   :class: hint

   The average being used here is the ensemble average. Define a probability density :math:`P(v,t)` for velocity at any time :math:`t`. In velocity space, the Liouville equation is

   .. math::
      \frac{d}{dt}P(v,t) + \frac{d}{dt}j = 0,

   where :math:`j` is the current density is the current density in the velocity space. Apply :math:`d_t v = -\gamma vt + R(t)`, we get

   .. math::
      \frac{d}{dt}P(v,t) + \frac{d}{dv} \left(  (-\gamma v+ R(t))P(v,t) \right) = 0 .


.. admonition:: The Fokker-Plank equation
   :class: hint

   The :highlit:`Fokker-Plank equation`.


The ensemble average is simplified to

.. math::
   \avg{v(t)} &= \avg{v(0)} e^{-\gamma t} \\
   \avg{v(t)^2} & = \avg{v(0)^2}e^{-2\gamma t} + C \frac{1- e^{-2\gamma t}}{2\gamma}.

As time goes to infinity, :math:`t\to\infty`, we have

.. math::
   \avg{v(t\to\infty)} & = 0, \\
   \avg{v(t\to \infty)^2} & = \frac{C}{2\gamma} .

Einstein's showed that the Boltzmann constant :math:`k` could be measured in Brownian motion experiments. :math:`\avg{v(t)^2}` is related to the thermal energy of the particles and also the temperature of the system based on the equipartition theorem,

.. math::
   \frac{1}{2}m \avg{v(t\to \infty)^2} = \frac{1}{2}k_B T .

The rigorous derivation is found in the book `Physical Mathematics <http://books.google.com/books?id=74ggAwAAQBAJ>`_.



Other Forms of Random Motion
-------------------------------

.. index:: Wiener Process

Wiener Process
~~~~~~~~~~~~~~~

Wiener process is determined by

.. math::
   \frac{d}{dt} x = R(t),

where :math:`x` is the displacement and :math:`R(t)` is the random force density defined by equation :math:`eqn-brownian-motion-langevin-eqn-force-req`.

The solution shows that the average of displacement squared is proportional to the time :math:`t`,

.. math::
   \avg{x^2} \propto t.


.. index:: Ornstein-Uhlenbeck Process
.. _Ornstein-Uhlenbeck Process:

Ornstein-Uhlenbeck Process
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Another version of the random motion is to replace the random force density with a random velocity restriction. In this case, we find the equation of motion to be

.. math::
   \frac{d}{dt} x + \gamma x  =  R(t),

where :math:`R(t)` is a random velocity restriction.

The solution is the same as Brownian motion but for :math:`x(t)` instead of :math:`v(t)`.


Harmonic Oscillators as the Skeleton Keys
--------------------------------------------


A driven and damped harmonic oscillator is

.. math::
   m \frac{d^2}{dt^2} x  + \alpha \frac{d}{dt} x + \beta x = R(t),
   :label: eqn-harmonic-oscillator-driven-damped-eom

where :math:`x` is the displacement and :math:`R(t)` is a random force. Equation :eq:`eqn-harmonic-oscillator-driven-damped-eom` has the genes of Brownian motion and :ref:`Ornstein-Uhlenbeck Process`.

Equation :eq:`eqn-harmonic-oscillator-driven-damped-eom` divided by :math:`m` leads to

.. math::
   \frac{d^2}{dt^2} x  + \frac{\alpha}{m} \frac{d}{dt} x + \frac{\beta}{m} x = \frac{1}{m}R(t).
   :label: eqn-harmonic-oscillator-driven-damped-eom-reduced


Equation :eq:`eqn-harmonic-oscillator-driven-damped-eom-reduced` is reduceed to the :highlit:`Ornstein-Uhlenbeck` equation when the mass is very small, i.e., :math:`\frac{\alpha}{m}\gg 1`.


.. admonition:: WKB Approximation
   :class: hint

   WKB approximation.











.
