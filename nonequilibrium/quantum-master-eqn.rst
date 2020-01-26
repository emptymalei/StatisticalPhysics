Quantum Master Equation
=======================================================

.. role:: highlit

.. index:: Quantum Master Equation

.._Quantum Master Equation:

Quantum Master Equation
------------------------

.. admonition:: Density Matrix
   :class: important

   In quantum mechanics, the probability doesn't deliver all the information available. The density matrix is a better choice to construct a master equation for quantum systems.

Quantum mechanics observables are averages over all the density matrix elements,

.. math::
   \langle O \rangle = \sum_{m,n} O_{nm}\rho_{mn}.

Given an initial condition with diagonalized density matrix, the dynamics won't necessarily guarantee the diagonalizion of the density matrix. Thus the average pickup off-diagonal element contributions as time goes on.

The classical master equations won't solve authentic quantum problems given the different definition of the average of the observables.

To derive a quantum master equation, we start from the first principle in quantum mechanics,

.. math::
   i\hbar \frac{d}{dt}\hat \rho = [\hat H,\hat \rho] \equiv \hat L \hat \rho.



Pauli's Mistake
~~~~~~~~~~~~~~~~~


Pauli derived the first quantum master equation. However, it was not quite right.

The formal solution to a quantum system is

.. math::
   \hat \rho(t) = e^{-iL(t-t_0)} \hat \rho(t_0) .


In the Heisenberg picture,

.. math::
   \hat \rho(t+\tau) = e^{-i\tau \hat H} \hat \rho(t) e^{i\tau \hat H} .

The diagonal elements of the density matrix are

.. math::
   \rho_{mm}(t+\tau) = \bra{m}e^{-i\tau \hat H} \hat \rho(t) e^{i\tau \hat H} \ket{m}.


On the left hand side, :math:`P_m\equiv \rho_{mm}` is the probability of the state. The right hand side becomes

.. math::
   \text{RHS} = \sum_{n,l}\bra{m}e^{-i\tau \hat H} \ket{n} \bra{n}\hat \rho(t) \ket{l}\bra{l} e^{i\tau \hat H} \ket{m}.


Pauli's then assumed that the system is "dirty" enought to have recurances of diagonalized density matrix. The diagonalized density matrix is used to calculate the probability,

.. math::
   P_m(t+\tau) &= \sum_{n}\bra{m}e^{-i\tau \hat H} \ket{n} \bra{n}\hat \rho(t) \ket{n}\bra{n} e^{i\tau \hat H} \ket{m} \\
   & = \sum_{n} P_n \left\vert \bra{m} e^{-i\tau \hat H} \ket{n}  \right\vert^2 .

The term :math:`\left\vert \bra{m} e^{-i\tau \hat H} \ket{n}  \right\vert^2` on the right hand side is the transition probability from a state n to state m in a short period :math:`\tau`. We define

.. math::
   Q_{mn}(\tau) \equiv \left\vert \bra{m} e^{-i\tau \hat H} \ket{n}  \right\vert^2.

The probability at time :math:`t+\tau` is

.. math::
   P_m(t+\tau) = \sum_n Q_{mn}(\tau)P_n(t).

The Chapman method is applied to derive the master eqution.

.. admonition:: Fermi's Golden Rule
   :class: important

   The Pauli assumption is the Fermi golden rule which requires an infinite amount of time. This is not gererally valid.


Better Quantum Master Equations
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The first "real" quantum master equation was derived by van Hove.

van Hove argued that Pauli's result is not correct. First of all,

.. math::
   P_m(t+\tau) &= \sum_n Q_{mn}(\tau) P_n(t) \\
   P_m(t-\tau) & = \sum_n Q_{mn}(-\tau) P_n(t) .

With :math:`Q_{mn}(\tau) = Q_{mn}(-\tau)`, we have

.. math::
   Q_{mn}(\tau) & = \left\vert \bra{m} e^{-i\tau \hat H} \ket{n}  \right\vert^2 \\
   & = \left\vert \bra{m} e^{i\tau \hat H} \ket{n}  \right\vert^2 \\
   & = Q_{mn}(-\tau),

which leads to

.. math::
   P_m(t+\tau) = P_m(t-\tau).

In other words, we've shown that the probabilities of states are constant.


van Hove
---------------------------------------------------


.. admonition:: Questions
   :class: important

   There are several key questions in inventing a quantum master equation.

   1. Which systems can be described by the master equations?
   2. What's the time scale for quantum master equation to be valid?

Suppose we have a quantum system with the Hamiltonian

.. math::
   \hat H = \hat H_0 + \lambda(t)\hat W .

van Hove's method was to describe systems with diagonal singularity conditions on a large time scale. The perturbations should be small enough, i.e., :math:`\lambda^2 t \approx \text{constant}`. The diagonal elements are

.. math::
   P_m & = \bra{m}\hat \rho \ket{m} \\
   & = \sum_{m,n} \bra{m} e^{i\hat H t/\hbar} \ket{n}\bra{n} \hat \rho(0) \ket{l}\bra{l} e^{-iHt/\hbar} \ket{m} \\
   & = \sum_{m,n} \left\vert \bra{m} e^{i (\hat H_0 + \lambda \hat W) t/\hbar } \ket{n} \right\vert^2 \rho_{nl}(0) .
   :label: eqn-quantum-master-equation-van-hove-pm-1

van Hove applied random phase condition on the initial condition, i.e., :math:`\rho_{nl}(0)` is diagonalized at initial :math:`t=0`. We have

.. math::
   \rho_{nl} (0) = \rho_{nn} \delta_{nl} = P_n(0) \delta_{nl},

Equation :eq:`eqn-quantum-master-equation-van-hove-pm-1` becomes,

.. math::
   P_m = \sum_n \left\vert \bra{m} e^{i (\hat H_0 + \lambda \hat W) t/\hbar } \ket{n} \right\vert^2 P_n(0) .
   :label: eqn-quantum-master-equation-van-hove-pm-2

The equation :eq:`eqn-quantum-master-equation-van-hove-pm-2` is furthure simplified by the Dyson series.

.. index:: Projection Technique
.. _projection-technique:

Zwawzig and Nakajiwa
---------------------

Zwawzig and Nakajiwa invented the projection technique to solve quantum master equations.

We define a :highlit:`diagonalizing operator` :math:`\hat D` which keeps the diagonal elements and drops the off-diagonal elements of a matrix. With this definition, it's conjugate :math:`1-\hat D` will drop all diagonal elements.

The diagonalized density matrix is

.. math::
   \hat \rho_d = \hat D \hat \rho

and the all the off-diagonal elements of the density matrix

.. math::
   \hat \rho_{od} = (1-\hat D)\hat \rho.

.. admonition:: Reconstruct the Density Matrix
   :class: hint

   The density matrix is trivilly reconstructed by

   .. math::
      \hat \rho = \hat \rho_d + \hat \rho_{od} .


The von Neumann equation is

.. math::
   i\hbar \partial_t \hat \rho = \left[\hat H, \hat \rho \right],

With the Liouville operator :math:`\hat L`, the von Neumann equation is rewritten as

.. math::
   \partial_t \hat \rho = -i \hat L \hat \rho .

Apply :math:`\hat D` and :math:`1-\hat D` to the von Neumann equation, we get two equations

.. math::
   \partial_t \hat \rho_d & = -i \hat D  \hat L \hat \rho \\
   \partial_t \hat \rho _{od} & = -i (1 - \hat D)  \hat L \hat \rho .
   :label: eqn-quantum-master-equations-projection-technique-dod-1

Use the completeness relation :math:`\hat \rho = \hat \rho_d + \hat \rho_{od}`,

.. math::
   \partial_t \hat \rho_d & = -i \hat D  \hat L \hat \rho_d - i \hat D  \hat L \hat \rho _ {od} \\
   \partial_t \hat \rho _{od} & = - i (1 - \hat D)  \hat L \hat \rho _ d - i (1 - \hat D)  \hat L \hat \rho_{od} .
   :label: eqn-quantum-master-equations-projection-technique-dod-2

The off-diagonal equation in equation :eq:`eqn-quantum-master-equations-projection-technique-dod-2` is solved using Green's function,

.. math::
   \hat \rho_{od} = e^{-i(1-\hat D)\hat L t} + \int_0^t dt' e^{-i(1-\hat D) \hat L (t-t')}(-i(1-\hat D)\hat L \hat \rho_d(t')) .
   :label: eqn-quantum-master-equations-projection-technique-od-green

.. admonition:: Green's Function
   :class: toggle

   Recall that the solution to

   .. math::
      \dot y + \alpha y = f

   is

   .. math::
      y = e^{-\alpha t} y(0) + \int_0^t dt' e^{-\alpha (t-t')} f(t') .


Insert :eq:`eqn-quantum-master-equations-projection-technique-od-green` into the equation for :math:`\hat \rho_d` in equation :eq:`eqn-quantum-master-equations-projection-technique-dod-2`,

.. math::
   {\color{red}\partial_t \hat \rho_d = - i\hat D\hat L \hat \rho_d -  \hat D\hat L \int_0^t dt' e^{-i(1-\hat D) \hat L (t-t')}(1-\hat D)\hat L \hat \rho_d(t')} {\color{blue} - i \hat D \hat L e^{-i(1-\hat D)\hat L t} \rho_{od}(0) }.
   :label: eqn-quantum-master-equations-projection-technique-d-1

The term :math:`- i \hat D \hat L e^{-i(1-\hat D)\hat L t} \rho_{od}(0)` disapears when we apply the random phase initial condition. Then we get our closed master equation for :math:`\hat \rho_d`, i.e.,  an equation for the probabilities,

.. math::
   {\color{red}\partial_t \hat \rho_d = - i\hat D\hat L \hat \rho_d -  \hat D\hat L \int_0^t dt' e^{-i(1-\hat D) \hat L (t-t')}(1-\hat D)\hat L \hat \rho_d(t')}.
   :label: eqn-quantum-master-equations-projection-technique-master-equation


.. admonition:: The Off-diagonal Elements
   :class: toggle


      "We can always use phasers."

      -- V. M. Kenkre

   The condition :math:`\rho_{od}(0)=0` needed to reach a closed master equation doens't imply that we have to require localized initial condition on any specific state.

   Given a system of five possible states, the off-diagonal elements are zeros if the system is on a specific state initially.

   .. image:: images/quantum1state.png
      :align: center

   The density matrix might contain off-diagonal elements if we have two non-orthogonal states initially.

   .. image:: images/quantum2states.png
      :align: center

   However, we can always choose a combination of the current basis to diagonalize the density matrix.

The projection technique can also be applied on the flavor transformations of neutrinos. [3]_


Simplify the Quantum Master Equation
----------------------------------------

We derived the quantum master equation using the projection method. However, the equation is complicated.

Let's stare at the solution equation :eq:`eqn-quantum-master-equations-projection-technique-master-equation` for a minute,

.. math::
   {\color{red}\partial_t \hat \rho_d = - i\hat D\hat L \hat \rho_d -  \hat D\hat L \int_0^t dt' e^{-i(1-\hat D) \hat L (t-t')}(1-\hat D)\hat L \hat \rho_d(t')} {\color{blue} - i \hat D \hat L e^{-i(1-\hat D)\hat L t} \rho_{od}(0) }.

By definition, :math:`\rho_d=\hat D\rho`. The term on the right hand side :math:`\hat D \hat L \rho_d` is

.. math::
   \hat D \hat L \rho_d & = \hat D\hat L \hat D \hat \rho \\
   & = \hat D \left[ {\color{magenta}  \begin{pmatrix}\rho_{11} & 0 & 0 & \cdots \\ 0 & \rho_{22} & 0 & \cdots \\ 0 & 0 & \rho_{33} & \cdots  \\ \vdots & \vdots & \vdots &  \ddots  \end{pmatrix} \begin{pmatrix} H_{11} & H_{12} & H_{13} & \cdots \\ H_{21} & H_{22} & H_{23} & \cdots  \\ H_{31} & H_{32} & H_{33} & \cdots \\ \vdots & \vdots \vdots & & \ddots \end{pmatrix}    } -  {\color{green} \begin{pmatrix} H_{11} & H_{12} & H_{13} & \cdots \\ H_{21} & H_{22} & H_{23} & \cdots  \\ H_{31} & H_{32} & H_{33} & \cdots \\ \vdots & \vdots \vdots & & \ddots   \end{pmatrix} \begin{pmatrix} \rho_{11} & 0 & 0 & \cdots \\ 0 & \rho_{22} & 0 & \cdots \\  0 & 0 & \rho_{33} & \cdots \\ \vdots & \vdots & \ddots & \cdots \end{pmatrix} } \right]


The diagonal elements are the same for the two terms (the magenta term and the green term) in the braket so that all the diagonal elements are gone. Finally, we apply :math:`\hat D` to the off-diagonalized matrix and get 0,

.. math::
   \hat D \hat L \rho_d = 0.

Thus the first term on the right hand side in equation :eq:`eqn-quantum-master-equations-projection-technique-master-equation` :math:`-i\hat D\hat L\hat \rho_d = 0`.

In quantum perturbation theory, the Hamiltonian is :math:`\hat H = \hat H_0 + \lambda \hat W`. The Liouville operator for this system has two parts,

.. math::
   \hat L = \hat L_0 + \lambda \hat L_W.

The master equation becomes

.. math::
   \partial_t \hat \rho_d & =  -  \int_0^t dt' \hat D (\hat L_0 + \lambda \hat L_W ) e^{-i(1-\hat D) (\hat L_0 + \lambda \hat L_W  )(t-t')}(1-\hat D)\hat L \hat \rho_d \\
   & =  -  \int_0^t dt' \hat D (\hat L_0 + \lambda \hat L_W ) e^{-i(1-\hat D)  (\hat L_0 + \lambda \hat L_W ) (t-t')} (\hat L_0 + \lambda \hat L_W ) \hat \rho_d \\
   & =  -  \int_0^t dt' \mathscr K(t-t') \hat \rho_d .

under the initial condition

.. math::
   - i \hat D \hat L e^{-i(1-\hat D)\hat L t} \rho_{od}(0) = 0

and the proved relation

.. math::
   \hat D \hat L \rho_d = 0.

Define

.. math::
   \mathscr K(t-t') = \hat D (\hat L_0 + \lambda \hat L_W ) e^{-i(1-\hat D)  (\hat L_0 + \lambda \hat L_W ) (t-t')} (\hat L_0 + \lambda \hat L_W ) .

In the weak coupling interaction limit, :math:`\lambda \rightarrow 0`,

.. math::
   \mathscr K(t-t')  &=  \hat D (\hat L_0 + \lambda \hat L_W ) e^{-i(1-\hat D)  (\hat L_0 + \lambda \hat L_W ) (t-t')} (\hat L_0 + \lambda \hat L_W )  \\
   &= \hat D (\hat L_0 + \lambda \hat L_W ) e^{-i(1-\hat D)  \hat L_0 (t-t')} (\hat L_0 + \lambda \hat L_W ) \\
   &= \hat D \hat L_0  e^{-i(1-\hat D)  \hat L_0 (t-t')} \hat L_0  + \lambda \hat D \hat L_0  e^{-i(1-\hat D)  \hat L_0 (t-t')}   \hat L_W   \\
   \phantom{\mathscr K(t-t')} & \phantom{{} = } + \lambda \hat D  \hat L_W  e^{-i(1-\hat D)  \hat L_0 (t-t')} \hat L_0  + \lambda^2 \hat D   \hat L_W  e^{-i(1-\hat D)  \hat L_0 (t-t')}  \hat L_W  \\
   &=  \lambda^2 \hat D   \hat L_W  e^{-i(1-\hat D)  \hat L_0 (t-t')}  \hat L_W  \\
   &=  \lambda^2 \hat D   \hat L_W  e^{-i\hat L_0 (t-t')}  \hat L_W .

Several terms of :math:`\lambda` are dropped. [1]_

We will derive the Fermi's golden rule. First, we have

.. math::
   \bra{m} \partial_t \rho_d \ket{m} = -\lambda^2 \bra{m} \int_0^t dt' \hat L_W e^{-i(t-t')\hat L_0} \hat L_W \rho_d(t') \ket{m}.
   :label: eqn-qme-d-avg-eqn-1



.. admonition:: A Useful Relation
   :class: hint

   Here is a useful relation,

   .. math::
      e^{iA\hat L} \hat O & = \hat O + i A \hat L \hat O + \frac{(iA)^2}{2} \hat L \hat L \hat O + \cdots \\
      & = \hat O + iA[\hat H, \hat O] + \frac{(iA)^2}{2}  [\hat H, [\hat H,\hat O]] + \cdots \\
      & = e^{iA\hat H}\hat O e^{-iA\hat H}.


By definition, :math:`\hat L_W \hat \rho_d = \frac{1}{\hbar}[W, \rho_d]`. Define

.. math::
   \hat{\mathscr M} = e^{-i(t-t')\hat H_0}[\hat V,\hat \rho_d]e^{i(t-t')\hat H_0}.

Equation :eq:`eqn-qme-d-avg-eqn-1` becomes

.. math::
   \bra{m} \partial_t \rho_d \ket{m} &= -\lambda^2 \bra{m} \int_0^t dt' [\hat W, e^{-i(t-t')\hat L_0}[\hat W, \rho_d(t')]] \ket{m}  \\
   & = -\lambda^2 \bra{m} \int_0^t [\hat W, ] dt' \ket{m}  \\
   & = -\lambda^2 \left( \bra{m} \int_0^t dt' \hat W\hat{\mathscr M} \ket{m} - \bra{m} \int_0^t \hat{\mathscr M}\hat W\ket{m} dt' \right) \\
   & = -\lambda^2 \int_0^t dt' \left( \bra{m} \hat W\hat{\mathscr M} \ket{m} - \bra{m} \hat{\mathscr M}\hat W\ket{m}  \right) \\
   & = -\lambda^2 \int_0^t dt' \sum_n (W_{mn}\mathscr M_{nm} - \mathscr M_{mn}W_{nm}).
   :label: eqn-qme-d-avg-eqn-2

We already know that :math:`\rho_d = P_{m}`. We rewrite equation :eq:`eqn-qme-d-avg-eqn-2`,

.. math::
   \partial_t P_m(t) = -\lambda^2 \int_0^t dt' \sum_n (W_{mn}\mathscr M_{nm} - \mathscr M_{mn}W_{nm}).

The eigen function of the system is

.. math::
   \hat H_0 \ket{m} = \epsilon_m \ket{m} .

The matrix elements :math:`M_{mn}` are

.. math::
   \mathscr M_{mn} &= \bra{m} e^{-i(t-t')\hat H_0}[\hat W,\hat \rho_d]e^{i(t-t')\hat H_0} \ket{n} \\
   & = e^{-i(t-t')\epsilon_m} \bra{m} [\hat W, \hat \rho_d] \ket{n} e^{i(t-t')\epsilon_n} \\
   & = \sum_\mu e^{-i(t-t')\epsilon_m} (\bra{m} \hat W \ket{\mu} \bra{\mu} \hat \rho_d \ket{n} - \bra{m} \hat \rho_d \ket{\mu}\bra{\mu} \hat W \ket{n} )e^{i(t-t')\epsilon_n} \\
   & = \sum_\mu  e^{-i(t-t')\epsilon_m} (W_{m\mu}\rho_{\mu n} - \rho_{m\mu}W_{\mu n}) e^{i(t-t')\epsilon_n} \\
   & = e^{-i(t-t')\epsilon_m} ( W_{mn}P_{n} - P_{m}W_{m n} ) e^{i(t-t')\epsilon_n} .

Finally, the quantum master equation becomes

.. math::
   \partial_t P_m &= -\lambda^2 \int_0^t dt' \sum_n \left[ ( W_{mn} e^{-i(t-t')\epsilon_n} ( W_{nm}P_{m} - P_{n}W_{n m} ) e^{i(t-t')\epsilon_m}) - (e^{-i(t-t')\epsilon_m} ( W_{mn}P_{n} - P_{m}W_{m n} ) e^{i(t-t')\epsilon_n} )W_{nm}  \right] \\
   & =  -\lambda^2 \int_0^t dt' \sum_n \left[ ( W_{mn} e^{-i(t-t')(\epsilon_n - \epsilon_m )  }  W_{nm} (P_{m} - P_{n}) - (e^{-i(t-t')\epsilon_m} ( W_{mn}P_{n} - P_{m}W_{m n} ) e^{i(t-t')\epsilon_n} )W_{nm}  \right] \\
   & = -2 \lambda^2 \int_0^t dt' \sum_n \left\vert W_{mn} \right\vert^2 \left[ P_n- P_m \right] \cos((\epsilon_m-\epsilon_n)(t-t'))
   :label: eqn-qme-pm-fgr

The above equation :eq:`eqn-qme-pm-fgr` is the :highlit:`Fermi's golden rule`.

We define :math:`\Omega_{mn}(t-t')=\Omega_{nm}(t-t') = 2\lambda^2 \left\vert W_{mn} \right\vert^2\cos((t-t')(\epsilon_m-\epsilon_n))`, so that the master equation,

.. math::
   \partial_t P_m = \int_0^t dt' \sum_n \left( \Omega_{mn}(t-t') P_n - \Omega_{nm}(t-t') P_m \right).
   :label: eqn-qme-pm-omega


Markovian
------------------------------

.. admonition:: The Kenkre Approach
   :class: note

   This is method tought by Professor Kenkre.

We can simplify equation :eq:`eqn-qme-pm-omega` more using the Markovian approximation,

.. math::
   \Omega_{mn}(t) = \delta(t) \left[\int_0^t d\tau \Omega_{mn}(\tau) \right].

The Laplace transform of the above equation is,

.. math::
   \tilde \Omega_{mn}(\epsilon) =  \Omega_{mn}(0),

from which the Fermi's golden rule is derived.

.. admonition:: Laplace Transform of :math:`\Omega`
   :class: toggle

   Laplace transform of integral and delta function are

   .. math::
      \mathscr L (\delta(t-a)) &= e^{-a\epsilon}, \qquad \text{for } a>0. \\
      \mathscr L (\int_0^t f(t') dt') & = \frac{1}{\epsilon} \mathscr L_\epsilon (f(t)).

   So we have the Laplace transform of :math:`\Omega_{mn}(t) = \delta(t) \int_0^t d\tau \Omega_{mn}(\tau)` on both sides,

   .. math::
      \tilde \Omega_{mn}(\epsilon) & = \int_0^\infty dt e^{-\epsilon t}  \delta(t) \int_0^t d\tau \Omega_{mn}(\tau) \\
      & = \int_0^\infty \frac{1}{-\epsilon}  \delta(t) \int_0^t d\tau \Omega_{mn}(\tau) d e^{-\epsilon t} \\
      & = \frac{1}{\epsilon} \int_0^\infty   e^{-\epsilon t} d\left(\delta(t) \int_0^t d\tau \Omega_{mn}(\tau) \right)  \\
      & = \frac{1}{\epsilon} \int_0^\infty   e^{-\epsilon t} \int_0^t d\tau \Omega_{mn}(\tau)   d\left(\delta(t) \right) + \frac{1}{\epsilon} \int_0^\infty   e^{-\epsilon t}  \delta(t)  d\left( \int_0^t d\tau \Omega_{mn}(\tau) \right)  \\
      & = \frac{1}{\epsilon} \int_0^\infty   e^{-\epsilon t}  \delta(t) \Omega_{mn}(t)  dt  \\
      & = \frac{1}{\epsilon}   \Omega_{mn}(0)



Markovian - The Second Approach
----------------------------------

.. admonition:: :math:`\hbar=1`
   :class: hint

   We use the natural unit system.

Here is a second Markovian approach to derive the Fermi's golden rule from quantum master equation. [2]_

The quantum master equationin the interaction picture is

.. math::
   \partial_t P_m & =  -\lambda^2/\hbar^2 \int_0^t dt' \sum_n \left[ ( W_{mn} e^{-i(t-t')(\epsilon_n - \epsilon_m ) /\hbar }  W_{nm} (P_{m} - P_{n}) - (e^{-i(t-t')\epsilon_m/\hbar} ( W_{mn}P_{n} - P_{m}W_{m n} ) e^{i(t-t')\epsilon_n/\hbar} )W_{nm}  \right] \\
   & = -\lambda^2/\hbar^2 \int_0^t dt' \sum_n \left[ ( e^{it\epsilon_m/\hbar}W_{mn} e^{-i t \epsilon_n/\hbar } e^{it'\epsilon_n/\hbar} W_{nm} e^{-it'\epsilon_m/\hbar} (P_{m} - P_{n}) - (e^{it\epsilon_m/\hbar}  W_{mn} e^{-it\epsilon_n/\hbar} (P_{n} - P_{m}) e^{it'\epsilon_n/\hbar} )W_{nm} e^{-it'\epsilon_m/\hbar} \right] \\
   & = -\lambda^2/\hbar^2 \sum_n \left[  \int_0^t dt' W_{mn}^I W_{nm}^I(P_m-P_n) - \int_0^t dt' W_{mn}^I W_{nm}^I(P_n-P_m)  \right]


In a Markov process, **the two point correlation in time** is zero at different time in the correlation function,

.. math::
   \mathrm{Corr}(t_1,t_2)=0

for all :math:`t_1\not= t_2`. In our master equation,

.. math::
   &\int_0^t dt' W_{mn}^I(t) W_{nm}^I(t')(P_m(t')-P_n(t')) \\
   & = \int_0^t dt' W_{mn}^I(t-t') W_{nm}^I(0)(P_m(t)-P_n(t)) \\
   & = (P_m(t)-P_n(t)) \lim_{t\rightarrow \infty}\int_0^t dt' W_{mn}^I(t-t') W_{nm}^I(0) .

.. admonition:: Kenkre Approach
   :class: note

   This is the same as the previous Markov approach (Kenkre approach).

The master equation in interaction picture becomes

.. math::
   \partial_t P_m(t) &= -\frac{\lambda^2}{\hbar ^2} \sum_n(P_m - P_n) \left[ \lim_{t\rightarrow \infty} \left( \int_0^t dt' e^{i(t-t')\epsilon_m/\hbar} W_{mn} e^{-i(t-t')\epsilon_n/\hbar} W_{nm} + \int_0^t dt' e^{-i(t-t')\epsilon_m/\hbar} W_{mn} e^{i(t-t')\epsilon_n/\hbar} W_{nm} \right) \right] \\
   & = -\frac{\lambda^2}{\hbar^2} \sum_n (P_m - P_n) \left[ \lim_{t\rightarrow \infty} \left( \frac{\left| W_{mn}\right|^2 }{i\omega_{nm}} \left( e^{-it\omega_{mn}}  - e^{it\omega_{mn}}  \right) \right)   \right] \\
   & = -\frac{\lambda^2}{\hbar^2} \sum_n (P_m - P_n) \left[ 2\left| W_{mn}\right|^2  \lim_{t\rightarrow \infty}   \left( \frac{i\sin(\omega_{mn}t)}{i\omega_{nm}}   \right)   \right] \\
   & =  \sum_n (P_m - P_n) \left[  \frac{2 \pi \lambda^2 \left| W_{mn}\right|^2 }{\hbar^2}  \lim_{t\rightarrow \infty}   \left( \frac{\sin(\omega_{mn}t)}{\pi\omega_{nm}}   \right)   \right]


.. admonition:: Delta Function
   :class: hint

   We have the following expression,

   .. math::
      \lim_{\epsilon\rightarrow 0} \frac{\sin(x/\epsilon)}{\pi x} = \delta(x) .


We derive the Fermi's golden rule,

.. math::
   \partial_t P_m & =  \sum_n (P_m - P_n)   \frac{2 \pi \lambda^2 \left| W_{mn}\right|^2 }{\hbar^2}  \delta(\omega_mn)  \\
   & =  \sum_n (P_m - P_n)   \frac{2 \pi \lambda^2 \left| W_{mn}\right|^2 }{\hbar^2}  \delta((\epsilon_m - \epsilon_n)/\hbar) \\
   & =  \sum_n (P_m - P_n)   \frac{2 \pi \lambda^2 \left| W_{mn}\right|^2 }{\hbar}  \delta(\epsilon_m - \epsilon_n)

Comparing this result with the classical master equation, the transition rate is

.. math::
   \Omega_{mn} = \frac{2 \pi \lambda^2 \left| W_{mn}\right|^2 }{\hbar}  \delta(\epsilon_m - \epsilon_n)


which is exactly the Fermi's golden rule.



References
-----------


.. [1] Refer to *Quantum Noise* by Gardiner and Zoller, Chapter 5, Section 1.
.. [2] `Quantiki <http://www.quantiki.org/wiki/>`_ is a website of quantum information etc. The item about master equation is `here <http://www.quantiki.org/wiki/Master_equation>`_ .
.. [3] `Master equation for neutrinos <http://docs.neutrino.xyz/statistical-physics/master-eqn.html>`_.