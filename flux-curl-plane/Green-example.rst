.. _Green ex:

########
Green ex
########

State the theorem:

.. math::

    \oint_C \mathbf{F} \cdot \mathbf{r} = \iint_R \nabla \times \mathbf{F} \ dA 

    \int_C M \ dx + N \ dy = \iint_R (N_x - M_y) \ dx \ dy 

To start with, if :math:`\mathbf{F}` is the gradient of some function, we call such a function the potential, and the integral of the work over a closed path is just zero.

.. math::

    \mathbf{F} = \ <y,x> 

    f = xy 

Suppose we take the line integral of :math:`\mathbf{F}\cdot \mathbf{r}`  over the unit square :math:`(0,0)` to :math:`(0,1)`, etc.

.. math::

    \oint_C y \ dx + x \ dy = 

I get :math:`0 + 1 -1 + 0 = 0`.

A sign change can make all the difference.

.. math::

    \mathbf{F} = \ <-y,x> 

    N_x - M_y = 1 - -1 = 2 \ne 0 

A common field with zero curl in 3D is

.. math::

    \mathbf{F} = \ <yz,xz,xy> 

    \nabla \times \mathbf{F} = \ <R_y-Q_z,P_z-R_x,Q_x-P_y> 

    = x - x, y - y, z - z > \ = \mathbf{0} 

======
Auroux
======

Suppose

.. math::

    \mathbf{F} = \ <ye^{-x},\frac{1}{2}x^2 - e^{-x}> 

And suppose further that the region is the unit disk centered at :math:`(2,0)`  The line integral does not look like fun, and the region is no help, but

.. math::

    N_x - M_y = x + e^{-x} - e^{-x} = x 

So the integral of the curl is just

.. math::

    \iint_R x \ dA 

which is :math:`\overline{x}` on this disk, which is just equal to :math:`2` by symmetry.

====
Paul
====

Given

.. math::

    \mathbf{F} = \ <xy,x^2y^3> 

The curl is

.. math::

    N_x - M_y = 2xy^3 - x 

If the region is the triangle :math:`(0,0) \rightarrow (1,0) \rightarrow (1,2) \rightarrow (0,0)` then

.. math::

    \int_0^1 \int_0^{2x} 2xy^3 - x \ dy \ dx 

inner

.. math::

    = \frac{1}{2}xy^4 - xy \ \bigg |_0^{2x} = 8x^5 - 2x^2 

outer

.. math::

    \int_0^1 8x^5 - 2x^2 \ dx = \frac{8}{6}x^6 - \frac{2}{3}x^3 \bigg |_0^1 
    
    = \frac{8}{6} - \frac{2}{3} = \frac{2}{3} 

Try the line integral to check it.

=======
Ellipse
=======

Of course, my favorite example is the area of the ellipse.  Suppose :math:`N_x - M_y = 1`.  Then the curl integral is the area of the region.  If the components of :math:`\mathbf{F}` are :math:`N = x/2` and :math:`M=-y/2`, this condition holds.  Parametrize the ellipse.

.. math::

    x = a \cos \theta 

    y = b \sin \theta 

So, for the left hand side we have

.. math::

    \int_C M \ dx + N \ dy = \int_C -\frac{1}{2}y \ dx + \frac{1}{2}x \ dy 

    = \int_0^{2\pi} (-\frac{1}{2})(b \sin \theta) \ (-a \sin \theta) \ d \theta \ + (\frac{1}{2})(a \cos \theta) \ (b \cos \theta) \ d\theta 

    = ab \int_0^{2\pi} \frac{1}{2} + \frac{1}{2} \ d \theta = 2 \pi a b
