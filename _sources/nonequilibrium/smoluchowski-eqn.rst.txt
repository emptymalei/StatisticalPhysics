Smoluchowski Equation
========================================

.. role:: highlit

Smoluchowski Equation
-----------------------

.. figure:: images/smoluchowski.png
   :alt: Probability distribution with an attraction point.
   :width: 90%
   :align: center

   Probability distribution with an attraction point.

Smoluchowski equation describes the probability distribution of particles in a attractive potential. Given a potential :math:`U(x)`, the master equation is,

.. math::
   \frac{\partial}{\partial t} P(x,t) = \frac{\partial}{\partial x}\left( \frac{\partial U(x)}{\partial x} P(x,t)  \right) + D \frac{\partial^2}{\partial x^2} P(x,t) .


This equation is called the :highlit:`Smoluchowski equation`.

For a quadratic potential :math:`U(x) = \gamma x^2/2`, we get

.. math::
   \frac{\partial}{\partial t} P(x,t) = \gamma \frac{\partial}{\partial x}\left(x P(x,t)  \right) + D \frac{\partial^2}{\partial x^2} P(x,t) .


.. hint::
   The Smoluchowski equation is solved by the :highlit:`methods of characteristics`.


Apply Fourier transform to the Smoluchowski equation, we get

.. math::
   \frac{\partial}{\partial t} P^k = \cdots \frac{\partial}{\partial k} P^k  + \cdots k^2 P^k.

The propagator is

.. math::
   \Pi(x,x',t) = \frac{e^{-(x - x' \exp(-\gamma t))^2}{4D\mathscr T(t)} }{\sqrt{4 \pi D \mathscr T(t)}}


where :math:`\mathscr T(t) = \frac{1-e^{-2\gamma t}}{2\gamma}`.

.. figure:: images/smoluTime.png
   :align: center
   :width: 90%

   Examples of the normalized time parameter in the solution of Smoluchowski equation.


.. [1] This is :highlit:`Riccati's equation`. More information `here <http://www.wolframalpha.com/input/?i=solve%5Bdf%2Fdx%3D%3D-2f%5E2%5D>`_.
