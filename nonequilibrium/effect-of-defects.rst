Effect of Defects
===========================

.. role:: highlit

.. index:: Defect

Defects
--------------------

.. _fig-effects-of-defects-1d-chain:
.. figure:: images/effectsofDefects.png
   :align: center

   Defects on a 1D chain

The :ref:`smoluchowski-equation` describes the distribution of particles in a continuous potential. Here we discuss the distribution of particles in on a chain with defects.

A defect on a chain is a site that captures the walker with a certain probability, as shown in :numref:`fig-effects-of-defects-1d-chain`. The master equation that describes the distribution is

.. math::
   \frac{d}{dt}P_m = F(P_{m+1}+P_{m-1}-2P_m) - C \delta_{m,r} P_m,
   :label: eqn-master-eqn-effect-of-defects

where :math:`C` is the capture rate at the site of defect.

Similar to any other master equations, the :eq:`eqn-master-eqn-effect-of-defects` is a set of coupled first order differential equations. To solve :eq:`eqn-master-eqn-effect-of-defects`, we consider the following equation

.. math::
   \frac{d}{dt}y+\alpha y = f(t).

The solution to the above equation when :math:`\alpha` is constant, which is

.. math::
   y(t)  = e^{-\alpha t} y(0) + \int_0^t dt' e^{-\alpha (t - t')} f(t').

If we introduce time dependencies for :math:`\alpha`, we get an extra term :math:`e^{-\int_{t'}^t ds \alpha(s)}`.


.. admonition:: Green's function
   :class: hint

   The general solution to any first order differential equation is

   .. math::
      y(t) = G(t,t_0) y(t_0) + \int_{t_0}^{t} df' G(t,t') f(t').

   If :math:`\alpha` is constant, we use Laplace transform to solve it. Otherwise it is much easier to introduce the Green's function.


   We reformulate the problem to include the initial condition,

   .. math::
      L[y]\equiv \dot y + \alpha(t)y = f(t), \qquad \text{for } a < t, \qquad y(a) = 0.

   The solution is

   .. math::
      y = \int_a^\infty G(t\vert \xi)f (\xi) d\xi,

   where the Green's function :math:`G(t\vert \xi)` is defined by

   .. math::
      L[G(t\vert \xi)] = \delta(t - \xi), \qquad \text{for } a < t, \qquad G(a\vert \xi) = 0.

   In this specific case, Green function is

   .. math::
      G(x\vert \xi) = e^{-\int_\xi^x \alpha(t) dt} H(t - \xi),

   where :math:`H` is the Heaviside function.

   For first order differential equations, it is much easier to use the general solution

   .. math::
      y(t) = \frac{\int\mu(t) f(t) dt + C}{\mu(t)},

   where :math:`\mu(t) := e^{\int \alpha(t') dt'}`.

   However, when dealing with more complicate differential equations, the Green's function method becomes more useful and intuitive. Green's function represents the impulse response of the dynamical system.

   More about Green's function, for example, the solution to second order inhomogeneous equation, is found in :ref:`greens-function`.

A more general problem is a time dependent source :math:`g_m(t)` in the master equation,

.. math::
   \frac{d}{dt}P_m = F(P_{m+1} + P_{m-1} - 2P_m) + g_m(t).

The formal solution is

.. math::
   P_m(t) = \eta_m(t) + \int_0^t dt'\sum_n \Pi_{m-n}(t-t') g(t').

However, the solution is still coupled to other sites. We apply Fourier transform on it to detangle the spatial coupling,

.. math::
   P^k(t) = \eta^k(t) + \int_0^t dt' \Pi^k(t-t') g^k(t').

To simplify the result, Laplace transform is used,

.. math::
   \tilde P^k  = \tilde \eta^k + \tilde \Pi^k \tilde g^k  .


.. admonition:: Laplace Transform
   :class: hint

   Laplace transform is a transform of a function :math:`f(t)` to a function of :math:`s` through

   .. math::
      L[f(t)] = \int_0^\infty f(t) e^{ - s t} dt .

   Some useful properties of Laplace transform are listed below.

   1. :math:`L[\frac{d}{dt}f(t)] = s L[f(t)] - f(0)`;
   2. :math:`L[\frac{d^2}{dt^2}f(t) = s^2 L[f(t)] - s f(0) - \frac{d f(0)}{dt}`;
   3. :math:`L[\int_0^t g(\tau) d\tau ] = \frac{L[f(t)]}{s}`;
   4. :math:`L[\alpha t] = \frac{1}{\alpha} L[s/\alpha]`;
   5. :math:`L[e^{at}f(t)] = L[f(s-a)]`;
   6. :math:`L[tf(t)] = - \frac{d}{ds} L[f(t)]`.

   Some useful results of Laplace transform on some simple functions are calculated.

   1. :math:`L[1] = \frac{1}{s}`;
   2. :math:`L[\delta] = 1`;
   3. :math:`L[\delta^k] = s^k`;
   4. :math:`L[t] = \frac{1}{s^2}`;
   5. :math:`L[e^{at}]= \frac{1}[s-a]`.

   More on Laplace transform is in :ref:`laplace-transform`.


Transform back into real space,

.. math::
   \tilde P_m(\epsilon) = \tilde \eta_m(\epsilon)  + \sum_n \tilde \Pi_{m-n}(\epsilon) \tilde g_n(\epsilon).
   :label: eqn-master-equation-1d-chain-defects-g-f-l

To get the solution to :eq:`eqn-master-eqn-effect-of-defects`, we simply define

.. math::
   \tilde g_n = - C\delta _{n,r} \tilde P_n

and plugin it back into :eq:`eqn-master-equation-1d-chain-defects-g-f-l`, we get

.. math::
   \tilde P_m = \tilde \eta _m - C \tilde \Pi_{m-r} \tilde P_r .
   :label: eqn-master-equation-1d-chain-defects-formal-solution


In fact, we haven't solved the equation. The solution :eq:`eqn-master-equation-1d-chain-defects-formal-solution` is merely a formal solution. The right hand side still depends on the probabillity.

If we set :math:`m=r`, we get remove the dependencis of the mth mode,

.. math::
   \tilde P_r  = \tilde \eta_r - C\tilde \Pi_0 \tilde P_r .

From which, we fine the solution to the rth component is,

.. math::
   \tilde P_r = \frac{\tilde \eta_r}{1+C\tilde \Pi_0}  .

The rth mode is then combined with :eq:`eqn-master-equation-1d-chain-defects-formal-solution`,

.. math::
   \tilde P_m &= \eta_m - C\tilde \Pi_{m-r}  \frac{\tilde \eta_r}{1+C\tilde \Pi_0} \\
   & = \eta_m - \frac{\tilde \Pi_{m-r} \eta_r}{1/C + \tilde \Pi_0}


Take the limits to check the properties.

1. Motion limit is given by

   .. math::
      \frac{1}{C} \ll \tilde \Pi_0 .

   In this case, :math:`\tilde P_m \to \tilde \eta_m - \frac{\tilde \Pi_{m-r} \tilde \eta_r}{\tilde \Pi_0}`. In this limit, the propagator decreases with time so fast that it becomes small enough to be neglected. The survival probability is dominated by motion not the capture.

2. Capture limit is given by

   .. math::
      \frac{1}{C} \gg \tilde \Pi_0 .

   In this limit, the survival probability is dominated by capture, :math:`\tilde P_m \to \tilde \eta_m`.


.. admonition:: Numerical Solution
   :class: note

   Numerical solution to this is straight forward.


.. admonition:: A Brief Summary of the Effect of Defect
   :class: toggle

   The master equation is

   .. math::
      \frac{d}{dt} P_m = \text{Without Defect} - C \delta_{m,r} P_m.

   The propagator, aka the Green's function, is :math:`\Pi_{m-n}(t,t_0)`. Apply Laplace transform,

   .. math::
      \tilde P_m(\epsilon) = \tilde \eta_m(\epsilon) - C\tilde \Pi_{m-r}(\epsilon) \tilde P_r(\epsilon).

   Substitute of :math:`m` with :math:`r`, we get

   .. math::
      \tilde P_r(\epsilon) = \frac{\tilde \eta_m(\epsilon)}{1+ \tilde \Pi_0(\epsilon)}.

   This result is then plugged back to the solution, the final solution becomes

   .. math::
      \tilde P_m(\epsilon) = \tilde \eta_m(\epsilon) - C\tilde \Pi_{m-r}(\epsilon) \tilde \eta_r(t) \frac{1}{1+C\tilde \Pi(\epsilon)}.

   The survival probability is defined as

   .. math::
      Q(t) = \sum_m P_m .

   Then we can find out its Laplace transform, which is

   .. math::
      \tilde Q(t) = \frac{1}{\epsilon} \left[ 1 - \frac{\tilde \eta_r(\epsilon)}{1/C + \tilde \Pi_0} \right]







Survival Probability
----------------------

The survival probability of a particle is the summation of the probabilities at all the sites,

.. math::
   Q(t) = \sum_n P_m(t),

i.e.,

.. math::
   \tilde Q(t) = \sum_m \tilde P_m = \frac{1}{\epsilon}\left( 1 - \frac{\tilde \eta_r}{1/C + \tilde \Pi_0} \right)

Looking through the table of Laplace transform,

.. math::
   \frac{d}{dt}Q \to \tilde Q - 1.

The survival probability is then calculated as

.. math::
   \frac{d}{dt}Q(t) = - \int_0^t dt' \mathscr M(t-t') \eta(t')

in which

.. math::
   \mathscr M(t-t') = \frac{1}{1/C + \tilde \Pi_0} .


.. hint::
   The Laplace transform of propagator is

   .. math::
      \tilde \Pi_0 = \int_0^\infty e^{-\epsilon t} \Pi_0 dt,

   which is actually decreasing when :math:`\Pi_0` is a constant.





Photosynthesis
------------------


.. figure:: images/chloroplast.png
   :alt: chloroplast
   :align: center

   Captions are `here on wikipedia <https://en.wikipedia.org/wiki/Photosynthesis#mediaviewer/File:Chloroplast.svg>`_. Chloroplast ultrastructure: 1. outer membrane 2. intermembrane space 3. inner membrane (1+2+3: envelope) 4. stroma (aqueous fluid) 5. thylakoid lumen (inside of thylakoid) 6. thylakoid membrane 7. granum (stack of thylakoids) 8. thylakoid (lamella) 9. starch 10. ribosome 11. plastidial DNA 12. plastoglobule (drop of lipids)


The obsorbed energy of photons follows a random walk in the chloroplast until it hits on a reaction center. On the other hand, the photons can also be emited after some time. The whole process is a master equation of the form

.. math::
   \frac{d}{dt} P_m = \text{Without reaction and emission} - C\delta_{m,r} P_m - \frac{P_m}{\tau},

where the last term :math:`\frac{P_m}{\tau}` is describes the emission.

What the experimentalists are interested in is a quantity called :highlit:`quantum yield`, which is defined as

.. math::
   \text{quantum yield} & = \frac{\text{ Number of excitations in the trap or reaction center } }{\text{Number of total excitations}}\\
   & = \frac{\text{Integration of survival probability with the reaction center}}{\text{Integration of survival probability without the raction center}} .

Without the reaction,

.. math::
   \frac{d}{dt}Q + \frac{Q}{\tau} = 0,
   :label: eqn-survival-probability-2

Assume the survival probability to have the following form

.. math::
   Q(t) = Q(0) e^{-t/\tau}.

:eq:`eqn-survival-probability-2` becomes,

.. math::
   \frac{1}{\tau} \int_0^\infty Q(t) dt = 1 .

The quantum yield is

.. math::
   \text{quantum yield} = \frac{\frac{1}{\tau} \int_0^\infty dt Q(t) \vert_{\text{with traps}} }{\frac{1}{\tau} \int_0^\infty dt Q(t) \vert_{\text{without traps}} } .

The integrals are complex. Forturnatedly, the inverse Laplace transform is not needed since

.. math::
   \int_0^\infty Q(t) dt = L_{\epsilon=0}[Q(t)] .

Define the quantities without traps to be the prime quantities. We define a new quantity

.. math::
   \bar P_m = e^{t/\tau} P_m'.

:math:`\bar P_m` reduces the master equation to the case without emissions which has already been solved,

.. math::
   \bar P_m = P_m.

Finally, the survival probability with traps is

.. math::
   Q' = e^{-t/\tau} Q.

Integrate over time :math:`t`,

.. math::
   \int_0^\infty Q'(t) dt &= \int_0^\infty e^{-t/\tau} Q(t) dt \\
   & = L_{\epsilon=1/\tau} [Q(t)].

This result simplifies our calculation because the survival probability in the case of traps is not needed with Laplace transform of :math:`Q(t)`,

.. math::
   \tilde Q(\epsilon) = \frac{1}{\epsilon} \left( 1- \frac{\tilde \eta}{1/C + 1/\sqrt{\epsilon(\epsilon +4F)}} \right).

We have

.. math::
   \frac{1}{\tau}\int_0^\infty dt Q(t)  &= L_{\epsilon=0}[Q(t)] = \tilde Q(\epsilon=0) \\
   \frac{1}{\tau}\int_0^\infty dt Q'(t)  &= L_{\epsilon=1/\tau}[Q'(t)] = \tilde Q(\epsilon=\frac{1}{\tau}).

The initial condition is used in :math:`\tilde \eta (\epsilon) = \tilde \Pi_{m-r}(\epsilon) P_m(0)`.



Multiple Defects
-------------------


The problem is generalized into include multiple defects. For example, the two defects case is described by

.. math::
   \frac{d}{dt}P_m = \cdots - C_r\delta_{m,r}P_m  - C_s \delta_{m,s} P_m.

Similar to the single defect case, we solve the two special modes by setting :math:`m=r` and :math:`m=s`. Two equations of :math:`\tilde P_r` and :math:`\tilde P_s` are observed,

.. math::
   \tilde P_r &= \eta_r - C_r \tilde \Pi_0 \tilde P_r - C_s \tilde \Pi_{r-s} \tilde P_r \\
   \tilde P_s = \eta_s - C_r \tilde \Pi_{s-r} \tilde P_s - C_s \tilde \Pi_0 \tilde P_s.

To a physicist, the problem gets quite complicated as the number of defects becomes larger.
