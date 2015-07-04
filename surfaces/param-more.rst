.. _param-more:

####################
More parametrization
####################

When we parametrized curves, we were able to work with curves which expressed :math:`x`,:math:`y` and :math:`z` as functions of a \single parameter, which we usually call :math:`t`.  For surfaces, we will usually have two variables :math:`u` and :math:`v`.  For example, on the globe we locate our position by longitude and latitude.

As an example, consider

.. math::

    \mathbf{r}(u,v) = u \hat{i} + u \ \cos \ v \hat{j} + u \ \sin \ v \hat{k} 

We have three parametric equations, one for each variable

.. math::

    x = u 

    y = u \ \cos \ v 

    z = u \ \sin \ v 

So what this looks like is that we'll have a circle parallel to the yz-plane with radius :math:`u`, where :math:`u = x`.  We notice that if we square all the terms

.. math::

    x^2 = u^2 

    y^2 + z^2 = u^2 \\cos^2 \ v + u^2 \\sin^2 \ v = u^2 = x^2 

Going from the equations back to the surface is fairly unusual.  Typically we do things the other way around.

==========
Paraboloid
==========

Suppose we start with the elliptic paraboloid

.. math::

    x = 5y^2 + 2z^2 - 10 

To visualize this, think about what happens when :math:`x=0`.  Then we have an ellipse parallel to the :math:`yz`-plane.  At :math:`x=-10`, :math:`y=z=0`;  and :math:`x` must be at least :math:`-10`, because otherwise the squared terms would have to sum to less than zero, which is impossible with real numbers.

If we plot this

.. image:: /figs/param1.png
   :scale: 50 %

the paraboloid is symmetric around the x-axis (the cross-sections really are ellipses), and the vertex is at :math:`x=-10`.  Here, we can pick :math:`y` and :math:`z` to be anything (there is a point on the surface for every :math:`y,z` pair).  :math:`x` is given by the equation above so

.. math::

    \mathbf{r}(y,z) = (5y^2 + 2z^2 -10)\hat{i} + y \hat{j} + z \hat{k} 

======
Sphere
======

.. math::

    x^2 + y^2 + z^2 = 16 

This is just a sphere of radius :math:`4`.  The parametric representation uses the two angles :math:`\phi` and :math:`\theta`.

.. math::

    x = \rho \ \sin \phi \ \cos \theta 

    y = \rho \ \sin \phi \ \sin \theta 

    z = \rho \ \cos \phi 

where :math:`\phi` is the angle with respect to the positive z-axis.  So in the xy-plane

.. math::

    \phi=\pi/2, \ \ \cos \phi = 0, \ \ z = 0, \ \ x = \rho \ \cos \theta, \ \ y = \rho \ \sin \theta 

and we just have a circle of radius :math:`\rho`.  In fact, for any :math:`z < \rho`, the angle :math:`\phi` is determined, which then makes the radius of the circle traced out by :math:`x` and :math:`y` smaller.

.. math::

    \mathbf{r}(\theta,\phi) = \rho \ \sin \phi \ \cos \theta \ \hat{i} + \rho \ \sin \phi \ \sin \theta  \ \hat{j} + \rho \ \cos \phi \ \hat{k} 

    0 \le \phi \le \pi, \ \ 0 \le \theta \le 2 \pi 

=======================
Cylindrical coordinates
=======================

.. math::

    x^2 + y^2 = 25 

Now we have no restrictions on :math:`z`.

.. math::

    x = r\cos \theta, \ \ y = r\sin \theta, \ \ z = z 

    \mathbf{r}(\theta,\phi) = r\cos \theta \ \hat{i} + r\sin \theta \ \hat{j} + z \hat{k} 

    0 \le \theta \le 2 \pi 

=============
Tangent plane
=============

A crucial idea is the method to find the equation of the tangent plane to a surface at a point.

.. math::

    \mathbf{r}(u,v) = x(u,v) \ \hat{i} + y(u,v) \ \hat{j} + z(u,v) \  \hat{k} 

The method is to find these two vectors

.. math::

    \mathbf{r_u}(u,v) = \frac{\partial x}{\partial u}(u,v) \ \hat{i} + \frac{\partial y}{\partial u}(u,v) \ \hat{j} + \frac{\partial z}{\partial u}(u,v) \  \hat{k} 

    \mathbf{r_v}(u,v) = \frac{\partial x}{\partial v}(u,v) \ \hat{i} + \frac{\partial y}{\partial v}(u,v) \ \hat{j} + \frac{\partial z}{\partial v}(u,v) \  \hat{k} 

Now just form the cross product

.. math::

    \mathbf{r_u} \times \mathbf{r_v} = \mathbf{n} 

Provided :math:`\mathbf{n} \ne 0`, this is the normal vector to the surface.

=======
Example
=======

Suppose we have

.. math::

    \mathbf{r}(u,v) = u \ \hat{i} + 2v^2 \ \hat{j} + (u^2 + v) \ \hat{k} 

and we're looking at the point :math:`(2,2,3)`.  We find the two tangent vectors u\sing the equation above

.. math::

    \mathbf{r_u} = \hat{i} + 2u \ \hat{k} = \ <1,0,2u> 

    \mathbf{r_v} = 4v \ \hat{j} + \hat{k} = \ <0,4v,1> 

The cross product is set up like this

.. math::

    \begin{bmatrix}
    \hat{i} & \hat{j} & \hat{k} \\
    1 & 0 & 2u \\
    0 & 4v & 1
    \end{bmatrix}

so

.. math::

    \mathbf{n} = -8uv \ \hat{i} - \hat{j} + 4v \ \hat{k} = \ <-8uv, -1, 4v> 

So far so good, but now we need to solve for :math:`u` and :math:`v`.  We plug the point we were given into the parametric equations

.. math::

    x = u, \ \ y = 2v^2, \ \ z = u^2 + v 

    2 = u, \ \ 2 = 2v^2, \ \ 3 = u^2 + v 

From the first two equations we get

.. math::

    u = 2, v = \pm 1 

And the third equation restricts :math:`v` further

.. math::

    v = -1 

So then the normal vector is

.. math::

    \mathbf{n} = \ <16, -1, -4> 

and the tangent plane is just

.. math::

    16(x-2) - (y-2) -4(z-3) = 0 

    16x -y -4z = 18 

That was fairly painless!

============
Surface area
============

The surface area is given by

.. math::

    A = \int \int_D \ \Vert \mathbf{r_u} \times \mathbf{r_v} \Vert \ dA 

Consider a sphere of radius :math:`a`

.. math::

    x^2 + y^2 + z^2 = a^2 

If we parametrize this as before

.. math::

    x = \rho \ \sin \phi \ \cos \theta = a \ \sin \phi \ \cos \theta 

    y = \rho \ \sin \phi \ \sin \theta = a \ \sin \phi \ \sin \theta

    z = \rho \ \cos \phi = a \ \cos \phi 

We can either remember that the normal vector at any point on this sphere is

.. math::

    \mathbf{n} = \ <x, y, z> 

or we can write

.. math::

    \mathbf{r}(\theta,\phi) = a \ \sin \phi \ \cos \theta \ \hat{i} + a \ \sin \phi \ \sin \theta \ \hat{j} + a \ \cos \phi \ \hat{k} 

    \mathbf{r_{\theta}} = - a\ \sin \phi \ \sin \theta \ \hat{i} + a \ \sin \phi \ \cos \theta \  \hat{j} + 0 \ \hat{k} 

    \mathbf{r_{\phi}} = a\ \cos \phi \ \cos \theta \ \hat{i} + a \ \cos \phi \ \sin \theta \  \hat{j} - a \ \sin \phi \ \hat{k} 

And

.. math::

    \mathbf{N} = \mathbf{r_{\theta}} \times \mathbf{r_{\phi}} = a^2

    \begin{bmatrix}
    \hat{i} & \hat{j} & \hat{k} \\
    -\sin \phi \ \sin \theta & \sin \phi \ \cos \theta & 0 \\
    \ \ \cos \phi \ \cos \theta & \cos \phi \ \sin \theta & -\sin \ \phi
    \end{bmatrix}

the components are (all multiplied by :math:`a^2`) and then we have

.. math::

    -\sin^2\phi \ \cos \ \theta \  \hat{i} 

    -\sin^2\phi \ \sin \ \theta \  \hat{j} 

    -\sin\phi \ \cos\phi \ \sin^2\theta - \sin\phi \ \cos\phi \ \cos^2\theta \  \hat{k} = -\sin \phi \ \cos \phi \  \hat{k} 

    \mathbf{N} = a^2 \ \sin \phi \ <-\sin \phi \ \cos \theta, -\sin \phi \ \sin \theta, -\cos \phi > 

    \Vert \mathbf{N} \Vert = a^2 \ \sin \phi \ \sqrt{\sin^2\phi \ \cos^2\theta + \sin^2\phi \ \sin^2\theta + \cos^2\phi } 

    \Vert \mathbf{N} \Vert = a^2 \ \sin \phi \ \sqrt{\sin^2\phi  + \cos^2\phi } = a^2 \ \sin \phi

    \mathbf{n} = \mathbf{N} / \Vert \mathbf{N} \Vert = \ <-\sin \phi \ \cos \theta, -\sin \phi \ \sin \theta, -\cos \phi > 

This is the unit normal at the point

.. math::

    (a \ \sin \phi \ \cos \theta, a \ \sin \phi \ \sin \theta, a \ \cos \phi ) = (x,y,z) 

The sign of the normal vector is negative.  By convention :math:`\mathbf{n}` points into the sphere.

How do we integrate this to get the surface area?  Aren't we mixing up :math:`x,y,z` with :math:`\theta,\phi`?  The answer is that in this formula

.. math::

    A = \int \int_D \ \Vert \mathbf{r_{\theta}} \times \mathbf{r_{\phi}} \Vert \ dA = \int \int_D \ \Vert \mathbf{N} \Vert \ dA = \int \int_D \ a^2 \ \sin \phi \ dA 

:math:`dA = \ d\theta \ d\phi`.  It is not really the area element, because we need to correct by u\sing the Jacobian, which is what we really just computed above..

The area element is actually :math:`a^2 \ \sin \phi \ d\theta \ d\phi`.

.. math::

    A = \int \int_D \ a^2 \ \sin \phi \ d\theta \ d\phi 

    0 \le \phi \le \pi, \ \ 0 \le \theta \le 2 \pi 

    A = \int_0^{\pi} \int_0^{2\pi} \ a^2 \ \sin \phi \ d\theta \ d\phi 

The inner integral is

.. math::

    \int_0^{2\pi} \ a^2 \ \sin \phi \ d\theta = 2 \pi a^2 \ \sin \phi 

and the outer integral is then

.. math::

    \int_0^{\pi} 2 \pi a^2 \ \sin \phi \  d \phi = 2\pi a^2 (-1)(\cos \phi) \bigg |_0^{\pi} =  2\pi a^2 (-1)(-2) = 4\pi a^2 

which is correct.

==================
Formulas (Marsden)
==================

We don't actually have to set up the cross product as the determinant, because we are going to get the norm (magnitude) of it right away.

.. math::

    \Vert \mathbf{r_{\theta}} \times \mathbf{r_{\phi}} \Vert = \sqrt{(\frac{\partial (x,y)}{\partial (u,v)})^2 + (\frac{\partial (y,z)}{\partial (u,v)})^2 + (\frac{\partial (x,z)}{\partial (u,v)})^2}

where

.. math::

    \frac{\partial (y,z)}{\partial (u,v)}) =

    \begin{vmatrix}
    \frac{\partial x}{\partial u} & \frac{\partial x}{\partial v} \\
    \frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}
    \end{vmatrix}

and so on.  This is our old friend, the Jacobian.  Thus, the area formula becomes

.. math::

    A = \int \int_R \sqrt{(\frac{\partial (x,y)}{\partial (u,v)})^2 + (\frac{\partial (y,z)}{\partial (u,v)})^2 + (\frac{\partial (x,z)}{\partial (u,v)})^2} \ du \ dv 

========
One more
========

I have one more example from Paul.  He says:  find the surface area of the portion of the sphere of radius :math:`4` that lies inside the cylinder :math:`x^2 + y^2 = 12` and above the xy-plane.

This shape is called a "spherical cap."  The problem should be pretty easy because we just worked out the area element for the sphere above.  We have

.. math::

    A = \int \int_D \ a^2 \ \sin \phi \ d\theta \ d\phi 

The trick is to find out where the cylinder and the sphere intersect.  We have

.. math::

    x^2 + y^2 + z^2 = 16 

    x^2 + y^2 = 12 

These are both true when :math:`z^2 = 4, z = \pm \ 2`.

What we need to do is to find the angle :math:`\phi` that this corresponds to.  \since we know that

.. math::

    z = a \ \cos \phi, \ \ a = 4, \ \ z=2 

    \cos \phi = \frac{1}{2}, \ \ \phi = \frac{\pi}{3} 

So we have that the range of :math:`\phi` is

.. math::

    0 \le \phi \le \frac{\pi}{3} 

Remember that :math:`\phi = 0` at the top of the sphere, and that's the part we want, above the circle formed by the intersection of the cylinder and the sphere.

.. math::

    A =  \int_0^{\pi/3} \int_0^{2\pi} \ a^2 \ \sin \phi \ d\theta \ d\phi 
    
The inner integral is

.. math::

    \int_0^{2\pi} \ a^2 \ \sin \phi \ d\theta = 2\pi a^2 \ \sin \phi 

and the outer is

.. math::

    \int_0^{\pi/3} 2\pi a^2 \ \sin \phi   \ d\phi 

    2\pi a^2 \ (-\cos \phi) \ \bigg |_0^{\pi/3} = 2\pi a^2 (-\frac{1}{2} + 1) = \pi a^2 = 16 \pi 
