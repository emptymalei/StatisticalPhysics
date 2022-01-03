Master Equation
====================

.. index:: Master Equatioin

.. role:: highlit



Master Equation
-----------------------------


**Master equation** method allows us to ignore the details of the microscopic equations yet capturing the properties of the system. The master equations describes the probability of states :math:`P_\xi(t)` by looking into the gains and losses,

.. math::
   \frac{dP_\xi}{d t} = \sum_{\mu} \left( T_{\xi\mu} P_\mu - T_{\mu\xi} P_\xi \right).


.. admonition:: What's the problem of this master equation?
   :class: warning

   1. It's linear and first order. High order effects are ignored.
   2. It comes from nowhere. To prove and interprate the transfer rates is required.


.. index:: Chapman-Kolmogorov equation

"Derive" Master Equation
--------------------------


Suppose the states of a system are denoted as :math:`\xi`, and the probability of the states at time :math:`t` are denoted as :math:`P_\xi(t)`. We assume the probability of the states at time :math:`t` only depends on the probability of the states a moment ago,

.. math::
   P_\xi(t) = \sum_\mu Q_{\xi\mu} P_\mu(t-\tau) .
   :label: eqn-chapman-kolmogorov-eqn

This is the :highlit:`Chapman-Kolmogorov equation`. The equation describes a randomwalk process, a.k.a. Markov process.

.. admonition:: Markov Process and State Machine
   :class: note

   The assumption that the current states doesn't depend on the full history indicates that the system follows a fixed state diagram. In other words, we are using a state machine to approximate a statistical system, except that our physical system has an enormous amount of possible states.

   It may sound weird that we only need the most recent history. However, a Markov process allows us to reach an desired equilibrium quickly.

The formalism of equation :eq:`eqn-chapman-kolmogorov-eqn` reminds us of the time derivative,

.. math::
   \partial_t P_\xi(t) = \lim \frac{P_\xi(t) - P_\xi(t-\tau)}{\tau} .


Notice that

.. math::
   \sum_\mu Q_{\mu\xi} = 1.
   :label: eqn-chapman-kolmogorov-eqn-normalization-relation

.. admonition:: Why the normalization?
   :class: note

   It is required that the probability of all the states at time :math:`t` to be 1, :math:`\sum_\xi P_\xi(t) = 1`.


Substract from the Chapman-Kolmogorov equation a term :math:`P_\xi(t-\tau)`, we get

.. math::
   P_\xi(t) - P_\xi(t-\tau) = \sum_\mu Q_{\xi\mu}P_\mu(t-\tau) - \sum_\mu Q_{\mu\xi} P_\xi(t-\tau) .
   :label: eqn-chapman-kolmogorov-eqn-sub-norm-rel

in which we have applied a variation of equation :eq:`eqn-chapman-kolmogorov-eqn-normalization-relation`, i.e.,

.. math::
   P_\xi(t-\tau) = \sum_\mu Q_{\mu\xi} P_\xi(t-\tau) .

We divide equation :eq:`eqn-chapman-kolmogorov-eqn-sub-norm-rel` by :math:`\tau` on both sides and the limit of :math:`\tau\rightarrow 0` is applied,

.. math::
   \lim_{\tau\rightarrow} \frac{P_\xi(t) - P_\xi(t-\tau)}{\tau} = \lim_{\tau\rightarrow 0} \frac{ \sum_\mu Q_{\xi\mu}P_\mu(t-\tau) - \sum_\mu Q_{\mu\xi} P_\xi(t-\tau) }{\tau}

At first glance, the right hand side of the above equation goes to infinity. However, **we do not expect the time derivative of a probability distribution to be infinite.** That being said, there should be a specific relation between the two terms in the denominator. If we assume that

.. math::
   Q_{ux} = R_{ux}\tau + O(\tau^n)

with :math:`n > 1`, the infinity is removed. This is a self-consistency condition so that our initial assumption that the system doesn't depend the full history holds even for our infinitesimal relations.

.. admonition:: It is werid.
   :class: warning

   By enforcing a system to obey :highlit:`Chapman-Kolmogorov equation`, we admit that the system loses information before a short time interval :math:`\tau`. Now we take the limit :math:`\tau\rightarrow 0`, which means the system has no memory of the past at all! How is this possible?

We get the following differential form

.. math::
   \partial_t P_\xi(t) = \sum_\mu \left( R_{\xi\mu}P_\mu(t) - R_{\mu\xi}P_\xi(t) \right)  .


.. admonition:: Derivation of Master Equation "Rigorously"
   :class: note

   Derivation of the master equation can be more rigorous. [1]_ This note references Reichl's chapter 6 B and Irwin Oppenheim and Kurt E. Shuler's paper. [2]_

   First of all we need the following conditional probability,

   .. math::
      P_1(y_1,t_1) P_{1|1}(y_1,t_1|y_2,t_2) = P_2(y_1,t_1;y_2,t_2)

   which means the probability of variable Y has value :math:`y_1` at time :math:`t_1` and :math:`y_2` at time :math:`t_2` is given by the probability of variable Y has value :math:`y_1` at time :math:`t_1` times that of it has value :math:`y_1` at time :math:`t_1` given it has value :math:`y_2` at time :math:`t_2`.




   Assume that :highlit:`the probability at` :math:`t_n` :highlit:`only depends on that at` :math:`t_{n-1}`, we have

   .. math::
      P_{n-1|1}(y_1,t_1;\cdots;y_{n-1},t_{n-1}|y_n,t_n) = P_{1|1}(y_{n-1},t_{n-1}|y_n,t_n) = P_{1|1}(y_{n-1},t_{n-1}|y_n,t_n) ,

   if the indices are arranged so that :math:`t_1<t_2< \cdots <t_n`.

   **This assumption indicates that the system is chaotic enough.** This is called a **Markov process**.

   Similar to the transition coefficients :math:`T_{\xi\mu}` we defined previously, this :math:`P_{1|1}(y_{n-1},t_{n-1}|y_n,t_n)` is the **transition probability**.

   To find out the time derivative of :math:`P_1(y_2,t_2)`, we need to write down the time dependence of it,

   .. math::
      P_1(y_1,t_1;y_2,t_2) = P_1(y_1,t_1) P_{1|1}(y_1,t_1|y_2,t_2)

   We integrate over :math:`y_1`,

   .. math::
      P_1(y_2,t_2) = \int P_1(y_1,t_1)P_{1|1}(y_1,t_1|y_2,t_2)dy_1

   As we can write :math:`t_2=t_1+\tau`,

   .. math::
      P_1(y_2,t_1+\tau) = \int P_1(y_1,t_1) P _ {1|1}(y_1,t_1|y_2,t_1+\tau) dy_1

   Next we can construct time derivatives of these quantities.

   .. math::
      \partial_{t_1} P_1(y_2,t_1) = \int \lim_{\tau\rightarrow 0} \frac{\int P_1(y_1,t_1) P _ {1|1}(y_1,t_1|y_2,t_1+\tau) - P_1(y_1,t_1) P _ {1|1}(y_1,t_1|y_2,t_1) }{\tau} dy_1


   We expand the right hand side using Taylor series, the details of which can be found in Reichl's book [1]_ , then we get a time derivative,

   .. math::
      \partial_{t} P_1(y_2,t) = \int dy_1 \left( W(y_1,y_2)P_1(y_1,t) - W(y_2,y_1)P_1(y_2,t) \right) .
      :label: eqn-master-equation-rigorous

   Equation :eq:`eqn-master-equation-rigorous` is the :highlit:`master equation`.

   The reason that :math:`W(y_1,y_2)` is a transition rate is that it represents "the probability per unit time that the system changes from state :math:`y_1` to :math:`y_2` in the time interval :math:`t_1\rightarrow t_1 +\tau` ". [1]_



.. admonition:: Is master equation the same as a Markov process?
   :class: important

   In this derivation, we have used the :highlit:`Markov process`. However, a master equation is not equivalent to a :highlit:`Markov process`.

   Read Irwin Oppenheim and Kurt E. Shuler's paper for more details. [2]_

.. admonition:: Patterns in the Probabilities
   :class: note

   We can find out the :highlit:`Chapman-Kolmogorov equation`

   .. math::
      P_{1|1}(y_1,t_1|y_3,t_3) = \int P _{1|1}(y_1,t_1|y_2,t_2)P_{1|1}(y_2,t_2|y_3,t_3)dy_2

   by comparing the following three equations.

   .. math::
      P_2(y_1,t_1;y_3,t_3) = \int P_3(y_1,t_1;y_2,t_2;y_3,t_3) dy_2

   .. math::
      P_3(y_1,t_1;y_2,t_2;y_3,t_3) = P_1(y_1,t_1) P _{1|1}(y_1,t_1|y_2,t_2) P _{1|1}(y_2,t_2|y_3,t_3)

   .. math::
      \frac{P_2(y_1,t_1;y_3,t_3)}{P_1(y_1,t_1)} = P_{1|1}(y_1,t_1|y_3,t_3)



Examples of Master Equation
------------------------------

The are many application of the master equation

.. math::
   \partial_t P_\xi(t) = \sum_\mu \left( R_{\xi\mu}P_\mu(t) - R_{\mu\xi}P_\xi(t) \right) .


Two States Degenerate System
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The master equations for a two-state degenerate system are

.. math::
   \partial_t P_1 = R (P_2 - P_1)

and

.. math::
   \partial_t P_2 = R (P_1 - P_2) .

To solve the equations, we choose a set of "canonical coordinates",

.. math::
   P_+ = P_1+P_2

and

.. math::
   P_- = P_1 - P_2 .

By adding the two original master equations, we have

.. math::
   \partial_t P_+ = 0

and

.. math::
   \partial_t P_- = -2R P_- .


Obviously, the solutions to these equations are

.. math::
   P_+(t) = P_+(0), \qquad P_-(t) = P_-(0)e^{-2Rt} .

This result proves that whatever states was the system in initially, it will get to equilibrium since the term :math:`e^{-2R t}` is a decaying process. This is a relaxation process.


.. admonition:: Von Neumann equation
   :class: hint

   In QM, Von Neumann equations is

   .. math::
      \hat \rho = \hat\rho(0) e^{-i \hat H t/\hbar},

   which is very similar to the solution to the stat mech Liouville equation,

   .. math::
      P(t) = P(0) e^{-A t},

   where A is a matrix

   .. math::
      A_{\xi\mu} = -R_{\xi\mu}, \qquad A_{\xi\xi} = \sum_\mu R_{\mu\xi} .

   The difference here is the :math:`i` in the exponential. With :math:`i`, we get rotation or oscillation, while without :math:`i`, the process is a decay process.


Non Degenerate Two State System
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In a non-degenerate two-state system, the transfer matrix is

.. math::
   \mathbf A = \begin{pmatrix}A_{11}, A_{12} \\ A_{21}, A_{22}\end{pmatrix}


The master equation is

.. math::
   \partial_t \begin{pmatrix}P_1 \\ P_2 \end{pmatrix} = \begin{pmatrix}A_{11}, A_{12}\\ A_{21}, A_{22} \end{pmatrix} \begin{pmatrix}P_1 \\ P_2 \end{pmatrix}

The non-degenerate system shows similar exponential decaying or growing behaviors as in the degenerate system. However, the equilibrium point or fixed point is different.

.. math::
   \partial_t P_1 = R_{12} P_2 - R_{21} P_1

shows that at equilibrium, i.e., :math:`\partial_t P_1 = 0`, the ratio of the probabilities is defined by the coefficients

.. math::
   \frac{R_{12}}{R_{21}} = \frac{P_1(\infty)}{P_2(\infty)}.


Footnotes
----------



.. [1] Linda E. Reichl. "A Modern Course in Statistical Physics".

.. [2] Irwin Oppenheim and Kurt E. Shuler. "Master Equations and Markov Processes". `Phys. Rev. 138, B1007 (1965) <http://journals.aps.org/pr/abstract/10.1103/PhysRev.138.B1007>`_ .
