.. _easy surface:

#######################
Basic Surface Integrals
#######################

Let's see if we can figure out the basic facts about surface integrals as simply as we can.  We would like to work in :math:`x,y,z` coordinates.  We will move through the shadow of a surface in the :math:`x,y`-plane in little increments of area :math:`dA`, and what we need to find is the exchange rate of those elements :math:`dA` with the surface that lies above.

For a point on a surface, we use the tangent plane approximation.  Imagine that the surface is tiled, composed of numerous tiny planes.  At any point, the surface is locally flat, having uniform slope and constant normal vector.  We want to find the angle :math:`\theta` that this plane makes with the horizontal.

.. image:: /figs/tilt.png
   :scale: 50 %

We use :math:`\theta` for this calculation:

.. math::

    dA = \cos \theta \ dS 

    dS = \frac{dA}{\cos \theta}

A little piece of area on the surface is larger than its projection on the :math:`xy`-plane by exactly this factor.

Like any plane, we describe a tangent plane by its normal vector, :math:`\mathbf{n}`.  You can probably see that :math:`\mathbf{n}` makes the same angle :math:`\theta` with the :math:`z`-axis or :math:`\hat{\mathbf{k}}` unit vector.  (Think about what happens in the limiting case when the surface is horizontal, then :math:`\theta` is zero).

So:

.. math::

    \mathbf{n} \cdot \hat{\mathbf{k}} = |\mathbf{n}| |\hat{\mathbf{k}}| \ \cos \theta 

Since :math:`\hat{\mathbf{k}}` is a unit vector, :math:`|\hat{\mathbf{k}}| = 1`

.. math::

    \mathbf{n} \cdot \hat{\mathbf{k}} = |\mathbf{n}| \ \cos \theta 

    \cos \theta = \frac{\mathbf{n} \cdot \hat{\mathbf{k}} }{|\mathbf{n}|} 

As always, we find :math:`\mathbf{n}` by first finding two vectors in the plane and then forming their cross-product.

Think about a cross-section of the plane at a point of interest, parallel to the :math:`xz`-plane.

The surface at this cross-section is just a line with some tilt to it.  The line has slope :math:`f_x`.  For each unit of change in :math:`x` or :math:`\hat{\mathbf{i}}` direction, there is a change of :math:`f_x` in the :math:`\hat{\mathbf{k}}` direction and no change in the :math:`\hat{\mathbf{j}}` direction.  So one vector in the plane is

.. math::

    \langle 1, 0, f_x \rangle 

By symmetry the second vector in the tangent plane is, of course,

.. math::

    \langle 0, 1, f_y \rangle 

Their cross-product is

.. math::

    \langle -f_x, -f_y, 1 \rangle = \mathbf{n}  

We have scaled things so that :math:`\mathbf{n} \cdot \hat{\mathbf{k}}` is :math:`1`!  Our currency exchange rate for area in the plane compared to area on the sloped tangent plane is the Jacobian:

.. math::

    \cos \theta = \frac{\mathbf{n} \cdot \hat{\mathbf{k}}}{ |\mathbf{n}|} =  \frac{1}{|\mathbf{n}|} =  \frac{dA}{dS} 

    dS = |\mathbf{n}| \ dA 

and

.. math::

    |\mathbf{n}| = \sqrt{1 + f_x^2 + f_y^2} 

So

.. math::

    \text{Surface area} = \iint_S \ dS = \iint \sqrt{1 + f_x^2 + f_y^2} \ dx \ dy 

+++++++
Example
+++++++

The hemisphere of radius :math:`R`

.. math::

    x^2 + y^2 + z^2 = R^2

    z = f(x,y) = \sqrt{R^2 - x^2 - y^2} 
    
    f_x = \frac{-2x}{2 \sqrt{R^2 - x^2 - y^2}}
    
    = -\frac{x}{z}
    
    f_y = -\frac{y}{z} 

    |\mathbf{n}| = \sqrt{1 + f_x^2 + f_y^2}  
    
    =  \sqrt{1 + (\frac{x}{z})^2 + (\frac{y}{z})^2} 

    = \frac{1}{z}  \sqrt{z^2 + x^2 + y^2} = \frac{R}{z} 

Hence

.. math::

    SA = \iint |\mathbf{n}| \ dx \ dy = \iint \frac{R}{z} \ dx \ dy 

The smart thing is to switch to polar coordinates:

.. math::

    = R \iint \frac{1}{\sqrt{R^2-r^2}} \ r \ dr \ d \theta 

    -2 \pi R\ [ \ \sqrt{R^2-r^2} \ ] \ \bigg |_0^R  
    
    = 2 \pi R^2  

and twice that for the sphere.

Alternatively, we can actually do the double integral.  Take :math:`dy` first:

.. math::

    SA = \int_{x=-R}^{x=R} \int_{y=-\sqrt{R^2 - x^2}}^{y=\sqrt{R^2 - x^2}} \frac{R}{\sqrt{R^2 - x^2 - y^2}} \ dy \ dx

For the inner integral :math:`x` is a constant.  Let :math:`a^2 = R^2 - x^2`, then that integral is:

.. math::

    R \int_{-a}^a \frac{1}{\sqrt{a^2 - y^2}} \ dy

We've done this integral before.  Try a trig substitution

.. math::

    y/a = \sin t
    
    dy = a \cos t \ dt
    
    \frac{1}{\sqrt{a^2 - x^2}} = \frac{1}{\cos \theta}

So the integral is simply :math:`\int dt = t`, and the whole thing is

.. math::

    = R \sin^{-1} \frac{y}{a} \ \bigg |_{-a}^{a} = \frac{\pi}{2} - - \frac{\pi}{2} = \pi R
 
The outer integral is

.. math::

    \pi R \int_{-R}^{R} dx = 2 \pi R^2

which is matches.