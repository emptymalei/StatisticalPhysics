Green's Function
==================

.. index:: Green's Function


Green's Function for Second Order Differential Equations
----------------------------------------------------------


A general form of second order differential equations is written as

.. math::
   L[y] \equiv y'' + p(x) y' + q(x) y = f(x),

for :math:`a<x<b` with boundary conditions

.. math::
   B_1[y] = B_2[y] = 0.


The solution to it is

.. math::
   y(x) = \int _a ^b G(x\vert \xi) f(\xi) d\xi

where :math:`G(x\vert \xi)` is the Green's function. The Green's function is an impulse response of the dynamical system, i.e.,

.. math::
   L[G(x\vert \xi)] = \delta(x-\xi)

with the two boundary conditions,

.. math::
   B_1[G] = B_2[G] = 0.


First order differential of Green's function :math:`G'(x\vert \xi)` has a jump discontinuity at :math:`x=\xi`. This is expected since we have to have a dirac delta type of response at :math:`x=\xi`.

Examples
~~~~~~~~~~~~~~~~~


For a 2nd order differential equation,

.. math::
   y''(x) = f(x), \qquad y(0)= y(1)=0,


the Green function is

.. math::
   G''(x\vert \xi) = \delta(x-\xi), \qquad G(0\vert \xi) = G(1\vert \xi) = 0.

We already know the two solutions to the homogeneous equation, :math:`y=1` or :math:`y=x`. However, only the second solution can satisfy the boundary conditions. Then the Green's function should have these properties,

.. math::
   G(x\vert \xi) = \begin{cases} c_1+c_2 x, &\quad  x<\xi \\ d_1+d_2 x. & \quad x>\xi  \end{cases}

The boundary conditions give us

.. math::
   G(x\vert \xi) = \begin{cases} c x, &\quad  x<\xi \\ d(x-1). & \quad x>\xi  \end{cases}


We also know that the Green's functon must be continuous, we then require

.. math::
   c\xi = d (\xi -1).

Using the discontinuity of the first order derivative of the Green's function, we get

.. math::
   d_x d (x-1)- d_x cx = 1.

With all these equation, we determine the Green's function,

.. math::
   G(x\vert\xi) = \begin{cases}  (\xi -1 ) x , & \qquad x<\xi  \\ \xi(x-1). & \qquad x>\xi  \end{cases}


To get the solution to :math:`y`, we integrate over :math:`\xi`,

.. math::
   y(x) &= \int_0^1  G(x\vert \xi) f(\xi) d\xi  \\
   & = (x-1)\int_0^x \xi f(\xi) d\xi + x \int_x^1 (\xi -1) f(\xi) d\xi .

It is that easy. This is the super power of the Green's function.
