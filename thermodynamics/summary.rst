Summary
************************


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

   if we have :math:`\mathbf{d}\underset{^\sim}{\omega} \wedge \underset{^\sim}{\omega}=0`, which is easily proven to be true here since we have repeated basis if we write it down.

   Or if we are back to functions,

   .. math::
      T(U,V)\mathbf{d}S = p \mathbf{d}V + \mathbf{d}U.
      :label: thermodynamics-not-the-second-law


   A list of references for differential geometry and thermodynamics:

   1. Bernard Schutz, Geometrical Methods in Mathematical Physics.


With the help of differential forms, we could derive the Maxwell identities more easily by rewriting the functions to be functions of other variables. The punch line is the exterior derivative of equation :eq:`thermodynamics-not-the-second-law`, 

.. math::
   \mathbf{d} T \wedge \mathbf{d} S = \mathbf{d} p \wedge \mathbf{d} V.

Maxwell identities are obtained by writing functions as functions of :math:`(S,V)` or :math:`T,V` etc.




Gas
===================


* Van der Waals gas $\left( p + \frac{a}{V^2} \right) (V - b) = R T$.


Refs & Notes
=====================