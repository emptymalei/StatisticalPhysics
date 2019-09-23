.. index:: Gaussian Integral, Special Functions


Functions
===========

In statistical mechanics, we will have to understand many distributions and laws with functions. In many cases, understanding the behavior of these functions is crucial to grasp the laws of statistical mechanics.


Visual Understanding of Functions
----------------------------------------------


.. note::
   In most cases, datasets, functions, and equations in physics carry dimensions.

   It is much easier to understand the datasets, functions and equations if we make them dimensionless. In other words, dimensionless equations and functions can reveal some more fundamental propertities of themselves and are easier to use.

   This trick is extremely useful for theoretical derivations.


0. **Boltzmann factor**

   Boltzmann factor is both important and weird in statmech.

   .. figure:: ../_static/voc/boltzfactor.png
      :align: center

      The nth order derivative of this function is always 0 at x=0, for all finite n. Then the question is, how could this function even grow to non-zero values? The reason is that we are actually dealing with infinite nth order derivatives.

      Quoter from Professor Kenkre: sleeping lion!


1. Tanh(x)

   .. image:: ../_static/voc/tanh.jpg
      :align: center

2. :math:`1-\exp(-x)`

   .. image:: ../_static/voc/exp1.jpg
      :align: center

3. :math:`\cosh(1/x)-1/x`

   .. image:: ../_static/voc/cosh1.jpg
      :align: center

4. :math:`1/(1+1/x)`

   .. image:: ../_static/voc/fraction1.jpg
      :align: center



   .. admonition:: Examples in Physics
      :class: note

      An example of this :math:`1/(1+1/x)` is the modified gas model.

      .. math::
         P (V - b) = N k T

      We can find out :math:`1/V`, which is

      .. math::
         \frac{1}{V} = \frac{1}{b+\frac{N k T}{P}}

      Now we can plot out :math:`\frac{1}{V} ~ P` and it shows a behavior just like :math:`1/(1+1/x)`.




Functions that will saturate
----------------------------


.. math::
   1-e^{-\alpha x}
   \tanh(x)
   \cosh(\frac{1}{x}) - \frac{1}{x}





Refs & Note
------------------
