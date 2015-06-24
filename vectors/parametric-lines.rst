.. _parametric-lines:

################
Parametric Lines
################

Lines are a bit more complicated in :math:`\mathbb{R^3}` because they are formed from the intersection of two planes.  However, they can also be written in parametric form, given two points on the line:

.. math::

    Q_0 = (-1,2,2)
    
    Q_1 = (1,3,-1)
    
    \mathbf{v} = Q_0 Q_1

then

.. math::
    
    Q_t = Q_0 + t (\mathbf{v})
    
    = (-1,2,2) + t(2,1,-3)

or a bit more fancy:

.. math::

    L = t \mathbf{v} \ \ \forall \ t \in \mathbb{R}
    
    L(t=0) = \langle -1, 2, 2 \rangle

We can also write this as three separate equations:

.. math::

    x = -1 + 2t
    
    y = 2 + t
    
    z = 2 - 3t
    
    t = \frac{x + 1}{2} = y - 2 = -\frac{z - 2}{3}
    
+++++++
Example
+++++++

Suppose we wish to determine the intersection of the line given above with a plane:

.. math::

    x + 2y + 4z = 7

Are :math:`Q_0` and :math:`Q_1` on the same side of the plane, or opposite sides, or maybe the line is in the plane.

We write:

.. math::

    \mathbf{N} = \langle, 1,2,4 \rangle
    
    \mathbf{N} \cdot \mathbf{v} = \langle, 1,2,4 \rangle \cdot \langle 2,1,-3 \rangle
    
    = 2 + 2 - 12 \ne 0

so the line is not in the plane.

Also, the line is not a multiple of :math:`\mathbf{N}`, so it's not parallel to :math:`\mathbf{N}`.

Neither point :math:`Q_0` not :math:`Q_1` solves the equation:

.. math::

    Q_0 = (-1,2,2)
    
    Q_1 = (1,3,-1)
    
    x + 2y + 4z = 7

    Q_0:  -1 + 4 + 8 = 11
    
    Q_1:  1 + 6 - 4 = 3
    
In fact, there is a suspicious symmetry here.  This suggests the points are on opposite sides of the plane.

A good way to solve this is to find the value of :math:`t` that solves the equation of the plane

.. math::

    x = -1 + 2t
    
    y = 2 + t
    
    z = 2 - 3t
    
.. math::

    x + 2y + 4z = 7
    
    2t - 1 + 2t + 4 - 12t + 8 = 7
    
    -8t + 11 = 7
    
    t = \frac{1}{2}

So :math:`(0,3/2,1/2)` *is* on the line, and it solves the equation of the plane.

Notice that the coefficients of :math:`t`  (:math:`2,2,-12`) in the equations for :math:`x,y,z` in the plane, are the terms of the dot product we computed above:

.. math::

    \mathbf{N} \cdot \mathbf{v} = \langle, 1,2,4 \rangle \cdot \langle 2,1,-3 \rangle
    
    = 2 + 2 - 12 \ne 0




