.. _Stokes math24:

#############
Stokes math24
#############

Stokes Theorem is:

.. math::

    \oint_C \mathbf{F} \cdot \mathbf{r} = \iint_R (\nabla \times \mathbf{F}) \cdot \hat{\mathbf{n}} \ dS 

=========
Problem 1
=========

Given

.. math::

    \mathbf{F} = \langle yz,xz,xy \rangle 

Show that the integral

.. math::

    \oint_C yz \ dx + xz \ dy + xy \ dz = 0 

over \emph{any} closed curve :math:`C`.

One way to do this is to guess the potential function for which :math:`\mathbf{F} = \nabla f`.

.. math::

    f(x,y,z) = xyz 

fulfills this criterion.  Since this is true, the curl of :math:`\mathbf{F}` must be zero.  By Stokes theorem, the integral is zero for any closed curve :math:`C`.

A second approach is to actually calculate the curl

.. math::

    \nabla \times \mathbf{F} = \langle R_y - Q_z, P_z - R_x, Q_x - P_y \rangle 

    = \langle x - x, y - y, z - z \rangle = \langle 0, 0, 0 \rangle 

and the dot product with *any* :math:`\hat{\mathbf{n}}` is zero.

=========
Problem 2
=========

Evaluate

.. math::

    \oint_C (y + 2z)dx + (x + 2z)dy + (x + 2y)dz 

where :math:`C` is the intersection of the unit sphere :math:`x^2 + y^2 + z^2 = 1` with the plane :math:`x + 2y + 2z = 0`.  This looks fairly hard at first.  How to parameterize this curve?  But we start by calculating

.. math::

    \nabla \times \mathbf{F} = \langle 2 - 2, 2 - 1, 1 - 1 \rangle = \langle 0, 1, 0 \rangle  

What is :math:`\hat{\mathbf{n}} \ dS`?  Our surface is a part of the plane.  Notice that :math:`(0,0,0)` is a solution of the equation for the plane, so it goes through the origin.  Therefore, the intersection is a circle of radius :math:`1`.  The plane has normal vector :math:`\mathbf{n} = \langle 1,2,2 \rangle` and *unit normal* :math:`\hat{\mathbf{n}} = 1/3 \ \mathbf{n}` so

.. math::

    (\nabla \times \mathbf{F} ) \cdot \hat{\mathbf{n}} = \frac{2}{3} 

Thus we have

.. math::

    \iint_R (\nabla \times \mathbf{F}) \cdot \hat{\mathbf{n}} \ dS =  \iint_R \ \frac{2}{3} \ dS 

which is just two-thirds the area of the unit circle, or :math:`4/3 \pi`.

=========
Problem 3
=========

Evaluate

.. math::

    \oint_C y^3 \ dx - x^3 \ dy + z^3 \ dz 

where :math:`C` is the intersection of the cylinder :math:`x^2 + y^2 = a^2` and the plane :math:`x+ y + z = b`.

The normal vector to the plane is :math:`\mathbf{n} = \langle 1,1,1 \rangle`.  We could certainly parametrize the curve in terms of the angle :math:`\theta` going around the cylinder.  :math:`z` would move from a minimum at :math:`\theta = \pi/4` to a maximum on the other side of the circle.

Let's try the curl first.

.. math::

    \mathbf{F} = \langle y^3, -x^3 , z^3 \rangle 

    \nabla \times \mathbf{F} = \langle R_y - Q_z, P_z - R_x, Q_x - P_y \rangle 

    = \langle 0, 0, -3x^2 - 3y^2 \rangle 

Using the equation of the surface :math:`z = b - x - y`, we get that :math:`f_x =  -1 = f_y` so

.. math::

    \hat{\mathbf{n}} \ dS = \langle -f_x,-f_y,1 \rangle \ dx \ dy 

and

.. math::

    (\nabla \times \mathbf{F} ) \cdot \hat{\mathbf{n}} \ dS = -3x^2 - 3y^2 \ dx \ dy 

    \iint_R (\nabla \times \mathbf{F}) \cdot \hat{\mathbf{n}} \ dS =  \iint_R -3x^2 - 3y^2 \ dx \ dy 

    = -3 \iint_R x^2 + y^2 \ dx \ dy 

We need to integrate this over a circle of radius :math:`a`,

so switch to polar coordinates

.. math::

    = -3 \int \int r^2 \ r \ dr \ d \theta 

    = -3 \  \int \frac{1}{4} a^4 \ d \theta 

    = -\frac{3}{2} \pi a^4 
