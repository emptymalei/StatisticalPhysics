Why does equilibrium state exists?
=====================================

In equilibrium statistical mechanics, the theories predict only one value for the thermodynamic observables. No variance or confidential level is given.

In experiments, the measured observables of equilibrum systems have quite small variance. Naturally, we assumed the theoretical values for the observables to be one fixed value and treat the variances as experimental uncertaintities. However, this is not accurate. Statistically speaking macroscopic systems have fluctuating observables, though tiny enough to be ignored. [Lysogorskiy2012]_


In most cases, we merely confine a few macroscopic observables. Why does equilibrium state exist?


Quantum Mechanics
-----------------------------------

In this section, we argue that requiring the average energy of a whole quantum mechanical system to be constant, a.k.a., constant of motion, leads to constant or almost constant observables. We follow the derivation in [Buck2015]_.

The Schrodinger equation reads

.. math::
   i \frac{\partial \ket{\Psi (t)} }{\partial t} = \hat {\mathscr H} \ket{\Psi (t)},

where :math:`\ket{\Psi (t)}` is the state describing the whole system of many particles. The general solution is

.. math::
   \ket{\Psi(t)} = \sum a_n e^{-i E_n t} \ket{\psi_n},

where :math:`\ket{\psi_n}` are the energy eigenstates, :math:`E_n` are the energy eigen values.

Conservation of energy says

.. math::
   \frac{\partial \bra{ \Psi (t) } \hat {\mathscr H} \ket{\Psi (t)} }{\partial t} = 0.


Suppose we have an **observable that commutes with the Hamiltonian**, i.e., :math:`\left[\hat {\mathscr O}, \hat {\mathscr H} \right] = 0`, the expectation of the observable is also constant of motion, i.e.,

.. math::
   \frac{\partial \bra{ \Psi (t) } \hat {\mathscr O} \ket{\Psi (t)} }{\partial t} = 0.

Suppose we have an **observable that does't commute with the Hamiltonian**, i.e., :math:`\left[\hat {\mathscr O} , \hat {\mathscr H} \right] \neq 0`, the expectation of the observable is

.. math::
   & \bra{ \Psi (t) } \hat {\mathscr O} \ket{\Psi (t)} \\
   =& \sum_{m,n}a^*_m a_n \bra{\phi_m} \hat{\mathscr O} \ket{\phi_n} e^{-i (E_n - E_m) t} \\
   = & \sum_{m,n} \delta_{m,n} a^*_m a_n \bra{\phi_m} \hat {\mathscr O} \ket{\phi_n} + \tilde O(t),

where :math:`\tilde O(t)` is the time dependent part

.. math::
   \tilde O(t) = \sum_{m \neq n} a^*_m a_n \bra{\phi_m} \hat {\mathscr O} \ket{\phi_n} e^{-i (E_n - E_m) t} \equiv \sum_{m, n} A_{mn} O_{mn} e^{-i(E_n - E_m)t},

where :math:`A_{mn} \delta_{mn} = 0` and both :math:`A_{mn}` and :math:`O_{mn}` are hermitian. The key is to prove that :math:`\tilde O(t)` only provides small fluctuations. Unless the terms satisfies some specific coherent conditions, those oscillations will not add up to large values. Thus the time dependent term provides fluctuations only.

In other words, a quantum mechanical system has equilibrium states.




References
-----------------------------

.. [Lysogorskiy2012] `Lysogorskiy, Y. V., Wang, Q. A., & Tayurskii, D. A. (2012). Study of energy fluctuation effect on the statistical mechanics of equilibrium systems. Journal of Physics: Conference Series, 394(1). <https://doi.org/10.1088/1742-6596/394/1/012006>`_
.. [Buck2015] `Buck, B., & Merchant, A. C. (2015). Probabilistic Foundations of Statistical Mechanics: A Bayesian Approach. <http://arxiv.org/abs/1512.01368>`_