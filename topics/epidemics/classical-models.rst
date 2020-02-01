Classical Models in Epidemics
==================================

There are compartment models such as SIR.

SIR
-------------------

.. figure:: assets/sir.png
   :align: center

   SIR model

The Kermack-McKendrick deterministic model describes the transitions between the different populations. The susceptible population :math:`S(t)` decrease at a rate :math:`-\alpha I(t) S(t)`, where :math:`\beta` is the average probability of getting infected by the infected population. The recovery rate of the infected population is :math:`\alpha`.

.. math::
   \frac{dS(t)}{dt} &= -\beta I(t) S(t) \\
   \frac{dI(t)}{dt} &= \beta S(t) I(t) - \alpha I(t),
   :label: eqn-kermack-mckendrick-eqn-n

with the constraint

.. math::
   S(t) + I(t) + R(t) = N,

where :math:`N` is the total population. [Martcheva2015]_

The limiting behavior of the system is also intuitive. If the infected population is quarantined, i.e., :math:`\beta=0`, the infected population decays exponentially with a half life :math:`1/\alpha`. Notice that the populations can only be integers. When :math:`S(t)<1`, the infected population moves to the exponential decay phase.

At a specific time :math:`t=t_t`, we might reach the threshold that

.. math::
   \beta S(t_t) - \alpha = 0.

Suppose the susceptible population is larger initially, we would have :math:`\beta S(t_0) - \alpha > 0` initially. The infected population will grow. The threshold indicates a flipping moment when the infected population will start to decrease.

The threshold requires

.. math::
   \frac{\beta S(t_t)}{\alpha} = 1.

When :math:`\frac{\beta S(t_t)}{\alpha}>1`, the infected population is growing. It is convinient to define

.. math::
   \tau(t) = \frac{\beta S(t)}{\alpha},

with which equations :eq:`eqn-kermack-mckendrick-eqn-n` becomes

.. math::
   \frac{dS(t)}{dt} &= - \alpha \tau(t) I(t)  \\
   \frac{dI(t)}{dt} &= \alpha (\tau(t) - 1) I(t),

If :math:`\tau(t)>1`, the infected population will grow. If :math:`\tau(t)<1`, the infected population will decrease.

In the **very beginning of a epidemic event**, the susceptible population fraction is almost constant, thus :math:`\tau(t)` is almost constant, i.e., :math:`\tau(t) = \tau_0`, the growth rate of :math:`I(t)` is

.. math::
   \frac{dI(t)}{dt} = \alpha (\tau_0 - 1) I(t).

The equations are solved

.. math::
   I(t) = I(t_0) e^{\alpha (\tau_0 - 1) t}.

The exponential growth rate is determined by

.. math::
   \alpha (\tau_0 - 1).

The days :math:`\Delta t` required to double the infected population is a constant in the early stage. To find out :math:`\Delta t_d`,

.. math::
   \frac{I(t+\Delta t)}{I(t)} = e^{\alpha (\tau_0 - 1) \Delta t} \equiv 2,

which leads to

.. math::
   \Delta t = \frac{\ln 2}{\alpha(\tau_0 -1)} \sim \frac{0.7}{\alpha(\tau_0 -1)} .




Simulate SIR Using Poisson Process
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The transition events of susceptible person being infected (:math:`S\to I`) and infected person being recovered (:math:`I\to R`).

The rates are determined by the equation :eq:`eqn-kermack-mckendrick-eqn-n`,

.. math::
   Y_{S\to I}\left(\int_0^t \beta I(t') S(t') dt' \right)

and

.. math::
   Y_{I\to R}\left( \int_0^t \alpha I(t') dt' \right).

Whenever a even is trigger in the process :math:`Y_{S\to I}`, we will have one more infected person and one less susceptible person.

In fact, :math:`1/\alpha` is the mean days an infectd person remains in the infectd status. This is used to estimate the :math:`\alpha` using data. The value of :math:`\beta` is estimated using the relation [Martcheva2015]_

.. math::
   \frac{\beta}{\alpha} = \frac{\ln (S(t_0)/S(t\to\infty))}{S(t_0) + I(t_0) - S(t\to\infty) }


SIS
-------------------

Some epidemics such as influenza infect us repeatedly. One simple model for them is the SIS model shown in figure :ref:`epidemic-compartment-sis-scheme`,

.. _epidemic-compartment-sis-scheme:
.. figure:: assets/sis.png
   :align: center

   SIS model

The dynamics is determined by

.. math::
   \frac{dI(t)}{dt} = \beta I(t) S(t) - \alpha I(t),

with the constraint

.. math::
   S(t) + I(t) = N.




References
--------------

.. [Martcheva2015] `Martcheva, M. (2015). Introduction to Epidemic Modeling, 9–31. <https://doi.org/10.1007/978-1-4899-7612-3_2>`_
.. [Hill2016] `Learning Scientific Programming with Python <https://scipython.com/book/chapter-8-scipy/additional-examples/the-sir-epidemic-model/>`_