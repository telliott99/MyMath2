.. _matrix-inverse:

##############
Matrix inverse
##############

Having the inverse of a matrix can be quite handy.  For example, if we have a system of equations represented as a matrix product:

.. math::

    A \mathbf{x} = \mathbf{b}

where we need to find :math:`x_1, x_2 \dots x_n` to solve all of these equations

.. math::

    a_{11} x_1 + a_{12} x_2 + a_{13} x_3 \dots a_{1n} x_n = b_1
    
    a_{21} x_1 + a_{22} x_2 + a_{23} x_3 \dots a_{2n} x_n = b_2

    \dots
    
    a_{m1} x_1 + a_{m2} x_2 + a_{m3} x_3 \dots a_{mn} x_n = b_n

The way we actually solve this thing is to find A^{-1} so that we can do

.. math::

    A^{-1} A \mathbf{x} = A^{-1} \mathbf{b}
    
    \mathbf{x} = A^{-1} \mathbf{b}

So how to do this?  The general method is more than we need here, what we really need is a way to do the for :math:`2 \times 2` and :math:`3 \times 3` matrices, and there are shortcuts for these.

For two by two we compute the determinant:

.. math::

    A = 
    \begin{bmatrix}
    a & b \\
    c & d 
    \end{bmatrix}

    |A| = ad - bc
    
    A^{-1} = \frac{1}{ad - bc} 
    \begin{bmatrix}
    d & -b \\
    -c & a 
    \end{bmatrix}

Let's do an example!

.. math::

    A = 
    \begin{bmatrix}
    \cos \theta & \sin \theta \\
    -\sin \theta & \cos \theta
    \end{bmatrix}

    A^{-1} = \frac{1}{cos^2 \theta + \sin^2 \theta}
    \begin{bmatrix}
    \cos \theta & -\sin \theta \\
    \sin \theta & \cos \theta
    \end{bmatrix}

Maybe we should do another one.  How about

.. math::

    A = 
    \begin{bmatrix}
    2 & 1 \\
    3 & 3
    \end{bmatrix}

    A^{-1} = \frac{1}{3}
    \begin{bmatrix}
    3 & -1 \\
    -3 & 2
    \end{bmatrix}
    
which is easily checked by multiplying out.

.. math::

    A A^{-1} = \frac{1}{3}
    \begin{bmatrix}
    2 \cdot 3 + 1 \cdot -3 & 2 \cdot -1 + 1 \cdot 2 \\
    3 \cdot 3 + 3 \cdot -3 & 3 \cdot -1 + 3 \cdot 2
    \end{bmatrix}
    = \frac{1}{3}
    \begin{bmatrix}
    1 & 0 \\
    0 & 1
    \end{bmatrix}
    = I

as required.

Auroux shows a trick for :math:`3 \times 3`:

- Compute minors
- Change cofactors
- Transpose
- Divide by the determinant
- Check

Suppose we look at 

.. math::

    A = 
    \begin{bmatrix}
    2 & 3 & 3 \\
    2 & 4 & 5 \\
    1 & 1 & 2
    \end{bmatrix}

We compute the minors as the determinants of the matrix obtained by removing the row and column in question.  For example the first entry at the upper left is :math:`4 \cdot 2 - 1 \cdot 5 = 3`.  I get

.. math::

    \begin{bmatrix}
    3 & -1 & -2 \\
    3 & 1 & -1 \\
    3 & 4 & 2
    \end{bmatrix}

Step two is to change the cofactors using the checkerboard pattern:

.. math::

    \begin{bmatrix}
    + & - & + \\
    - & + & - \\
    + & - & +
    \end{bmatrix}
    
    \begin{bmatrix}
    3 & -1 & -2 \\
    3 & 1 & -1 \\
    3 & 4 & 2
    \end{bmatrix}
    \Rightarrow
    \begin{bmatrix}
    3 & 1 & -2 \\
    -3 & 1 & 1 \\
    3 & -4 & 2
    \end{bmatrix}

Step three is to find the transpose:

.. math::

    \begin{bmatrix}
    3 & -3 & 3 \\
    1 & 1 & -4 \\
    -2 & 1 & 2
    \end{bmatrix}

Step four is to divide by the determinant of the original vector :math:`A = 2 \cdot  3 - 3 \cdot -1 + 3 \cdot -2 = 3`.

So

.. math::

    A^{-1} =
    \begin{bmatrix}
    1 & -1 & 1 \\
    1/3 & 1/3 & -4/3 \\
    -2/3 & 1/3 & 2/3
    \end{bmatrix}

which is easily checked by multiplying out.  The result is:

.. math::

    I =
    \begin{bmatrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1
    \end{bmatrix}

If these tricks don't appeal, or if you are in higher dimension, use Gauss-Jordan elimination to find the series of matrices that multiplies :math:`A` to obtain :math:`I`.  The same matrix multiplied by :math:`I` will give  :math:`A^{-1}`.  Really.

.. math::

    P_1 P_2 P_3 A = I
    
    P_1 P_2 P_3 I = A^{-1}

