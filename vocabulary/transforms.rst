.. index:: Laplace Transform

Transforms
===========



Fourier Transform
--------------------

Fourier transforms are quite useful in solving differential equations. By decomposing the functions using Fourier transform, we might be able to simplify many differential equations.

Suppose we have a differential equation

.. math::
   \frac{\partial}{\partial x} f(x) = a g(x).

To solve the equation, we decompose :math:`f(x)` using its Fourier transform,

.. math::
   f(x) = \frac{1}{2\pi} \int_{-\infty}^{\infty} f(k) e^{ikx} dk.

Then we get

.. math::
   \frac{1}{2\pi}\frac{\partial}{\partial x} \int_{-\infty}^{\infty} f(k) e^{ikx} dk = a \frac{1}{2\pi}\int_{-\infty}^{\infty} g(k) e^{ikx} dk.

The equation is then simplified into

.. math::
   ik f(k) = a g(k).


.. note::
   To summarize, we simple do replacement of the differential operators.

   .. math::
      \frac{\partial}{\partial x} e^{ikx}=ike^{ikx} &\implies \frac{\partial}{\partial x} \to ik \\
      \frac{\partial^2}{\partial x^2} e^{ikx} = -k^2 e^{ikx} & \implies \frac{\partial^2}{\partial x^2} \to -k^2


Laplace Transform
--------------------

Similar to Fourier transform, Laplace transform is also useful in equation solving.

Laplace transform is a transform of a function of :math:`t`, e.g. :math:`f(t)`, to a function of :math:`s`,

.. math::
   \mathscr{L}[f(t)] = \int_0^\infty f(t) e^{ - s t} dt .

Some useful properties:

1. :math:`\mathscr{L}[\frac{d}{dt}f(t)] = s \mathscr{L}[f(t)] - f(0)`;
2. :math:`\mathscr{L}[\frac{d^2}{dt^2}f(t) = s^2 \mathscr{L}[f(t)] - s f(0) - \frac{d f(0)}{dt}`;
3. :math:`\mathscr{L}[\int_0^t g(\tau) d\tau ] = \frac{\mathscr{L}[f(t)]}{s}`;
4. :math:`\mathscr{L}[\alpha t] = \frac{1}{\alpha} \mathscr{L}[s/\alpha]`;
5. :math:`\mathscr{L}[e^{at}f(t)] = \mathscr{L}[f(s-a)]`;
6. :math:`\mathscr{L}[tf(t)] = - \frac{d}{ds} \mathscr{L}[f(t)]`.



Some useful results:

1. :math:`\mathscr{L}[1] = \frac{1}{s}`;
2. :math:`\mathscr{L}[\delta] = 1`;
3. :math:`\mathscr{L}[\delta^k] = s^k`;
4. :math:`\mathscr{L}[t] = \frac{1}{s^2}`;
5. :math:`\mathscr{L}[t^n] = \frac{n!}{s^{n+1}}`
6. :math:`\mathscr{L}[e^{at}]= \frac{1}{s-a}`.


A very nice property of Laplace transform is

.. math::
   \mathscr{L}_s [e^{at}f(t)] &= \int_0^\infty e^{-st} e^{-at} f(t) dt \\
   & =  \int_0^\infty e^{-(s+a)t}f(t) dt \\
   & = L_{s+a}[f(t)]

which is very useful when dealing with master equations.

Two useful results are

.. math::
   \mathscr{L}[I_0(2Ft)] = \frac{1}{\sqrt{ \epsilon^2 - (2F)^2 }}

and

.. math::
   \mathscr{L}[J_0[2Ft]]  = \frac{1}{\sqrt{\epsilon^2 + (2F)^2}},

where :math:`I_0(2Ft)` is the modified Bessel functions of the first kind. :math:`J_0(2Ft)` is its companion.


Using the property above, we can find out

.. math::
   \mathscr{L}[I_0(2Ft)e^{-2Ft}]  = \frac{1}{\sqrt{(\epsilon + 2F)^2 - (2F)^2}} .


.. admonition:: Example: Solving Differential Equations
   :class: toggle

   For a first order differential equation

   .. math::
      f'(x) = x,

   we apply Laplace transform,

   .. math::
      s F(s) - f(0) = \frac{1}{s^2},

   from which we solve

   .. math::
      F(s) = \frac{1}{s^3} + \frac{f(0)}{s}.

   Then we lookup in the transform table, we find that

   .. math::
      f(x) = x^2/2 + f(0).



.. _legendre-transform:

Legendre Transform
-------------------------

The geometrical meaning of Legendre transformation in thermodynamics can be illustrated by the following graph.


.. figure:: images/LegendreTransform.png
   :align: center
   :alt: Legendre Transform made clear

   Legendre transform

In the above example, we know that entropy :math:`S` is actually a function of temperature :math:`T`. For simplicity, we assume that they are monotonically related like in the graph above. When we are talking about the quantity :math:`T \mathrm d S` we actually mean the area shaded with blue grid lines. Meanwhile the area shaded with orange line means :math:`S \mathrm d T`.

Let's think about the change in internal energy. For this example, we only consider the thermal part,

.. math::
   \mathrm d U = T \mathrm d S  .

Internal energy change is equal to the the area shaded with blue lines. The area shaded with orange lines is the Helmholtz free energy,

.. math::
   \mathrm d A = S \mathrm d T .

The two quantities :math:`T \mathrm d S` and :math:`S \mathrm d T` sum up to :math:`d(TS)`. This is also the area change of the rectangle determined by two edges :math:`0` to :math:`T` and :math:`0` to :math:`S`.

This is a Legendre transform,

.. math::
   \mathrm d U \to \mathrm d A,

or

.. math::
   T\mathrm dS \to S \mathrm d T.

The point is that :math:`S(T)` is a function of :math:`T`. However, if we know the blue area, we can find out the orange area. This means that the two functions :math:`A(T)` and :math:`U(S)` are somewhat like a pair. Choosing one of them for a specific calculation is a choice of freedom but we carry all the information in either one once the relation between :math:`T` and :math:`S` is know.

The above example sheds light on Legendre transform. The mathematical form is a little bit tricky so we will illustrate it using an example. For a function :math:`U(T, X)`, we find its differential as

.. math::
    \mathrm d U(T, X) = \frac{\partial U}{\partial T} \mathrm d T + \frac{\partial U}{\partial X} \mathrm d X.

For convinience, we define

.. math::
   S =& \frac{\partial U}{\partial T} \\
   Y =& \frac{\partial U}{\partial X}.

The differential of function becomes

.. math::
   \mathrm d U(T, X) = S \mathrm dT + Y \mathrm d X,

where :math:`S` (:math:`Y`) and :math:`T` (:math:`X`) are a conjugate pair.

A Legendre transform says that we change the variable of the differential from :math:`T` (:math:`X`) to :math:`S` (:math:`Y`). For example, we know that

.. math::
   S \mathrm d T = \mathrm d (ST) - T \mathrm d S.

Plugging this into :math:`\mathrm d U`, we get

.. math::
   \mathrm d U(T, X) - \mathrm d(ST) = - T \mathrm dS + Y \mathrm d X.

The left hand side is defined as a new differential

.. math::
   \mathrm d A(S, X) = \mathrm d ( U(T, X) - ST ).

In these calculations, :math:`U` is the internal energy and :math:`A` is the Helmholtz free energy. The transform that changes the variable from :math:`X` to :math:`Y` gives us enthalpy :math:`H`. If we transform both variables then we get Gibbs free energy :math:`G`. More about these thermodynamic potentials will be discussed in the following chapters.



Refs & Note
------------------

1. Zia, Royce K. P., Edward F. Redish and Susan R. McKay. “Making sense of the Legendre transform.” (2009).