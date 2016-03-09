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





Gas
===================


* Van der Waals gas $\left( p + \frac{a}{V^2} \right) (V - b) = R T$.
