.. index:: Gaussian Integral

Integrals
===========

.. index:: Gaussian Integral

Gaussian Intergral
--------------------

The Gaussian integral is a handy tool for calculating/estimating integrals.

.. math::
   \int_{-\infty}^{\infty} e^{-ax^2} \mathrm dx = \sqrt{\frac{\pi}{a}}

A comprehensive description of how this is done is `here <http://mathworld.wolfram.com/GaussianIntegral.html>`_. It is easier to solve the integral using polar coordinates.

In general, we could define a more general form of the integral,

.. math::
   I_n(a) = \int_{0}^{\infty} e^{-ax^2} \mathrm dx.

.. admonition:: A Practice of Symmetries
   :class: note

   The integral we just solved is

   .. math::
      &\int_{-\infty}^{\infty} e^{-ax^2} \mathrm dx \\
      =& \int_{0}^\infty e^{- a x^2} \mathrm dx + \int_{-\infty}^0 e^{-a x^2} \mathrm dx  \\
      =& I_0(a) - \int_{-x=\infty}^{-x=0} e^{-a (-x)^2} \mathrm d (-x) \\
      =& I_0(a) + \int_{-x=0}^{-x=\infty} e^{-a (-x)^2} \mathrm d (-x) \\
      =& I_0(a) + I_0(a) \\
      =& 2 I_0(a)

   Another view of this is that we could investigate the symmetry of the expression :math:`I_n(a)`. By changing the sign of :math:`x`, we know that

   .. math::
      &\int_{x=0}^{x=\infty} e^{-a(-x)^2} \mathrm d(-x) \\
      =& \int_{-x=0}^{-x=-\infty} e^{-a (-x)^2} \mathrm d(-x) \\
      =& -\int_{x=0}^{x=\infty} e^{-a x^2} \mathrm dx \\
      = - I_n(a).

   Using this we could easily calculate the first integral.



