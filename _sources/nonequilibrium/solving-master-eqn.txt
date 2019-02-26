Solving Master Equations
========================================

.. index:: Master Equation

.. role:: highlit


Solving Master Equations
-----------------------------

Master equation, again, is

.. math::
   \frac{d P_m}{dt} = \sum_n R_{mn} P_n - \sum_n R_{nm} P_m

which can be written as a more simple form,

.. math::
   \frac{d P_m}{dt} + \sum_n A_{mn}P_n = 0 .

To figure out the elements of this new matrix :math:`A`, we need to understand how to combine the RHS of master equation.

.. math::
   \partial_t \begin{pmatrix} P_1 \\ P_2 \\ \vdots \\ P_N \end{pmatrix} = \begin{pmatrix} 0  & R_{12} & \cdots & R_{1N} \\ R_{21}  & 0 & \cdots & R_{2N} \\ \vdots & \vdots & \ddots & \vdots \\ R_{N1} & R_{N2} & \cdots & 0   \end{pmatrix} \begin{pmatrix} P_1 \\ P_2 \\ \vdots \\ P_N \end{pmatrix}   - \sum_{n}R_{nm} \begin{pmatrix}  1 & 0 & \cdots & 0 \\  0 & 1 & \cdots & 0 \\ \vdots & \vdots & \ddots &  0  \\ 0 & 0 & \cdots & 1  \end{pmatrix}  \begin{pmatrix} P_1 \\ P_2 \\ \vdots \\ P_N \end{pmatrix}


Since :math:`A_{mm} = \sum_n R_{nm}` is just a real number, we can combine the two matrices on the RHS, which is

.. math::
   \partial_t \begin{pmatrix} P_1 \\ P_2 \\ \vdots \\ P_N \end{pmatrix} + \begin{pmatrix} A_{11}  & -R_{12} & \cdots & -R_{1N} \\ -R_{21}  & A_{22} & \cdots & -R_{2N} \\ \vdots & \vdots & \ddots & \vdots \\ -R_{N1} & -R_{N2} & \cdots & A_{NN}   \end{pmatrix} \begin{pmatrix} P_1 \\ P_2 \\ \vdots \\ P_N \end{pmatrix} = 0  .

We can define the :math:`\mathbf A` matrix now.

.. math::
   A_{mn} = \begin{cases} -R_{mn} &\quad  n \neq m \\ \sum_{n} R_{nm} & \quad n=m  \end{cases}

:math:`\mathbf A` matrix is defined in this way so that we have the master equation becomes

.. math::
   \partial_t \mathbf P + \mathbf A \mathbf P = 0 .

So solve such a matrix equation, we need to diagonalize :math:`\mathbf A`, so that we have a simple solution

.. math::
   \mathbf P_{\text{diag}} = e^{- \mathbf A_{\text{diag}} t} .


The most general way is to diagonalize it using an invertible matrix :math:`\mathbf S`, i.e.,

.. math::
   \partial_t \bf S^{-1} P + S^{-1}AS S^{-1} P = 0

in which we'll define :math:`\mathbf A_{\text{diag}} = \bf S^{-1} P S` and :math:`\mathbf P_{\text{diag}} = \bf S^{-1} P`. For simplicity, we won't write down the indices from now on.


.. warning::
   Is there a mechanism that ensures the :math:`\mathbf A` is :highlit:`invertible` ? If :math:`\mathbf A` is :highlit:`defective` , none of these can be done. Do all physical systems have invertible :math:`\mathbf A`?




.. hint::
   Notice that the form of master equation after this transform is similar to the dynamics of quantum mechanics which is

   .. math::
      i\hbar \frac{\partial }{\partial t} \ket{\psi} = \hat H \ket{\psi}.

   Another thing is that this form is also similar to Liouville equation,

   .. math::
      i\partial_t \rho^N = \hat L^N \rho^N .




Solving Master Equations: Fourier Transform
---------------------------------------------

Fourier transform is a quick and efficient way of diagonalizing :math:`\mathbf A` matrix.


We consider the case that coarsed system has translational symmetry, then we know the value of elements in :math:`\mathbf A` matrix only dependends on :math:`l:= n-m`. In ohter words,

.. math::
   \partial_t P_m  + \sum_n A_{mn} P_n  = 0.

For translational symmetric system, we can work out discrete Fourier transform to find the normal modes. Define the kth mode as

.. math::
   P^k = P_m e^{ikm} .

Multiply by :math:`e^{ikm}` on master equstion and sum over m, we get

.. math::
   \sum_m \partial_t P_m e^{ikm} + \sum_m \sum_n e^{ikm}A_{m-n} P_n = 0.

With the definition of kth mode above there, the master equation can be written as

.. math::
   \partial_t P^k + \sum_n\sum_m e^{ik(m-n)}A_{m-n} e^{ikn}P_n = 0

which "accidently" diagonalizes the matrix :math:`\mathbf A`. So define the kth mode of :math:`\mathbf A` as :math:`A^k = \sum_{l=m-n} e^{ik(m-n)}A_{m-n}` then

.. math::
   \partial_t P^k + \sum_{l=m-n}e^{ik(m-n)}A_{m-n} \sum_n e^{ikn}P_n = 0

is reduced to

.. math::
   \partial_t P^k + A^k P^k = 0 \qquad\text{No summation over k!.}

.. note::
   Note that summation over n and m is equivalent to summation over n and m-n.

Finally we have the solution of normal modes,

.. math::
   P^k(t) = P^k(0) e^{-A^k t} .

To find out the final solution, inverse Fourier transform on kth mode,

.. math::
   P_m(t) = \frac{1}{N} \sum_k P^k(t) e^{-ikm} .



.. important::
   Note that due to the Born van Karman BC we chose,

   .. math::
      e^{ikm} = e^{ik(m+N)}

   which leads to

   .. math::
      k=\frac{2\pi}{N} .

   Discrete transform will become integral if we are dealing with continous systems, which will be achieved by using the following transformation,

   .. math::
      \frac{1}{N}\sum_k  \rightarrow \frac{1}{2\pi} \int dk

   We write down this identity like transformation because the discrete result has the form :math:`\frac{1}{N}\sum_k`.




Finite Chain with Nearest Neighbor Interactions
-----------------------------------------------------


In this simple case, the transfer is

.. math::
   R_{mn} = F(\delta_{m,n-1}+ \delta_{m,n+1}) .



So master equation becomes

.. math::
   \partial_t P_m = F(P_{n+1} + P_{n-1}) -2F P_m .


.. note::
   There is no need to use the definition of :math:`\mathbf A` matrix in this simple case.

Discrete Fourier transform,

.. math::
   \partial_t P^k  = F(e^{ikm} P_{m+1} + e^{ikm} P_{m-1} -2 P^k) .

Combine terms,

.. math::
   \partial_t P^k = 4F\sin^2\frac{k}{2} .


The solution for kth mode should be

.. math::
   P^k(t) = P^k(0) e^{-4F \sin^2\frac{k}{2} t} .


Inverse Fourier transform gives us the result of

.. math::
   P_m(t)  = \frac{1}{N} \sum_ {k} P^k(t) e^{-i km} .

The last thing is to find out the value of :math:`k`. Apply Born-Von Karman boundary condition, we find that :math:`k` is quantized,

.. math::
   k = \frac{2\pi}{N} n, \qquad n=0,1,2, \cdots, N-1 .


Matrix Form
~~~~~~~~~~~~~~~~~~~~~~~

To make it clear, we'll redo this problem in matrix form.

First of all, write down master equation for this problem again,

.. math::
   \partial_t P_m = F(P_{n+1} + P_{n-1}) -2F P_m .

In the form of matrix, we have

.. math::
   \partial_t \begin{pmatrix} P_1 \\ P_2 \\ P_3 \\ P_4 \\ P_5 \\ P_6 \end{pmatrix} + F \begin{pmatrix}  2 & -1 & 0 & 0 & 0 & -1 \\ -1 & 2 & -1 & 0 & 0 & 0 \\0 & -1 & 2 & -1 & 0 & 0 \\ 0 & 0 & -1 & 2 & -1 & 0 \\ 0 & 0 & 0 & -1 & 2 & -1 \\ -1 & 0 & 0 & 0 & -1 & 2 \end{pmatrix} \begin{pmatrix} P_1 \\ P_2 \\ P_3 \\ P_4 \\ P_5 \\ P_6 \end{pmatrix} = 0



.. hint::
   An easy way to get the matrix is to write down the :math:`\mathbf R` matrix which has 0 diagonal elements, construct :math:`\mathbf A` matrix by adding minus sign to all elements and put the sum of the original elements at the diagonal in the corresponding line. Pay attention to the signs.

   Another propertity worth talking about is the :highlit:`additive of the matrices`. :highlit:`A more complicated system can be decomposed into several simple systems.`


The technique used to solve this problem is to diagonalize the 6 times 6 matrix because we can then just write down the solutions.

The way to do this is exactly what have did in the previous part, that is defining new quantities. Then we have in matrix form

.. math::
   \partial_t \begin{pmatrix} P^{k_1} \\ P^{k_2}\\ P^{k_3}\\ P^{k_4}\\ P^{k_5}\\ P^{k_6} \end{pmatrix} + 4F \begin{pmatrix} \sin^2\frac{k_1}{2} 0 & 0 & 0 & 0 & 0 \\ 0 &  \sin^2\frac{k_2}{2} & 0 & 0 & 0 & 0 \\ 0 & 0 &  \sin^2\frac{k_3}{2} & 0 & 0 & 0 \\ 0 & 0 & 0 & \sin^2\frac{k_4}{2} & 0 & 0 \\ 0 & 0 & 0 & 0 &  \sin^2\frac{k_5}{2} & 0 \\ 0 & 0 & 0 & 0 & 0 &  \sin^2\frac{k_6}{2}   \end{pmatrix} \begin{pmatrix} P^{k_1} \\ P^{k_2}\\ P^{k_3}\\ P^{k_4}\\ P^{k_5}\\ P^{k_6} \end{pmatrix} = 0

By writing in this form, we imediately know why diagonalizing is the thing we eager to do. The solutions are just

.. math::
   P^k(t) = P^k(0) e^{-4F\sin^2(k/2) t} .


.. hint::
   Recall that the elements in the diagonailized :math:`\mathbf A_{\text{diag}}` matrix are just the eigenvalues of :math:`\mathbf A` matrix with corresponding eigenvectors. So in other words, the way to solve this kind of descrete master equations is to solve the eigen problem of :math:`\mathbf A` matrix and then find the eigen modes and finally inverse transform back to :math:`P_m(t)`.






Infinite Chain with Nearest Neighbor Interactions
---------------------------------------------------------------------


We have exactly the same equations as in finite chain. The difference lies in the boundary condition where :math:`N\rightarrow \infty` and

.. math::
   \frac{1}{N}\sum_k \rightarrow \frac{1}{2\pi}\int dk .

.. hint::
   The way to check this result is to check the sum of unit probability.

   .. math::
      \frac{1}{N}\sum_{k=1}^{N} 1 = 1 \Leftrightarrow \frac{1}{2\pi}\int_{-\pi}^{\pi} 1 dk = 1



So the solutions are





.. math::
   P_m(t) &= \frac{1}{2\pi} \int _{-\pi}^{\pi} P^k(0) e^{-2F(1-\cos{k})t} e^{-ikm} dk \\ &=  P^k(0)  e^{-2Ft} \frac{1}{2\pi} \int_{-\pi}^{\pi} e^{2Ft\cos{k}} e^{-ikm} dk \\
   & = P^k(0)  e^{-2Ft} \mathrm{I_m}(2Ft)



.. index:: Modified Bessel Function

.. important::
   **Vocabulary**: :highlit:`Modified Bessel function` is defined as

   .. math::
      \mathrm{I_m} (z) = \frac{1}{2\pi}\int_{-\pi}^{\pi} e^{-ikm} e^{z\cos{k}} dk  .

   Since the argument has imaginary part, this is also called Bessel function of imaginary argument.

   Check out more properties about this function in vocabulary part.

   .. figure:: ../vocabulary/images/besselIFunctions1stKind.png
      :align: center
      :width: 100%

      https://en.wikipedia.org/wiki/File:BesselI_Functions_(1st_Kind,_n%3D0,1,2,3).svg










2D Lattice
-----------


A 2D lattice image is shown below `with image cridet of Jim Belk (public domain) <https://commons.wikimedia.org/wiki/File:Equilateral_Triangle_Lattice.svg>`_.

.. figure:: images/equilateralTriangleLattice.png
   :alt: equilateral Triangle Lattice
   :align: center

   An equilateral triangle lattice



Note that we have translational symmetry in both x and y direction. So the solution is simply the product of solutions to two directioins,

.. math::
   P_m(t) = e^{-2(F_x+F_y)t} \mathrm{I_m}(2F_xt) \mathrm{I_m}(2F_y t)




Continuum Limit
-----------------


Suppose we have a continuum system,

.. math::
   \partial_t P_m &= F(P_{m-1} + P_{m+1}) - 2FP_m \\
   & = F(P_{m+1}-P_m -(P_m-P_{m-1})) \\
   & = F \epsilon^2 \frac{ (P_{m+1}-P_m)/\epsilon -(P_m-P_{m-1})/\epsilon )  }{\epsilon}

We can identify the form of derivatives but RHS becomes zero if :math:`F` is a constant when we take the limit :math:`\epsilon \rightarrow 0`.

It does make sense that :math:`F` actually increases when the distance between two sites becomes smaller. And the way to reconcile the zero problem is to assume that

.. math::
   F = \frac{D}{\epsilon^2} .

Then we have the diffusion equation.

.. math::
   \frac{\partial P(x,t)}{\partial t} = D\frac{\partial^2 P(x,t)}{\partial x^2}





.
