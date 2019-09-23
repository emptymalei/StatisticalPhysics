.. index:: Laplace Transform

Transforms
===========



Fourier Transform
--------------------

Fourier transform for continuous equation is

.. math::
   \frac{\partial}{\partial x} e^{ikx}=ike^{ikx} &\implies \frac{\partial}{\partial x} \to ik \\
   \frac{\partial^2}{\partial x^2} e^{ikx} = -k^2 e^{ikx} & \implies \frac{\partial^2}{\partial x^2} \to -k^2


Laplace Transform
--------------------

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
5. :math:`\mathscr{L}[e^{at}]= \frac{1}{s-a}`.


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





.. _legendre-transform:

Legendre Transform
-------------------------



The geometrical of physical meaning of Legendre transformation in thermodynamics can be illustrated by the following graph.


.. figure:: images/LegendreTransform.png
   :align: center
   :alt: Legendre Transform made clear

   Legendre transform

For example, we know that entropy :math:`S` is actually a function of temperature :math:`T`. For simplicity, we assume that they are monotonically related like in the graph above. When we are talking about the quantity :math:`T \mathrm d S` we actually mean the area shaded with blue grid lines. Meanwhile the area shaded with orange line means :math:`S \mathrm d T`.

Let's think about the change in internal energy which only the thermal part are considered here, that is,

.. math::
   \mathrm d U = T \mathrm d S  .

So internal energy change is equal to the the area shaded with blue lines. Now think about a three dimensional graph with a third axis of internal energy which I can't show here. Notice that the line of internal energy is on the plane which is vertical to :math:`{T, S}` plane and contains the line black line in the graph above. The change of internal energy with an increase of :math:`\mathrm dS` is the value that the line of internal energy goes up.

Now we do such a transform that we actually remove the internal energy from :math:`\mathrm d ( T S )`, which finally gives us Helmholtz free energy,

.. math::
   \mathrm d A = S \mathrm d T .

It's obvious that after this Legendre transform, the new area is the part shaded with orange lines.

Now the key point is that :math:`S(T)` is a function of :math:`T`. So if we know the blue area then we can find out the orange area, which means that the two function :math:`A(T)` and :math:`U(S)` are identical. Choosing one of them for a specific calculation is a kind of freedom and won't change the final results.




Refs & Note
------------------
