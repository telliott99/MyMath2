.. _vectors-planes:

##################
Vectors and Planes
##################

Let's make the move into 3D (officially :math:`\mathbb{R}^3`).  Now our vectors have three components.  The vector

.. math::

    \mathbf{v} = \  \langle v_1, v_2, v_3 \rangle

has a length that can be computed (by two sequential applications of the Pythagorean Theorem) as

.. math::

    |\mathbf{v}| = \sqrt{v_1^2 + v_2^2 + v_3^2}

For example 

.. math::

    \mathbf{v} =  \ \langle -2,1,0\rangle
    
    |v| = \sqrt{(-4)^2 + 1^2} = \sqrt{5}

The dot product of :math:`\mathbf{u}` with :math:`\mathbf{v}` is just

.. math::

    u \cdot v = u_1v_1 + u_2v_2 + u_3v_3

A really nice thing happens here.  The formula

.. math::

    \cos \theta \ = \frac{\mathbf{u} \cdot \mathbf{v}}{ |\mathbf{u}| |\mathbf{v}| }

is still valid.  So the dot product can find the angle between vectors in three-dimensional space (or even higher).

Let's take a moment to understand why this is the case.  Although the first formula for the dot product

.. math::

    \mathbf{u} \cdot \mathbf{v} = \sum_i a_i b_i

has terms that will depend on *which* coordinate system has been chosen, the formula :math:`|\mathbf{u}| |\mathbf{v}| \cos \theta` does not contain any such references.  So somehow the components of the vectors in a new coordinate system are constrained to make this statement still true:

.. math::

    \mathbf{u} \cdot \mathbf{v} = \sum_i a_i b_i

We can choose a new coordinate system, the plane containing :math:`\mathbf{u}` and :math:`\mathbf{v}`.  The angle between the two vectors can be computed there in the usual way.  And that angle is independent of the coordinate system

Another nice property that follows is that :math:`\mathbf{u} \perp \mathbf{v} \iff \mathbf{u} \cdot \mathbf{v} = 0`.   If and only if :math:`\mathbf{u} \perp \mathbf{v}`, then :math:`\mathbf{u} \cdot \mathbf{v}` = 0.

Here is an application.  Suppose I have a vector :math:`\mathbf{u} = \ \langle 1,2,0 \rangle`, then I can easily find two vectors that are perpendicular (out of many)

.. math::

    \mathbf{u} = \ \langle 1,2,0 \rangle

    \mathbf{v} =  \ \langle -2,1,0 \rangle

    \mathbf{u} \cdot \mathbf{v} = 0

    \mathbf{w} = \ \langle 0,0,5 \rangle

    \mathbf{u} \cdot \mathbf{w} = 0

Now, :math:`\mathbf{v}` and :math:`\mathbf{w}` are not parallel, because if they were parallel then there would have to be a constant :math:`t` such that

.. math::

    t \ \mathbf{v} = \mathbf{w}

So their linear combinations :math:`c \ \mathbf{v} + d \ \mathbf{u}`, where :math:`c` and :math:`d` are scalar constants, form a plane.  In fact, you may notice that :math:`\mathbf{v} \cdot \mathbf{w} = 0` so,  :math:`\mathbf{v} \perp \mathbf{w}`, and we now see that we have three perpendicular vectors, also referred to as orthogonal vectors.

We often talk of the unit vectors, vectors with unit magnitude in the direction of the :math:`x`-axis, or the :math:`y`-axis, or the :math:`z`-axis.  These are usually called :math:`\mathbf{\hat{i}}` ("i hat"), etc.

.. math::

    \mathbf{\hat{i}} =  \ \langle 1,0,0 \rangle

    \mathbf{\hat{j}} =  \ \langle 0,1,0 \rangle

    \mathbf{\hat{k}} = \  \langle 0,0,1 \rangle

Take a second to confirm that these three vectors are perpendicular, by computing their dot products.

If we wanted to choose a new *basis* for this vector space, we could choose :math:`\mathbf{u}, \mathbf{v}`, and :math:`\mathbf{w}`.  All that would be required would be to make them unit vectors, dividing each one by its length.  Then the components of any vector could be determined with respect to the new coordinate system by computing the dot products with the unit vectors :math:`\mathbf{\hat{u}}`, :math:`\mathbf{\hat{v}}` and :math:`\mathbf{\hat{w}}`.

======
Planes
======

The equation of a plane has the form:

.. math::

    ax + by + cz = d
    
where :math:`x,y,z` specify the coordinates of a point in space, and :math:`a,b,c,d` are constants.  For example, given any :math:`x` and :math:`y`, we can compute

.. math::

    z = \frac{d - ax - by}{c}

There is another way to look at the equation of a plane, using vectors, that yields insight into this equation.

Pick three points that are not colinear:  :math:`P`, :math:`Q`, and :math:`R`.  These three points all lie in a single, unique plane.

Form the vectors joining any one point to the other two, for example:  :math:`PQ` and :math:`PR` (by subtracting the coordinates).  Now linear algebra tells us that any point in the plane can be formed from a unique *linear combination* of these two vectors.

.. image:: /figs/linear-combos2.png
   :scale: 50 % 

=============
Normal vector
=============

Suppose we have :math:`P = (1,0,0)`, :math:`Q = (0,1,0)`, and :math:`R = (0,0,1)`.  Then the two vectors could be :math:`PQ` and :math:`PR`:

.. math::

    \mathbf{u} = PQ = Q-P = (0,1,0) - (1,0,0) = \langle -1, 1, 0 \rangle
    
    \mathbf{v} = PR = R-P = (0,0,1) - (1,0,0) = \langle -1, 0, 1 \rangle

As we said, any point in the plane can be described as a (unique) linear combination of these vectors.

But rather than get into that, let's explore the fact that this plane can be described in another way:  it is the set of all points that are perpendicular to the *normal* vector.  We can find the normal vector, given two vectors in the plane, by using the cross-product.

.. math::

    \mathbf{N} = \mathbf{u} \times \mathbf{v}
    
To compute the cross product, set up the matrix and read off the terms.  

.. math::

    \begin{bmatrix} 
      \mathbf{\hat{i}}  &  \mathbf{\hat{j}}  &  \mathbf{\hat{k}} \\ 
      -1  &  1 & 0 \\
      -1  &  0 & 1
    \end{bmatrix}

I get:

.. math::

    \mathbf{N} = \langle 1, 1, 1 \rangle

This normal vector does not describe one single plane but rather a family of planes that are parallel to one another.  To specify a unique plane that contains these three points, we also need a fixed point in the plane.  Let's take :math:`P = (1,0,0)`.  

All the points in the plane have coordinates :math:`x,y,z` *such that*, the vector from :math:`P` to :math:`(x,y,z)` is perpendicular to :math:`\mathbf{N}`.  That is, the dot product with :math:`\mathbf{N}` must be equal to zero.  Writing this out, the general vector in the plane is:

.. math::

    \mathbf{w} = \langle x - 1, y, z \rangle

and the zero dot product requires that

.. math::
    
    \mathbf{N} \cdot \mathbf{w} = 0
    
    \langle 1, 1, 1 \rangle \ \cdot \ \langle x - 1, y, z \rangle = 0
    
    (x-1) + y + z = 0
    
    x + y + z = 1

We can easily verify that each of the points :math:`P = (1,0,0)`, :math:`Q = (0,1,0)`, and :math:`R = (0,0,1)` does satisfy this equation.  And we can also verify that the two vectors

.. math::

    \mathbf{u} = PQ = \langle 1, -1, 0 \rangle
    
    \mathbf{v} = PR = \langle 1, 0, -1 \rangle

each give a dot product of zero with :math:`\mathbf{N}`.

The general formulation is that given a point :math:`P = (x_0,y_0,z_0)` and the normal vector :math:`\mathbf{N} = \langle a, b, c \rangle`, the equation of the plane is:

.. math::

    \mathbf{N} \cdot \mathbf{w} = 0
    
    0 = \langle a, b, c \rangle \ \cdot \ \langle x - x_0, y - y_0 , z - z_0 \rangle

    0 = ax + by + cz - ax_0 - by_0 - cz_0
    
    ax + by + cz = ax_0 + by_0 + cz_0 = d

What is the distance from the origin to the plane at the closest point?  We can solve this from the geometry, but a quicker way is to take a vector from the origin to one of the known points and measure its projection *onto* the normal vector.  First, we turn :math:`\mathbf{N}` into a unit vector:

.. math::

    \mathbf{\hat{n}} = \frac{\mathbf{N}}{|\mathbf{N}|} 
    
    = \frac{1}{\sqrt{3}} \ \langle 1, 1, 1 \rangle

So

.. math::

    \langle 1, 0, 0 \rangle \ \cdot \frac{1}{\sqrt{3}} \ \langle 1, 1, 1 \rangle
    
    = \frac{1}{\sqrt{3}}

Let's check, using the geometry.  Well, as Lockhart says in his book *Measurement*, **do not ignore symmetry**.  We have no reason to prefer one of :math:`x,y` or :math:`z` over the others, therefore I guess that :math:`x=y=z` so from the equation of the plane we have that :math:`3x = 1` and the point of closest approach is :math:`(1/3,1/3,1/3)`.  The squared length of the vector from the origin to this point is

.. math::

    3 \frac{1}{3^2} = \frac{1}{3}

so its length is :math:`1/\sqrt{3}`, which matches what we had.  And of course there is a constant :math:`t` such that :math:`t \ \mathbf{N}` is equal to this vector.

Actually working out the arithmetic:  again from the symmetry the distance to each of our points is the same so

.. math::

    (x-1)^2 + y^2 + z^2 = x^2 + (y-1)^2 + z^2 = x^2 + y^2 + (z-1)^2
    
From the first equality we obtain

.. math::

    x^2 -2x + 1 + y^2 + z^2 = x^2 + y^2 -2y + 1 + z^2

which gives :math:`x=y`, and so on.

The significance of the constant :math:`d` being equal to :math:`1` is partly that this gives the points of intersection of the plane with the coordinate axes.  Since :math:`a = b = c = 1`, :math:`d=1` gives our points as :math:`P = (1,0,0)`, :math:`Q = (0,1,0)`, and :math:`R = (0,0,1)`.

But there is another thing.  Recall that we have the equation:

.. math::

    x + y + z = 1
    
    \mathbf{N} = \langle 1,1,1 \rangle

Notice that if we normalize :math:`\mathbf{N}`:

.. math::

    \mathbf{\hat{n}} = \frac{1}{\sqrt{3}} \langle 1,1,1 \rangle

Then the equation of the plane becomes

.. math::

    \frac{x}{\sqrt{3}} + \frac{y}{\sqrt{3}} + \frac{z}{\sqrt{3}} = \frac{1}{\sqrt{3}}

It's the same plane.

If the equation of the plane is written with a *unit* normal vector, then :math:`d` is the distance from the origin to the plane.
