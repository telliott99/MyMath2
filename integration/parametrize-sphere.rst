.. _parametrize-sphere:

######################
Parametrize the sphere
######################

A sphere centered at the origin is defined as the set of points :math:`x,y,z` at a distance :math:`\rho` away from :math:`(0,0,0)`, leading to the equation :math:`x^2 + y^2 + z^2 = \rho^2`.  We are looking for a "parametrization" or relationship between :math:`x,y,z` coordinates and spherical coordinates in terms of one radial and two angular variables.  These are usually called :math:`\rho, \theta`, and :math:`\phi`.

.. image:: /figs/sphcoord.png
   :scale: 50 %

If we think of the vector :math:`<x,y,z>` to a point on the sphere.  The radius of the sphere is :math:`\rho`.   The projection of :math:`\rho` in the :math:`xy`-plane is :math:`r`, and :math:`\theta` is the angle that :math:`r`, the projection of :math:`\rho` makes going ccw from the positive :math:`x`-axis and ranges from :math:`0 \le \theta \le 2\pi`.  

:math:`\phi` is the "polar" angle that the same vector makes with the positive :math:`z`-axis and ranges from :math:`0 \le \phi \le \pi`.  (Note:  unfortunately, the mathematicians and the physicists did not agree on what to call these angles).

.. math::

    r = \rho \cos (\frac{\pi}{2} - \phi) = \rho \sin \phi 

    x = r \cos \theta = \rho \sin \phi \cos \theta 

    y = r \sin \theta = \rho \sin \phi \sin \theta 

    z = \rho \sin (\frac{\pi}{2} - \phi) = \rho \cos \phi 

Now, above we said that :math:`x^2 + y^2 + z^2 = \rho^2`, as if it were obvious.  For a circle, we know that :math:`x^2 + y^2 = r^2` by using the Pythagorean theorem.  To get the same thing for a sphere, we use it in 3-dimensions, i.e. :math:`x^2 + y^2 = r^2` and then :math:`r^2 + z^2 = \rho^2`.

Let's just check that our parametrization (some people say parameterization, but not many) works:

.. math::

    x^2 + y^2 + z^2  

    = \rho^2 \sin^2 \phi \cos^2 \theta + \rho^2 \sin^2 \phi \sin^2 \theta +  \rho^2 \cos^2 \phi 

    = \rho^2 ( \sin^2 \phi \cos^2 \theta +  \sin^2 \phi \sin^2 \theta +  \cos^2 \phi ) 

    = \rho^2 ( \sin^2 \phi +  \cos^2 \phi) 

    = \rho^2

Looks good.

For what comes below we will unfortunately need all 9 partial derivatives.

.. math::

    x_{\rho} =  \sin \phi \cos \theta 

    x_{\phi} = \rho \cos \phi \cos \theta 

    x_{\theta} = - \rho \sin \phi \sin \theta 

    y_{\rho} = \sin \phi \sin \theta 

    y_{\phi} = \rho \cos \phi \sin \theta 

    y_{\theta} = \rho \sin \phi \cos \theta 

    z_{\rho} = \cos \phi 

    z_{\phi} = -\rho \sin \phi 

    z_{\theta} = 0 

When we change variables from :math:`x,y,z` to :math:`\rho,\theta,\phi`, the scaling factor for the volume element :math:`dV` is the Jacobian:

.. math::

    dx \ dy \ dz = J \ d\rho \ d\phi \ d\theta 

where :math:`J` is the absolute value of the determinant of this matrix:

.. math::

    J =
    \begin{vmatrix}
    x_{\rho} & x_{\phi} & x_{\theta} \\
    y_{\rho} & y_{\phi} & y_{\theta} \\
    z_{\rho} & z_{\phi} & z_{\theta}
    \end{vmatrix}

If you notice, :math:`z_{\theta} = 0`, which suggests we compute using either the third row or the third column.

.. math::

    J = x_{\theta}(y_{\rho}z_{\phi} - y_{\phi}z_{\rho}) - y_{\theta}(x_{\rho}z_{\phi}-x_{\phi}z_{\rho}) 

Now we just plug in from our list above.  The first term is

.. math::

    - \rho \sin \phi \sin \theta \ [ \ \sin \phi \sin \theta \ (-\rho \sin \phi) - \rho \cos \phi \ \sin \theta \cos \phi \ ]

    - \rho \sin \phi \sin \theta \ [ \ -\rho \sin^2 \phi \sin \theta - \rho \cos^2 \phi \ \sin \theta \ ]

    = - \rho \sin \phi \sin \theta \ (-\rho \ \sin \theta) 

    = \rho^2 \sin \phi \sin^2 \theta 

while the second term is

.. math::

    - \rho \sin \phi \cos \theta \ (\sin \phi \cos \theta \ (-\rho \sin \phi) - \rho \cos \phi \cos \theta \  \cos \phi) 

    - \rho \sin \phi \cos \theta \ [ \ - \rho \sin^2 \phi \cos \theta - \rho \cos^2 \phi \cos \theta \ ]

    = -\rho \sin \phi \cos \theta \ (- \rho \cos \theta) 

    = \rho^2 \sin \phi \cos^2 \theta 

Putting them together

.. math::

    J = \rho^2 \ \sin \phi (\sin^2 \theta + \cos^2 \theta) = \rho^2 \ \sin \phi 

So our volume element is

.. math::

    dV = dx \ dy \ dz
    
    = J \ d \rho \ d \phi \ d \theta
    
    = \rho^2 \sin \phi \ d \rho \ d \phi \ d \theta 

.. image:: /figs/sphere_dV.png
   :scale: 50 %

Notice that the top of the box is :math:`\rho \sin \phi \ d\theta = r d\theta`, varying with :math:`\phi`, while the sides do not depend on the polar angle but are just :math:`\rho \ d\phi`.

We might as well check this

.. math::

    V = \iiint dV 
    
    = \int_{\theta = 0}^{2\pi} \ \int_{\phi=0}^{\pi} \ \int_{\rho=0}^{a} \rho^2 \sin \phi \ d \rho \ d \phi \ d \theta 

    =  \int_{\theta = 0}^{2\pi} \ \int_{\phi=0}^{\pi}  \frac{1}{3} a^3 \sin \phi \ d \phi \ d \theta 

    =  \int_{\theta = 0}^{2\pi} \ \frac{1}{3} a^3 (-\cos \phi) \bigg |_{0}^{\pi}   \ d \theta 

    =  \int_{\theta = 0}^{2\pi} \ \frac{1}{3} a^3 (2)   \ d \theta 

    =  \frac{1}{3} a^3 (2)(2 \pi) 

    =  \frac{4}{3} \pi a^3 

which seems to be correct.

=======
Surface
=======

How about parametrizing the surface of the sphere?  In this case :math:`\rho` is a constant, and we will have only two variables, similar to longitude and latitude.

The standard parametrization of the (unit) sphere is

.. math::

    \mathbf{r}(\phi, \theta) = \langle \sin \phi \cos \theta, \sin \phi \sin \theta, \cos \phi \rangle

with partial derivatives:

.. math::

    \mathbf{r}_{\phi} = \langle \cos \phi \cos \theta, \cos \phi \sin \theta, -\sin \phi \rangle 

    \mathbf{r}_{\theta} = \langle -\sin \phi \sin \theta, \sin \phi \cos \theta, 0 \rangle

The cross-product is

.. math::

    \mathbf{r}_{\phi} \times \mathbf{r}_{\theta} =  

    < \sin^2 \phi \cos \theta, \sin^2 \phi \sin \theta, \sin \phi \cos \phi> 

If we want

.. math::

    |\mathbf{r}_{\phi} \times \mathbf{r}_{\theta} | = \sqrt{\sin^4 \phi \cos^2 \theta + \sin^4 \phi \sin^2 \theta + \sin^2 \phi \cos^2 \phi} 

    = \sqrt{\sin^4 \phi + \sin^2 \phi \cos^2 \phi} 

    = \sqrt{\sin^2 \phi} 

    = \sin \phi 

In my writeup of the first part of Schey's book (chapter 2), we saw that the normal vector to a surface is

.. math::

    \hat{\mathbf{n}} = \frac{\mathbf{u} \times \mathbf{v}}{| \mathbf{u} \times \mathbf{v} |} 

Dividing the cross-product above by its absolute value we get

.. math::

    \frac{\mathbf{r}_{\phi} \times \mathbf{r}_{\theta} }{ | \mathbf{r}_{\phi} \times \mathbf{r}_{\theta} | } 

    = \frac{1}{\sin \phi} \langle -\sin^2 \phi \cos \theta, \sin^2 \phi \sin \theta, \sin \phi \cos \phi \rangle

    =  \langle -\sin \phi \cos \theta, \sin \phi \sin \theta, \cos \phi \rangle

    = \langle x,y,z \rangle 
