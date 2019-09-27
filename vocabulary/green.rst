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
   y''(x) = f(x), \qquad y(0)= y(1)=0.


Then Green function for this problem is

.. math::
   G''(x\vert \xi) = \delta(x-\xi), \qquad G(0\vert \xi) = G(1\vert \xi) = 0.

We know the two solutions to the homogeneous equation, :math:`y=1` or :math:`y=x`. However, only the second solution can satisfy the BC. So Green function should have these properties,

.. math::
   G(x\vert \xi) = \begin{cases} c_1+c_2 x &\quad  x<\xi \\ d_1+d_2 x & \quad x>\xi .  \end{cases}

The BCs give us

.. math::
   G(x\vert \xi) = \begin{cases} c x &\quad  x<\xi \\ d(x-1) \quad x>\xi . \end{cases}


Green functon must be continuous, we have

.. math::
   c\xi = d (\xi -1).

Apply the discontinuity of the first order derivative of Green function,

.. math::
   d_x d (x-1)- d_x cx = 1.

With all these equation, we can determine the Green function,

.. math::
   G(x\vert\xi) = \begin{cases}  (\xi -1 ) x , & \qquad x<\xi  \\ \xi(x-1), & \qquad x>\xi  \end{cases}


Finally we integrate over :math:`\xi` to get the solution,

.. math::
   y(x) &= \int_0^1  G(x\vert \xi) f(\xi) d\xi  \\
   & = (x-1)\int_0^x \xi f(\xi) d\xi + x \int_x^1 (\xi -1) f(\xi) d\xi .


This is the power of Green function.
