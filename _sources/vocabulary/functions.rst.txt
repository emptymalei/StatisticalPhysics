.. index:: Gaussian Integral, Special Functions


Functions
===========

In statistical mechanics, we will have to understand many distributions and laws with functions. In many cases, understanding the behavior of these functions is crucial to grasp the laws of statistical mechanics.


Visual Understanding of Functions
----------------------------------------------


.. admonition:: Make it Dimensionless
   :class: toggle

   In most cases, datasets, functions, and equations in physics carry dimensions.

   It is much easier to understand the datasets, functions and equations if we make them dimensionless. In other words, dimensionless equations and functions can reveal some more fundamental propertities of themselves and are easier to use.

   This trick is extremely useful for theoretical derivations.

We plot out some most used functions in statistical physics.

0. **Boltzmann factor**

   Boltzmann factor is both important and weird in statmech.

   .. figure:: ../_static/voc/boltzfactor.png
      :align: center

      The nth order derivative of this function is always 0 at x=0, for all finite n. Then the question is, how could this function even grow to non-zero values? The reason is that we are actually dealing with infinite nth order derivatives.

      Quote from Professor Kenkre: sleeping lion!


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

   .. figure:: ../_static/voc/fraction1.jpg
      :align: center

      The function approaches 1 at :math:`x\to \infty`



   .. admonition:: Example: Modified Gas Model
      :class: toggle

      The ideal gas law is determined by

      .. math::
         P V = NkT,

      where :math:`P` is the pressure of the gas, :math:`V` is the volume, :math:`N` is the total number of molecules, :math:`T` is the temperature, and :math:`k` is the Boltzmann constant. This equation is telling us that the pressure is proportional to the temperature for a fixed bottle of gas.

      However, the idea gas model sees the gas molecules as points without any interactions between them. For real gas, molecules do interact with each other. Effectively, we have an effective size for the molecules.

      So we modified ideal gas model so that the molecules are treated as hard balls. Assuming the molecules are taking up volume :math:`b` out of the total volume of the gas, we simply need to replace :math:`V` with :math:`V-b`, i.e.,

      .. math::
         P (V - b) = N k T.

      We solve :math:`1/V`, which is

      .. math::
         \frac{1}{V} = \frac{1}{b+\frac{N k T}{P}}.

      Now we can plot out :math:`\frac{1}{V} ~ P` and it shows a behavior just like :math:`1/(1+1/x)`.



5. :math:`1-e^{-\alpha x}\tanh(x)\cosh(\frac{1}{x}) - \frac{1}{x}`

   .. figure:: images/function-1etcf.png
      :align: center

      It is easy to prove that this function will saturate to 1 at :math:`x\to \infty`



Refs & Note
------------------
