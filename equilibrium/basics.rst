.. index::
   Statistical Mechanics, Mechanics, Phase Space, Probability, Boltzmann Factor

Basics of Statistical Mechanics
==============================================




Phase Space
--------------------


Why is statistics important? Remember we are dealing with Avogadro's number of DoFs. If we are going to calculate the dynamics of this system by calculating the dynamics of each particles. To store one screen shot of the system with each DoF take only 8 bits, we need :math:`10^23` bytes that is :math:`10^17` GB. It is not even possible to store only one screen shot of the system. So time to change our view of these kind of systems.

.. figure:: images/newtonsDream.jpg
   :alt: Newton's Dream
   :width: 60%
   :align: center

   Newton's plan of mechanics. Mechanics was in the center of all physics.

What is mechanics? It deals with dynamics in the following way:

* Description of initial state
* Time evolution of the system
* Extraction of observables

As we already mentioned initial state, we need to explain how to describe a state. A vector in phase space gives us a state. Time evolution is motion of points in phase space. Finally, we can do whatever is needed to extract observables, for example just use projection of points in phase space.

Problem is, when it comes to stat mech, it's not possible to do all these DoFs one by one. We need a new concept.


Boltzmann Factor
-----------------


.. math::

   \text{probability of a point in phase space} = \exp(-\frac{E}{k_B T})

Boltzmann factor gives us the (not normalized) probability of the system staying on a phase space state with energy :math:`E`.


.. admonition:: Why Boltzmann Factor
   :class: note

   Why does Boltzmann factor appear a lot in equilibrium statistical mechanics? Equilibrium of the system means when we add infinitesimal amount of energy to the whole thing including system and reservoir, a characteristic quantity :math:`C(E) = C_S C_R` won't change. That is the system and the reservoir will have the same changing rate of the characteristic quantity when energy is changed, i.e.,

   .. math::
      \frac{\partial \ln C_S}{\partial E_S} = - \frac{\partial \ln C_R}{\partial E_R} .

   We have :math:`\mathrm dE_1 = -\mathrm dE_2` in a equilibrium state. They should both be a constant, which we set to :math:`\beta`. Finally we have something like

   .. math::
      \frac{\partial \ln C_S}{\partial E_S} = \beta

   which will give us a Boltzmann factor there.

   This is just a very simple procedure to show that Boltzmann factor is kind of a natural factor in equilibrium system.







Partition Function
--------------------

For a given Hamiltonian H, the (classical) partition function Z is

.. math::
   Z = \int d p \int d x e^{-\beta H}

A simple example is the Harmonic Oscillator,

.. math::
   H = \frac{p^2}{2m} + \frac{1}{2} q x^2

The partition function

.. math::
   Z = \int e^{-\beta p^2/(2m)} d q \int  e^{-\beta \frac{1}{2} q x^2 } d x  = 2\pi \sqrt{m/q} \frac{1}{\beta}


Energy

.. math::
   E = \frac{1}{Z} \int \int e^{-\beta p^2/(2m)}   e^{-\beta \frac{1}{2} q x^2 }  H d p d x  = \cdots = k_B T

(This result is obvious if we think about equipartition theorem.)


A more clever approach for the energy is to take the derivative of partition function over :math:`\beta`, which exactly is

.. math::
   \langle E \rangle = -\frac{\partial }{\partial \beta } \ln Z

In our simple case,

.. math::
   \ln Z = -\frac{\partial}{\partial \beta} \left(\ln (k_B T) + \mathrm{Some Constant} \right)= k_B T



This is the power of partition function. To continue the SHO example, we find the specific heat is

.. math::
   C = k_B


.. admonition:: Does This Result Depend on SHO
   :class: toggle

   This result has nothing to do with the detail of the SHO, no matter what mass they have, no matter what potential constant :math:`q` they have, no matter what kind of initial state they have. All the characteristic quantities of SHO are irrelevant. Why? Mathematically, it's because we have Gaussian integral here. **But what is the physics behind this?** Basicly this classical limit is a high temperature limit.





Magnetization
--------------


We have such a result in an experiment of magnetization with N magnetic dipoles in 1D.

.. image:: images/magnetizationExp.jpg
   :align: center

How can we describe this with a theory?

It's not possible to describe the system by writing down the dynamics of each magnetic dipole. So we have to try some macroscpic view of the system. Probability theory is a great tool for this. The probability of a dipole on a energy state :math:`E_i` is

.. math::
   P(E_i) = \frac{\exp(-\beta E_i)}{\sum_{i=1}^{n} \exp(-\beta E_i)}  .

So the megnetization in this simple case is

.. math::
   M = (\mu N e^{\beta \mu B} - \mu N e^{-\beta \mu B})/(\exp(\beta \mu B) + \exp(-\beta \mu B)) = \mu N \tanh (\beta \mu B)

.. admonition:: Python Code
   :class: toggle

   Use ipython notebook to display this result. The original notebook can be downloaded from `here <http://emptymalei.github.io/StatisticalPhysics/equilibrium/display.ipynb>`_. (Just put the link to `nbviewer <http://nbviewer.ipython.org>`_ and everyone can view online.)


   .. code:: python

       %pylab inline
       from pylab import *

   .. parsed-literal::

       Populating the interactive namespace from numpy and matplotlib


   .. code:: python

       x=linspace(0,10,100)
       y=tanh(x)
   .. code:: python

       figure()
       plot(x, y, 'r')
       xlabel('External Magnetic Field')
       ylabel('M')
       title('Tanh theory')
       show();


.. image:: display_files/display_2_0.png
   :align: center



This is exactly the thing we saw in the experiment.


This can be classified as a category of problems. In this specific example we see saturation of magnetization. However this is not alway true.

.. admonition:: Examples
   :class: note

   Examples can be shown here.


Heat Capacity
---------------


Another category of problems is temperature related. For example, a study of average energy with change temperature.

For the paramagnetic example, the energy of the system is

.. math::
   E = -(\mu B N e^{\beta \mu B} - \mu N e^{-\beta \mu B})/(\exp(\beta \mu B) + \exp(-\beta \mu B)) = -\mu N B \tanh (\beta \mu B)


Obviously, no phase transition would occur. But if we introduce self interactions between dipoles and go to higher dimensions, it's possible to find phase transitions.



Specific Heat
----------------


.. math::
   C = \frac{d}{T}\langle E \rangle

Check the behavior of specific heat,

1. Is there a Discontinuity?
2. Constant?
3. Blow up?
4. Converge?

Specific heat can be used for second order phase transition. An simple example of this is Landau theory.




Importance of Dimensions
--------------------------------------------


`IPython Notebook about heat capacity of systems with different dimensions. <http://nbviewer.ipython.org/github/emptymalei/StatisticalPhysics/blob/master/equilibrium/homework/StatMech_HW1.ipynb>`_ .
