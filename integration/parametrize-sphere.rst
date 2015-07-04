.. _parametrize-sphere:

######################
Parametrize the sphere
######################

A sphere centered at the origin is defined as the set of all the points :math:`x,y,z` at a distance :math:`\rho` away from :math:`(0,0,0)`, leading to the equation :math:`x^2 + y^2 + z^2 = \rho^2`.  We are looking for a "parametrization" or relationship between :math:`x,y,z` coordinates and spherical coordinates in terms of one radial and two angular variables.  These are called :math:`\rho, \theta`, and :math:`\phi`.

Auroux has a really nice description of parametrization of the sphere.  Start by considering the surface area element.

We describe where we are on the surface of the earth in terms of latitude and longitude.  In a similar way, we describe a position on the surface of a sphere in terms of two parameters, the angles :math:`\phi` and :math:`\theta`.  :math:`\phi` measures how far "north and south" we are (the latitude), while :math:`\theta` measures how far "east and west" we are (the longitude).

.. image:: /figs/latitude-longitude.png
   :scale: 50 %

Consider a sphere with radius :math:`a`. 

If we think about a point on the surface of the sphere in :math:`x,y,z` coordinates, and ignore :math:`z` for the moment, then what we will have is the *projection* of the point onto the :math:`x,y`-plane.  The same as in polar coordinates, the angle :math:`\theta` is the angle a ray to our point makes with the positive :math:`x`-axis, moving in a counter-clockwise direction.  (It ranges from :math:`0 \le \theta \le 2 \pi`).

Note that, in this projection, all the points with the same :math:`z` lie on a circle of radius :math:`r`, where :math:`r \le a`.  In the same way, lines of latitude on the globe are circles, but they are (mostly) not great circles.  The circumference of a line of latitude near the north pole is very small, while that at the equator is a great circle.

.. image:: /figs/spherical-projection.png
   :scale: 50 %

The second angle, :math:`\phi` is the "polar" angle that the same ray makes with the positive :math:`z`-axis.  (It ranges from :math:`0 \le \theta \le \pi`).  This angle determines both the value of :math:`z`, and the radius :math:`r` of our circle of latitude.

.. math::

    z = a \cos \phi
    
    r = a \sin \phi
    
.. image:: /figs/latitude-projection.png
   :scale: 50 %

Returning now to the element of surface area, recall that *angles are not lengths*.  For a given "rectangle" of surface area :math:`\Delta A`, the "vertical" or "longitudinal" sides are arcs of a great circle and the lengths of those sides will be :math:`a \times \Delta \phi`.

On the lines of latitude, we are no longer on a great circle but on a smaller circle of radius :math:`r` and the lengths of those sides will be:

.. math::

    r \Delta \phi = a \sin \phi \ \Delta \phi

Putting this together, the surface area element is

.. math::

    \Delta A = (a \sin \phi \ \Delta \phi) \times (a \ \Delta \theta)
    
    = a^2 \sin \phi \ \Delta \phi \ \Delta \theta

We can check that quickly by determining the surface area of the entire sphere:

.. math::

    A = \iint dA
    
    = \int_0^{2 \pi} \int_0^{\pi} a^2 \sin \phi \ d \phi \ d \theta

The inner integral is (:math:`a^2` times)

.. math::

    - \cos \phi \ \bigg |_0^{\pi} = -(-1 - 1) = 2

The outer integral is just :math:`2 \pi` (it nearly always is), so we obtain finally

.. math::

    A = 2 \pi a^2 2 = 4 \pi a^2

The correct result.

To get the volume element, we need to add the distance from the origin as a variable, which is called :math:`\rho`.  In the formula given above, we replace the fixed radius :math:`a` with the variable :math:`\rho`

.. math::

    \Delta A = \rho^2 \sin \phi \ \Delta \phi \ \Delta \theta

The volume element adds a third side :math:`\Delta \rho`, so we obtain for the volume element

.. math::

    \Delta V = \rho^2 \sin \phi \ \Delta \phi \ \Delta \theta \ \Delta \rho

.. image:: /figs/sphcoord.png
   :scale: 50 %

We can obtain the whole volume as

.. math::

    V = \iiint dV
    
    = \int_0^{2 \pi} \int_0^{\pi} \int_0^{a} \rho^2 \sin \phi \ d \phi \ d \theta \ d \rho
    
The inner integral is 

.. math::

    \frac{\rho^3}{3} \ \bigg |_0^a = \frac{a^3}{3}

The middle integral adds a factor of :math:`2` as before:

.. math::

    - \cos \phi \ \bigg |_0^{\pi} = -(-1 - 1) = 2

and the outer integral adds a factor of :math:`2 \pi` so we obtain finally

.. math::

    V = \frac{a^3}{3} \times 2 \times 2 \pi
    
    = \frac{4}{3} \pi a^3

The expected result.

(Note:  unfortunately, the mathematicians and the physicists did not agree on what to call these angles, so you may run into an alternative notation).

.. image:: /figs/spherical-physics.png
   :scale: 50 %

========
Jacobian
========

There is a general formula for determining the relative value of area or volume units in different coordinate systems.  The exchange rate (called the Jacobian) is the determinant of a matrix of partial derivatives.

.. math::

    r = \rho \sin \phi 

    x = r \cos \theta = \rho \sin \phi \cos \theta 

    y = r \sin \theta = \rho \sin \phi \sin \theta 

    z = \rho \cos \phi 

Now, above we said that :math:`x^2 + y^2 + z^2 = \rho^2`, as if it were obvious.  For a circle, we know that :math:`x^2 + y^2 = r^2` by using the Pythagorean theorem.  To get the same thing for a sphere, we use it in 3-dimensions, i.e. :math:`x^2 + y^2 = r^2` and then :math:`r^2 + z^2 = \rho^2`.

Let's just check that our parametrization (some people say parameterization) works:

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

We take the partial derivatives of :math:`x,y,z` with respect to :math:`\rho,\phi,\theta` and the resulting :math:`J` multiplies the latter system's volume element.

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

=======
Example
=======

Auroux (25,26) gives a spherical cap example that is a bit tricky.  Suppose we have a unit sphere centered at the origin and then it is sliced by a plane.  We want to integrate to find the volume of the "spherical cap".

In the general case, the plane might have any orientation.  In order to use symmetry and simplify the calculation, we should rotate the objects so that the plane is parallel to the :math:`x,y`-axis, with equation :math:`z = d`.  This :math:`d` is the distance from the origin to the closest point on the plane (which is on the :math:`z`-axis).

If the equation of the plane is scaled

.. math::

    ax + by + cd = d
    
so that :math:`N` is a unit vector (that is, if :math:`a^2 + b^2 + c^2 = 1`), then :math:`d` is the origin to the plane.  (prove this).

Suppose that the distance is :math:`1/\sqrt{2}`.  How do we set up the triple integral for the volume?  We will integrate first with respect to :math:`\rho`, then :math:`\phi`.  This amounts to fixing a ray in space and moving along it from the origin outward.  When do we enter our solid, and when do we leave it?  The latter is easy:  the upper bound is just :math:`\rho`.

We enter the solid at the point when :math:`z = 1/\sqrt{2}`, that's the equation of the plane.  But :math:`z = \rho \cos \phi` so :math:`\rho = 1/\sqrt{2} \cos \phi`.

As for :math:`\phi`, the lower bound is just :math:`\phi = 0` and the upper bound is :math:`1/\sqrt{2} = \sin \phi` so :math:`\phi = \pi/4`.  

Here is a figure with different labels:

.. image:: /figs/spherical_cap.png
   :scale: 50 %

We are saying that :math:`\alpha` in the figure is the complement of :math:`\phi`.

In our notation, :math:`z` (:math:`R-h` in the figure) is equal to :math:` \rho \cos \alpha` so

.. math::

    z = \frac{1}{\sqrt{2}} = \sin \phi

at the most extreme angle :math:`\phi`, so that makes :math:`\phi = \pi/4`.

Finally the triple integral is

.. math::

    V = \iiint dV
    
    = \int_0^{2 \pi} \int_0^{\pi/4} \int_{1/\sqrt{2} \cos \phi}^{1} \rho^2 \sin \phi \ d \rho \ d \phi \ d \theta

To evaluate the inner integral, we have

.. math::

    \frac{\rho^3}{3} \sin \phi \ \bigg |_{1/\sqrt{2} \cos \phi}^{1}
    
    = \sin \phi \ (\frac{1}{3} - \frac{1}{2 \sqrt{2}} \ \frac{1}{\cos^3 \phi})

Then we need to integrate this with respect to :math:`\phi`.  The first term is just :math:`-1/3 \ \cos \phi` and the second term is

.. math::

    \int - \frac{1}{2 \sqrt{2}} \ \frac{\sin \phi}{\cos^3 \phi} \ d \phi

So we have :math:`u^3` on the bottom and :math:`du` on the top which gives

.. math::

    - \frac{1}{4 \sqrt{2}} \frac{1}{\cos^2 \phi}

combined, that is

.. math::

    (-\frac{\cos \phi}{3} - \frac{1}{4 \sqrt{2}} \frac{1}{\cos^2 \phi}) \ \bigg |_0^{\pi/4}

    = (- \frac{1}{3 \sqrt{2}} - \frac{1}{4 \sqrt{2}} \frac{1}{2}) ) - (-\frac{1}{3} - \frac{1}{4 \sqrt{2}} \frac{1}{2})
    
    = \frac{1}{3}(1 - \frac{1}{\sqrt{2}}) 

Finally, we pick up a factor of :math:`2 \pi` as usual from the outer integral so 

.. math::

    = \frac{2}{3} \pi (1 - \frac{1}{\sqrt{2}})