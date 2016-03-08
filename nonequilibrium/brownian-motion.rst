Brownian Motion
====================

.. role:: highlit

The equation for Brownian Motion is

.. math::
   \frac{d}{dt} v + \gamma v = R(t),

where :math:`R(t)` is random force which requires

.. math::
   \avg{R(t)} &= 0 \\
   \avg{R(t)R(t')} = C \delta(t-t') .

This equation is the linear :highlit:`Langevin equation`.

The formal solution, which seems to be useless, is

.. math::
   v(t) = v(0)e^{-\gamma t} + \int_0^t dt' e^{-\gamma (t-t')} R(t') .


Knowing that :math:`R(t)` is random, or stochastic, we imediately realize that :math:`v(t)` is stochastic. The thing to do is to find out the statistics.

This quantity squared is,

.. math::
   v(t)^2 = v(0)^2 e^{-2\gamma t} + \int_0^t dt'\int_0^t dt'' e^{-\gamma (t- t')} e^{-\gamma (t - t'')} R(t')R(t'') + \mathrm{Cross Terms}

Average of the solution is

.. math::
   \avg{v} &= \avg{v(0)e^{-\gamma t}} + {\color{magenta}\avg{\int_0^t dt' e^{-\gamma (t-t')} R(t') } } \\
   \avg{v^2} &= \avg{v(0)^2 e^{-2\gamma t}} + \avg{\int_0^t dt'\int_0^t dt'' e^{-\gamma (t- t')} e^{-\gamma (t - t'')} R(t')R(t'')} + {\color{magenta}\avg{ \mathrm{Cross Terms}} }

where these magenta colored terms are zero.

.. hint::
   Note that the average here is ensemble average. Define probability density :math:`P(v,t)` for velocity at time t. Recall that in velocity space, Liouville equation is

   .. math::
      \frac{d}{dt}P(v,t) + \frac{d}{dt}j = 0.

   It's very important to realize that this current density is the current density in velocity space. Applying :math:`d_t v = -\gamma vt R(t)`,

   .. math::
      \frac{d}{dt}P(v,t) + \frac{d}{dv} \left(  (-\gamma v+ R(t))P(v,t) \right) = 0 .


.. warning::
   Now I am curious what ENSEMBLE average is. It's not this probability density because there is time dependence.


.. warning::
   What about :highlit:`Fokker-Plank equation`?



By using the definition of random motion, the ensemble average shows us very simple results.

.. math::
   \avg{v(t)} &= \avg{v(0)} e^{-\gamma t} \\
   \avg{v(t)^2} & = \avg{v(0)^2}e^{-2\gamma t} + C \frac{1- e^{-2\gamma t}}{2\gamma}

In the limit that time goes to infinity, we have

.. math::
   \avg{v(t\to\infty)} & = 0 \\
   \avg{v(t\to \infty)^2} & = \frac{C}{2\gamma} .


The legacy of Einstein is to measure Boltzmann constant using Brownian motion. The regorous derivation can be found in `Physical Mathematics <http://books.google.com/books?id=74ggAwAAQBAJ>`_ . The results, however, is that :math:`\avg{v(t)^2}` is related to thermal energy of the particle and also related to the temperature according to equipartition theorem,

.. math::
   \frac{1}{2}m \avg{v(t\to \infty)^2} = \frac{1}{2}k_B T .



Other Forms of Random Motion
-------------------------------



Wiener Process
~~~~~~~~~~~~~~~

Equation for this process is

.. math::
   \frac{d}{dt} x = R(t).

Derived from this,

.. math::
   \avg{x^2} \propto t.


Ornstein-Uhlenbeck Process
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Change the velocity in Brownian motion to displacement,

.. math::
   \frac{d}{dt} x + \gamma x  =  R(t).

Suppose we have :math:`\avg{v(0)}=0`, :math:`\avg{x^2}` becomes constant.




Harmonic Oscillators The Skeleton Key
----------------------------------------


A damped, driven harmonic oscillator is

.. math::
   m \frac{d^2}{dt^2} x  + \alpha \frac{d}{dt} x + \beta x = R(t)  .

Divided by :math:`\alpha`,

.. math::
   \frac{d^2}{dt^2} x  + \frac{\alpha}{m} \frac{d}{dt} x + \frac{\beta}{m} x = \frac{1}{m}R(t)  .


We understand immediately that this reduces to a :highlit:`Ornstein-Uhlenbeck` equation if mass is very small.


.. warning::
   Does it ring a bell of the WKB approximation?











.
