.. _matrix-multiplication-full:

#####################
Matrix Multiplication
#####################

Here is the figure from wikipedia.

.. image:: /figs/mm1.png
   :scale: 50 % 

First of all, note that for two matrices :math:`A` and :math:`B` to be multiplied together :math:`A \times B`, the number of columns in :math:`A` must be equal to the number of rows in :math:`B`. Here we have two columns in :math:`A` (it is a 4 x 2 matrix) and two rows in :math:`B` (a 2 x 3 matrix).

Let's call the product :math:`P` = :math:`AB`.  Then, :math:`P_{ij}`, the entry in row :math:`i`, column :math:`j` of :math:`P`, is obtained from the *dot product* of row :math:`i` of :math:`A` :math:`\cdot` column :math:`j` of :math:`B`.  In this case, there are two terms in each sum.  So

.. math::

    P_{12} = a_{11} \ b_{12} + a_{12} \ b_{22} = \text{row} \ a_1 \cdot \text{col} \ b_2

If :math:`A` is an m x n matrix and :math:`B` is an n x p matrix, the result will be an m x p matrix, and each cofactor will be formed as the sum of n terms.

And in general, 

.. math::

    P_{ij} = \sum_{k=1}^n a_{ik} \ b_{kj}

This is a little risky, but let's write out a :math:`2 \times 2` example where, as an experiment, I've labeled the subscripts going vertically in the second matrix

.. math::

    M1 \times M2 = M1 \ M2

    \begin{bmatrix}
    a_1 & a_2 \\
    b_1 & b_2 
    \end{bmatrix}
    \times
    \begin{bmatrix}
    c_1 & d_1 \\
    c_2 & d_2 
    \end{bmatrix}
    = 
    \begin{bmatrix}
    a_1\ c_1 + a_2 \ c_2 & \ a_1\ d_1 + a_2 \ d_2 \\
    b_1\ c_1 + b_2 \ c_2 & \ b_1\ d_1 + b_2 \ d_2
    \end{bmatrix}

In this arrangement, it's clear that the upper left entry is :math:`\mathbf{a} \cdot \mathbf{c}`, where :math:`\mathbf{a}` is the first row of :math:`M1` and :math:`\mathbf{c}` is the first column of :math:`M2`.

Here are two great pictures that I found on the web, which shows the dot product clearly.

.. image:: /figs/mm2.png
   :scale: 50 % 

.. image:: /figs/mm3.png
   :scale: 50 % 

It can be confusing keeping track of which row and column you are doing, or even whether it should be a row or a column.  That's why I really like the setup shown above in the first figure above (wikipedia), where rather than write :math:`A` and :math:`B` on the same line, :math:`A` is written to the left of the space where :math:`P` will be filled in, and :math:`B` is shown above it.  Then it's clear which row and which column to choose when forming the sums.

==============
Column picture
==============

The second way of looking at this same operation is introduced by thinking of the multiplication of a matrix :math:`A` times a vector :math:`\mathbf{x}` to give a second vector :math:`A \mathbf{x} = \mathbf{b}`

.. math::

    \begin{bmatrix}
    a_{11} & a_{12} \\
    a_{21} & a_{22} 
    \end{bmatrix}
    \times
    \begin{bmatrix}
    x_1 \\
    x_2 
    \end{bmatrix}
    =
    \begin{bmatrix}
    b_1 \\
    b_2 
    \end{bmatrix}

This is the same thing as

.. math::

    x_1
    \begin{bmatrix}
    a_{11} \\
    a_{21} 
    \end{bmatrix}
    +
    x_2
    \begin{bmatrix}
    a_{12} \\
    a_{22} 
    \end{bmatrix}

The result :math:`\mathbf{b}` is a *combination* of the columns of :math:`A`.  Here is a numerical example

.. math::

    \begin{bmatrix}
    1 & 2 \\
    2 & 3 
    \end{bmatrix}
    \times
    \begin{bmatrix}
    1 \\
    2 
    \end{bmatrix}
    =
    \begin{bmatrix}
    5 \\
    8 
    \end{bmatrix}

This is the same thing as

.. math::

    1
    \begin{bmatrix}
    1 \\
    2
    \end{bmatrix}
    +
    2
    \begin{bmatrix}
    2 \\
    3 
    \end{bmatrix}
    =
    \begin{bmatrix}
    5 \\
    8 
    \end{bmatrix}

This extends to a full matrix :math:`B` instead of the single vector :math:`\mathbf{x}`.

.. image:: /figs/mm4.png
   :scale: 50 % 

Each of its columns :math:`C_1`, :math:`C_2`, etc. picks out a combination of the columns of :math:`A`, and those combinations are what end up as the columns of the product.

===========
Row picture
===========

In the same way, if we multiply (on the left) by a row vector---the transpose of a column vector---we see that the product is a combination of the rows of :math:`A`.
:math:`A \times \mathbf{x} = \mathbf{b}`

.. math::

    \begin{bmatrix}
    x_1 & x_2 
    \end{bmatrix}
    \times
    \begin{bmatrix}
    a_{11} & a_{12} \\
    a_{21} & a_{22} 
    \end{bmatrix}
    =
    \begin{bmatrix}
    b_1 & b_2 
    \end{bmatrix}

This is the same thing as

.. math::

    x_1
    \begin{bmatrix}
    a_{11} &  a_{21} 
    \end{bmatrix}
    +
    x_2
    \begin{bmatrix}
    a_{12} & a_{22} 
    \end{bmatrix}
    =
    \begin{bmatrix}
    b_1 & b_2 
    \end{bmatrix}

Here is a numerical example

.. math::

    \begin{bmatrix}
    1 & 2 
    \end{bmatrix}
    \times
    \begin{bmatrix}
    1 & 2 \\
    2 & 3 
    \end{bmatrix}
    =
    \begin{bmatrix}
    5 & 8 
    \end{bmatrix}

This is the same thing as

.. math::

    1
    \begin{bmatrix}
    1 &  2 
    \end{bmatrix}
    +
    2
    \begin{bmatrix}
    2 & 3 
    \end{bmatrix}
    =
    \begin{bmatrix}
    5 & 8 
    \end{bmatrix}

.. image:: /figs/mm5.png
   :scale: 50 % 

======================
One row and one column
======================

.. math::

    \begin{bmatrix}
    a_1 & a_2 & a_3 
    \end{bmatrix}
    \begin{bmatrix}
    b_1 \\ 
    b_2 \\ 
    b_3 
    \end{bmatrix}
    =
    \begin{bmatrix}
    a_1\ b_1 & a_1\ b_2 & a_1\ b_3 \\
    a_2\ b_1 & a_2\ b_2 & a_2\ b_3 \\
    a_3\ b_1 & a_3\ b_2 & a_3\ b_3
    \end{bmatrix}

For each row of :math:`A` we find the correct column of :math:`B` and do this multiplication, generating a whole series of matrices of full size.  Then we add together all the matrices.  Not the most efficient approach.

======
Blocks
======

The fifth and last view of matrix multiplication involves thinking about sub-regions derived from the original matrix but containing an equal number of elements.

.. image:: /figs/mm6.png
   :scale: 50 % 

The upper-left hand corner (2 x 2) would be formed by :math:`A_{11} \times B_{11} + A_{21} \times B_{12}`.

For example, with these two 4 x 4 matrices

.. math::

    \begin{bmatrix}
    a & b & c & d \\
    e & f & g & h \\
    i & j & k & l \\
    m & n & o & p \\
    \end{bmatrix}
    \times
    \begin{bmatrix}
    A & B & C & D \\
    E & F & G & H \\
    I & J & K & L \\
    M & N & O & P \\
    \end{bmatrix}
    =

The entry in row 1, column 1 is computed in the standard "dot product" way as :math:`aA + bE + cI + dM`, but if you broke it up into blocks the upper left-hand corner (a 2 x 2 matrix) would be computed as follows

.. math::

    \begin{bmatrix}
    a & b \\
    e & f \\
    \end{bmatrix}
    \times
    \begin{bmatrix}
    A & B  \\
    E & F \\
    \end{bmatrix}
    +
    \begin{bmatrix}
    c & d \\
    g & h \\
    \end{bmatrix}
    \times
    \begin{bmatrix}
    I & J  \\
    M & N \\
    \end{bmatrix}

    =
    \begin{bmatrix}
    aA + bE & aB + bF  \\
    eA + fE & eB + fF  \\
    \end{bmatrix}
    +
    \begin{bmatrix}
    cI + dM & cJ + dN  \\
    gI + hM & gJ + hN  \\
    \end{bmatrix}


I won't fill in the whole thing, but you can see that the entry in row 1, column 1 is indeed :math:`aA + bE + cI + dM`.