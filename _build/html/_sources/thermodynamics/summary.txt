Summary
************************


Thermodynamics is about the desciption of large systems which is mostly about the following keypoints. (*A Modern Course in Statistical Physics* by L. E. Reichl)

1. Thermodynamic variables; extensive, intensive, neither;
2. Equations of state;
3. Four fundamental laws of thermodynamics;
4. Thermodynamics potentials
5. Phase transitions
6. Response
7. Stability

Anyway, thermodynamics is a kind of theory that deals with black boxes. We manipulate any variables we like and look at the changes. Then we summarize and get a set of laws.




.. index:: Thermodynamic Potentials

.. _thermodynamical-potentials:

Thermodynamic Potentials
==========================================

The first thermodynamics potential we can think of is the (differential) internal energy, which, by definition is a function of entropy :math:`S`, volume :math:`V` and number of particles :math:`N_i`,

.. math::
   d U(S,V,\{N_i\}) = T dS - p dV + \mu_i d N_i,

where repeated indices are summed over. The simplest way to generate all the other thermodynamics potentials is to use Legendre transform, which is explained in :ref:`legendre-transform`.

Mathematically, three-variable function will generate seven extra functions through Legendre transform. The differential forms of them are

.. math::
   dA(T,V,\{N_i\}) & = dU(S,V,\{N_i\}) - d(ST) = - S dT - p dV + \mu_i dN_i\\
   dH(S,p,\{N_i\}) & = dU(S,V,\{N_i\}) - d(-pV) = T dS + V dp + \mu_i dN_i \\
   dG(T,Y,\{N_i\}) & = dU(S,V,\{N_i\}) - d(ST)-d(-pV) = -S dT + V dp + \mu_i dN_i \\
   d\Omega (T,X,\{\mu_i\}) & = dU(S,V,\{N_i\}) - d(ST) - d(\mu_i N_i) = -SdT - pdV - N_i d\mu_i\\
   d\kappa_1(T,Y,\{\mu_i\})& = dU(S,V,\{N_i\}) - d(ST) - d(\mu_iN_i) - d(-pV) = -SdT + V dp - N_i d\mu_i\\
   d\kappa_2(T,V,\{\mu_i\}) & = dU(S,V,\{N_i\}) -  d(\mu_i N_i) = TdS -pdV - N_i d\mu_i \\
   d\kappa_3(T,p,\{\mu_i\}) & = dU(S,V,\{N_i\}) - d(-pV) - d(\mu_i N_i) = TdS + Vdp - N_i d\mu_i.

Physically, there are at three different kinds of couplings here, which are

* thermal coupling: :math:`d(ST)`;
* mechanical coupling: :math:`d(pV)`;
* chemical coupling: :math:`d(\mu_i N_i)`.

Legendre transform, in an easy understanding, is about turning on and off switches of the three different couplings. Turning off the mechanical coupling of (differential) internal energy :math:`dU(S,V,\{N_i\})` leads to (differential) enthalpy :math:`dH(S,p,\{N_i\})`. Indeed, enthalpy is the same as internal energy when we are talking about constant pressure.

Let's sum up.

1. Internal Energy
2. Enthalpy
3. Helmholtz Free Energy
4. Gibbs Free Energy
5. Grand Potential

The relations between them? All potentials are Legendre transformation of each other. To sum up, let's gliffy.

.. image:: images/thermodynamicPotentials.png
   :alt: Thermodynamic Potentials
   :scale: 80%

(The gliffy source file is `here <images/thermodynamicPotentials.gliffy>`_ . Feel free to download and create your own version.)

This graph needs some illustration.

1. Legendre transformation: :math:`ST-U(S)` transform a funcion :math:`U(S)` with variable :math:`S` to another function :math:`H(T)`. However, in thermodynamics use the different sign can be more convinient. In other words, :math:`U(S)` and :math:`-H(T)` are dual to each other.
2. Starting from this graph, we can find out the differentials of thermodynamic potentials. Next take the partial derivatives of thermodynamic potential with respect to their own variables. By comparing the partial derivatives and the definitions of them, we find out expressions of their vairables. Finally different expressions for the same variable are equal, which are the Maxwell relations.
3. As we have seen in 2, all the thermodynamic quantities can be obstained by taking the derivatives of thermodynamic potentials.



.. hint::
   **Question:** Mathematically we can construct the sixth potential namely the one that should appear at the right bottom of the graph. Why don't people talk about it?

   We can surely define a new potential called :math:`Null(T,X,\{\mu_i\})`. However, the value of this function is zero. So we can have the derivitive of this potential is also zero. This is the Gibbs Duhem equation.

   The answer I want to hear is that this is something :math:`\mathrm d\mathrm d f = 0` where f is exact.


.. hint::
   **Question**: Why is internal energy :math:`U` a function of three extensive quantities, :math:`V`, :math:`S`, :math:`N`?

   There are three aspects to be considered.




Differential Forms
=============================

This has always been confusing to use so many differential potentials. The trick of math is to discuss in the theory of differential forms.

.. admonition:: What Are Forms
   :class: note

   In simple words, 1-forms are linear mapping of functions to numbers.

   For illustration purpose, we take the simple case that

   .. math::
      \bar d Q = p dV + dU.

   We know that :math:`dU` is a 1-form and it can be the basis of 1-forms, so is :math:`dV`. Also notice that we could difine a map from a point :math:`(U,V)` to a real number, which explains the pressure :math:`p(U,V)`. As a result, :math:`\bar dQ` is also a 1-form. Rewrite the equation using the language of forms,

   .. math::
      \underset{^\sim}{\omega} = p \underset{^\sim}{dV} + \underset{^\sim}{dU},

   where the under tilde denotes 1-form. However, :math:`\underset{^\sim}{\omega}` is not exact, which means that we do not find a function :math:`Q(U,V)` on the manifold so that :math:`\mathbf{d d }Q = 0`. Following Bernard Schutz in his Geometrical Methods in Mathematical Physics, an exact :math:`\underset{^\sim}{\omega}` means that

   .. math::
      \mathbf{d}\underset{^\sim}{\omega}=0=\mathbf{dd}Q = \mathbf{d}p\wedge \underset{^\sim}{dU}=\left( \frac{\partial p}{\partial U} \right)_V \underset{^\sim}{dU}\wedge \underset{^\sim}{dV},

   where we have used the condition that :math:`\underset{^\sim}{dU}` is exact, i.e., :math:`\mathbf{d}\underset{^\sim}{dU}=0`. In order for it to be valid at all point, we have to require :math:`\left( \frac{\partial p}{\partial U} \right)_V=0` at all points on the manifold.

   `Frobenius' theorem <https://en.wikipedia.org/wiki/Frobenius_theorem_(differential_topology)>`_ tells us that we will find functions on the manifold so that :math:`\underset{^\sim}{\omega}=T(U,V)\mathbf{d}S`, which gives us

   .. math::
      T(U,V)\mathbf{d}S = p \underset{^\sim}{dV} + \underset{^\sim}{dU},

   if we have :math:`\mathbf{d}\underset{^\sim}{\omega} \wedge \underset{^\sim}{\omega}=0`, which is easily proven to be true here since we have repeated basis if we write it down (no n+1 forms on n-dimension manifold).

   Or if we are back to functions,

   .. math::
      T(U,V)\mathbf{d}S = p \mathbf{d}V + \mathbf{d}U.
      :label: thermodynamics-not-the-second-law


   A list of references for differential geometry and thermodynamics:

   1. Bernard Schutz, Geometrical Methods in Mathematical Physics.
   2. Hannay, J. H. (2006). Carnot and the fields formulation of elementary thermodynamics. American Journal of Physics, 74(2), 134. doi:10.1119/1.2121755


With the help of differential forms, we could derive the Maxwell identities more easily by rewriting the functions to be functions of other variables. The punch line is the exterior derivative of equation :eq:`thermodynamics-not-the-second-law`,

.. math::
   \mathbf{d} T \wedge \mathbf{d} S = \mathbf{d} p \wedge \mathbf{d} V.

Maxwell identities are obtained by writing functions as functions of :math:`(S,V)` or :math:`T,V` etc.


The questions is, how could this formalism help us understanding more of the laws of thermodynamics. As an example, we examine second law using differential forms. For a more general composite system which has more dimensions or basis, we write down a one form that is related to heat production,

.. math::
   \underset{^\sim}{\omega_n} = \sum_{i=1}^N \left( p_i \mathbf{d} V_i + \mathbf{d} U_i \right).

In general, on a n-dimension manifold, we could have non-zero :math:`\mathbf{d}\underset{^\sim}{\omega} \wedge \underset{^\sim}{\omega}` since we have up to non-zero n-forms. The meaning is that we do not find global temperature and entropy on the whole manifold [BSchutz]_ or no globally integrable function of heat exchange :math:`\underset{^\sim}{\omega_n}`.

Regarding the geometrical meaning of 1-forms, which are surfaces of equi-function values, just like equipotential lines, we think of a system that has a global entropy and temperature with such equi-entropy surfaces. One of the aspects of the second law thus is to state that for a system that has no heat exchange :math:`\underset{^\sim}{\omega}=0`, it is restricted on a curtain part of the phase space, i.e., it has limited states compared to the whole possible states on the manifold. In the language of differential forms, the second law is all about the existance of entropy, by Caratheodory's theorem.


Related Papers
------------------

1. Samuel L. Braunstein and Carlton M. Caves, `Statistical distance and the geometry of quantum states <http://journals.aps.org/prl/abstract/10.1103/PhysRevLett.72.3439>`_, Phys. Rev. Lett. 72, 3439.


.. [BSchutz] Bernard Schutz, *Geometrical Methods in Mathematical Physics*.








.. index:: Laws of Thermodynamics

The Laws of Four
========================


.. admonition:: Zeroth Law of Thermodynamics
   :class: admonition-laws

   **Zeroth** Law: A first peek at temperature

   Two bodies, each in thermodynamic equilibrium with a third system, are in thermodynamic equilibirum with each other.

   This gives us the idea that there is a universal quantity which depends only on the state of the system no matter what they are made of.




.. admonition:: First Law of Thermodynamics
   :class: admonition-laws

   **First** Law: Conservation of energy

   Energy can be transfered or transformed, but can not be destroyed.


   In math,

   .. math::
      \mathrm d U  = W + Q

   where :math:`W` is the energy done to the system, :math:`Q` is the heat given to the system. A better way to write this is to make up a one-form :math:`\underset{^\sim}{\omega}`,

   .. math::
      \underset{^\sim}{\omega} \equiv \mathbf d U  - \underset{^\sim}{W},

   where in gas thermodynamics :math:`\underset{^\sim}{W}=-p\mathbf{d}V`.



   Using Legendre transformation, we know that this one form have many different formalism.



.. admonition:: Second Law of Thermodynamics
   :class: admonition-laws

   **Second** Law: Entropy change; Heat flow direction; Efficieny of heat engine

   There are three different versions of this second law. Instead of statements, I would like to use two inequalities to demonstrate this law.

   .. math::
      \eta = \frac{\Delta W}{\Delta Q} \le 1

   For isolated systems,

   .. math::
      \mathrm d S \ge 0

   Combine second law with first law, for reversible systems, :math:`Q = T \mathrm d S`, or :math:`\underset{^\sim}{\omega}=T\mathbf{d}S`, then for ideal gas

   .. math::
      \mathbf  d S = \mathbf d U + p \mathbf d V

   Take the exterior derivative of the whole one-form, and notice that :math:`U` is exact,

   .. math::
      \left(\frac{\partial T}{\partial V}\right)_S \mathbf d V \wedge \mathbf d S = \left( \frac{\partial p}{\partial S}\right)_S \mathbf d S \wedge \mathbf d V

   Clean up this equation we will get one of the Maxwell relations. Use Legendre transformation we can find out all the Maxwell relations.





   .. index:: Second Definition of Temperature
   .. index:: Thermodynamic Temperature

   .. admonition:: Second Definition of Temperature
      :class: hint

      Second definition of temperature comes out of the second law. By thinking of two reversible Carnot heat engines, we find a funtion depends only a parameter which stands for the temperature like thing of the systems. This defines the **thermodynamic temeprature**.


.. admonition:: Third Law of Thermodynamics
   :class: admonition-laws

   **Third** Law: Abosoulte zero; Not an extrapolation; Quantum view

   The difference in entropy between states connected by a reserible process goes to zero in the limit :math:`T\rightarrow 0 K`.

   Due to the asymptotic behavior, one can not get to absolute zero in a finite process.





.. index:: Entropy

The Entropy
================

When talking about entropy, we need to understand the properties of cycles. The most important one is that

.. math::
   \sum_{i=1}^n \frac{Q_i}{T_i} \leq 0

where the equality holds only if the cycle is reversible for the set of processes. In another sense, if we have infinitesimal processes, the equation would have become

.. math::
   \oint \frac{\mathrm d Q}{T} = 0 .

The is an elegent result. It is intuitive that we can build correspondence between one path between two state to any other paths since this is a circle. That being said, the following integral

.. math::
   \int_A^B \frac{\mathrm d Q}{T},

is independent of path on state plane. We imediately define :math:`\int_A^B \frac{\mathrm d Q}{T}` as a new quantity because we really like invariant quantities in physics, i.e.,

.. math::
   S(B) - S(A) = \int_A^B \frac{\mathrm d Q}{T},

which we call entropy (difference). It is very important to realize that entropy is such a quantity that only dependents on the initial and final state and is independent of path. Many significant results can be derived using only the fact that entropy is a function of state.

1. Adiabatic processes on the plane of state never go across each other. Adiabatic lines are isoentropic lines since :math:`\mathrm dS = \frac{\mathrm dQ}{T}` as :math:`\mathrm dQ = 0` gives us :math:`\mathrm dS = 0`. The idea is that at the crossing points of adiabatic lines we would get a branch for entropy which means two entropy for one state.
2. No more than one crossing point of two isothermal lines is possible. To prove it we need to show that entropy is a monotomic equation of :math:`V`.
3. We can extract heat from one source that has the same temperature and transform into work if the isoentropic lines can cross each other which is not true as entropy is quantity of state. Construct a system with a isothermal line intersects two crossing isoentropic lines.
4. We can extract heat from low temperature source to high temperature source without causing any other results if we don't have entropy as a quantity of state.




Irreversiblity
===================


1. some discussion here. :ref:`irreversiblity`


This problem can be understood by thinking of the statistics. Suppose we have a box and N gas molecules inside. We divide it into two parts, left part and right part. At first all the particles are in the L part. As time passing by the molecules will go to the R part.

The question we would ask is what the probablity would be if all the particles comes back to the L part. By calculation we can show that the ratio :math:`R` of number of particles on L part and R part,

.. math::
   R = \frac{N_L}{N-N_R},

will have a high probability to be 0.5, just as fascinating as central limit theorem.








Gas
===================


* Van der Waals gas $\left( p + \frac{a}{V^2} \right) (V - b) = R T$.


Refs & Notes
=====================
