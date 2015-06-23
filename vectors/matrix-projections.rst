.. _matrix-projections:

##################
Matrix Projections
##################

The more general formula used in :math:`\mathbb{R}^3` and higher is 

.. math::

    P = A(A^T A)^{-1} A^T

To compute the projection of a vector :math:`\mathbf{b}` onto a plane which is defined by the columns of :math:`A`, we just compute:

.. math::

    \mathbf{p} = P \mathbf{b}
    
It seems like quite a bit, but if you look at the vector version from :ref:`before <projections>`

.. math::

    \frac{\mathbf{a} \cdot \mathbf{b}}{\mathbf{a} \cdot \mathbf{a} }  \ \mathbf{a}
    
you may see some parallels.  :math:`\mathbf{a} \cdot \mathbf{a}` is the analog of :math:`A^T A`, and since there is no matrix division we multiply by its inverse.  The trick is to remember that all this occurs in a certain order, first :math:`A`, then the inverse :math:`(A^T A)^{-1}`, and then :math:`A^T`.

To check this out, we need two vectors in one of the family of planes defined by the normal vector :math:`\mathbf{n} = \langle 1, 1, 1 \rangle`.  We can make these up by inspection.  Set one of :math:`x`, :math:`y` or :math:`z` to zero, one of the others to be :math:`1`, and then compute the third value.  We will use :math:`\langle 1, -1, 0 \rangle` and :math:`\langle 1, 0, -1 \rangle`.  We set up

.. math::

    A =
    \begin{bmatrix}
    \ \ 1 & \ \ 1 \\
    -1 & \ \ 0 \\
    \ \ 0 & -1 
    \end{bmatrix}

Rather than grind out a calculation (I always seem to make an error), I used 

http://www.sympy.org/en/index.html

.. math::

    A (A^T A)^{-1} A^T = 
    \frac{1}{3} \
    \begin{bmatrix}
    \ \ 2 & -1 & -1 \\
    -1 & \ \ 2 & -1 \\
    -1 & -1 & \ \ 2
    \end{bmatrix}

Notice that :math:`P^T = P`.  

Also, note that :math:`PP = P`.  **Once a vector has been projected into a plane, it will not change upon a second projection**.

We have :math:`\mathbf{b} = \langle 1, 2, 3 \rangle` and we are to compute

.. math::

    P \mathbf{b} =  
    \frac{1}{3} \
    \begin{bmatrix}
    -3 \\
    \ \ 0 \\
    \ \ 3
    \end{bmatrix}
    =
    \begin{bmatrix}
    -1 \\
    \ \ 0 \\
    \ \ 1
    \end{bmatrix}

=============
3D derivation
=============

For a plane with *basis* vectors :math:`a_1` and :math:`a_2` the projection is some combination of the two vectors.

.. math::

    p = \hat{x_1} a_1 + \hat{x_2} a_2 = A \hat{x}

We know that :math:`e=b-p=b-A\hat{x}` is :math:`\perp` to the plane.

.. math::

    a_1^T(b-A \hat{x}) = 0 =  a_2^T(b-A \hat{x})
    
Put them into a matrix

.. math::

    \begin{bmatrix} 
      a_1^T    \\ 
      a_2^T    \\
    \end{bmatrix}
    (b-A\hat{x}) =
    \begin{bmatrix} 
      0    \\ 
      0    \\
    \end{bmatrix}

    A^T(b-A\ \hat{x}) = 0

    A^T A\ \hat{x} = A^Tb

    \hat{x} = (A^T A)^{-1}A^Tb
    
The fundamental equation is then

.. math::

    p = A \hat{x} = A(A^T A)^{-1}A^Tb
    
Compare with the one-dimensional case

.. math::

    a\frac{a^T b}{a^Ta}
    
It's basically the same, as long as you remember that dividing is like multiplying by the inverse, and that it has to happen in a particular order.  (In this notation, we are using matrices, so the multiplication is understood to be a dot product).

+++++++
Example
+++++++

Suppose we have a line

.. math::

    l : \{p_0 + t \mathbf{v}, t \in \mathbb{R} \}
    
How do we find the distance to the point on the line that is closest to the origin?  

First, we recognize that the vector from the origin to that point of closest approach is perpendicular or orthogonal to the line.  So if we first find a vector to *any* point on the line, and then find the projection :math:`\mathbf{p}` of that vector on the line, we can find the other part of it by subtraction, which is what we called :math:`\mathbf{e}` above.

Let's call :math:`\mathbf{r}` the vector from the origin to :math:`p_0`:

The projection is 

.. math::

    \mathbf{p} = \frac{\mathbf{v} \cdot \mathbf{r}}{\mathbf{v} \cdot \mathbf{v}} \mathbf{v}

and the vector of closest approach is

.. math::

    \mathbf{r} - \mathbf{p} = \mathbf{r} - \frac{\mathbf{v} \cdot \mathbf{r}}{\mathbf{v} \cdot \mathbf{v}} \mathbf{v}

The distance to the line is just the length of this vector.  It is clear that the point so defined is actually on the line, because we have the equation of the line as given, with the substitution

.. math::

    t = -\frac{\mathbf{v} \cdot \mathbf{r}}{\mathbf{v} \cdot \mathbf{v}}

The distance is

.. math::

    \text{distance} = \| \mathbf{r} - \mathbf{p} \|

We can modify this approach to use any point :math:`p_1`, rather than just the origin.  We simply set

.. math::

    \mathbf{r} = p_0 - p_1
    
and then proceed as before.

+++++++
Example
+++++++

Suppose we have a plane, and we want to know the distance between the origin and the plane.

First, we recognize that this is again a problem of closest approach.  We already know a vector orthogonal to the plane, :math:`\mathbf{n}`.  We need a point on the plane, for example from the definition

.. math::

    P :  \mathbf{n} \cdot [(x,y,z) - p_0]
    
or perhaps by solving

.. math::

    ax + by + cz = d
    
for :math:`z` with :math:`x=0, y=0`.  Given some :math:`p_0` we find the dot product of the corresponding vector and a unit vector in the direction of :math:`\mathbf{n}`:

.. math::

    \hat{\mathbf{n}} = \frac{\mathbf{n}}{\| \mathbf{n} \| }

    \text{distance} = \mathbf{r} \cdot  \hat{\mathbf{n}}

And as before, we can modify this for use with any point, rather than just the origin, by changing the definition of :math:`\mathbf{r}`.