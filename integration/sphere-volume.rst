.. _sphere-volume:

####################
Volume of the sphere
####################

One of the great things about calculus is the discovery that one can use integration to compute not only the areas of plane figures, but also surface areas and volumes in 3D space (:math:`\mathbb{R}3`).

I previously wrote up several techniques for doing this in single variable calculus (the methods of "disks" and "shells"), as well as what Archimedes discovered.  That material is in the other book (MyMath).  Here we will just do the double and triple integral parts.

===============
Double integral
===============

Consider the sphere as a function :math:`f(x,y)` of points in the :math:`xy`-plane.  The graph of this function is plotted on the :math:`z`-axis, above the points.  (Here we consider one octant of the hemisphere, the part where :math:`x,y,z > 0`).  The equation is

.. math::

    R^2 = x^2 + y^2 + z^2 


    z = f(x,y) = \sqrt{R^2 - x^2 - y^2} 


The "shadow" of the sphere is a quadrant of the circle of radius :math:`R` (since :math:`z=0` in the :math:`xy`-plane).  For each little area element :math:`dA` inside the shadow, we find the distance up to the graph of the function as :math:`f(x,y)`.

It's going to be an adventure, but suppose we try using Cartesian coordinates, and integrate first with respect to :math:`y` and then with respect to :math:`x`.  We will have

The volume is this double integral

.. math::

    V = \int_{x=0}^{x=R} \int_{y=0}^{\sqrt{R^2-x^2}}  \sqrt{R^2 - x^2 - y^2} \ dy \ dx 


This looks rather forbidding, but it won't be too bad.  Let us first, for the moment, substitute :math:`a = \sqrt{R^2-x^2}` and keep in mind that this is a constant for the inner integral.  So that part is now

.. math::

    \int_{y=0}^{a} \sqrt{a^2 - y^2} \ dy 


A little investigation reveals that the right approach to this is a trig substitution, namely

.. math::

    y = a \sin \theta 


    dy = a \cos \theta \ d \theta 


We will have

.. math::

    \int \sqrt{a^2 - a^2 \sin^2 \theta} \ a \cos \theta \ d \theta 


    \int a^2 \sqrt{1 - \sin^2 \theta} \cos \theta \ d \theta 


    \int a^2 \cos^2 \theta \ d \theta 


The crucial thing is to change the limits.  We need to find the value of :math:`\theta` at the old limits for :math:`y`, namely

.. math::

    y = 0, \ \ 0 = a \sin \theta, \ \ \theta = 0 


    y = a, \ \ a = a \sin \theta, \ \ \theta = \frac{\pi}{2} 


So

.. math::

    \int_0^{\pi/2} a^2 \cos^2 \theta \ d \theta 


    = a^2 \int_0^{\pi/2} \frac{1}{2}(1 + \cos 2 \theta) \ d \theta 


    = a^2 \ \frac{1}{2} \ (\theta + \frac{1}{2} \sin 2 \theta) \ \bigg |_0^{\pi/2} 


    = \frac{a^2}{2} (\frac{\pi}{2} + 0 - 0 - 0) 


    = a^2 \frac{\pi}{4} = (R^2-x^2) \frac{\pi}{4} 


So then finally the outer integral is

.. math::

    \int_{x=0}^{x=R} (R^2-x^2) \frac{\pi}{4} \ dx 


    = \frac{\pi}{4} (R^2x - \frac{1}{3}x^3) \ \bigg |_0^R 


    = \frac{\pi}{4} \ \frac{2}{3}R^3 = \frac{1}{6}\pi R^3 


Recall that this is for one octant, so for the whole sphere we multiply by :math:`8` and obtain:

.. math::

    = \frac{8}{6}\pi R^3 = \frac{4}{3}\pi R^3 


===============
Triple integral
===============

For the triple integral, we are integrating the volume element over the entire range of values inside the sphere.

.. math::

    V = \iiint dV 


We can do this integral relatively easily in both cylindrical and spherical coordinates.  For completeness, I'm going to try it in Cartesian coordinates as well.

Consider the one-eighth of the sphere that has :math:`x,y,z>0`.

Let's work from the outside in.  We will do :math:`x` last.  The limits on :math:`x` are :math:`x=0 \rightarrow R`.  Simple enough.  The shadow of the sphere in the :math:`xy`-plane is a circle with radius :math:`R` and so the limits on :math:`y` are :math:`y=0 \rightarrow \sqrt{R^2-x^2}`.

And then, naturally enough, the limits on :math:`z` are :math:`z=0 \rightarrow \sqrt{R^2 - x^2 - y^2}`.

So our integral is

.. math::

    \int_{x=0}^{R} \int_{y=0}^{\sqrt{R^2-x^2}} \int_{z=0}^{\sqrt{R^2 - x^2 - y^2}} \ dz \ dy \ dx 


The inner integral is trivial.  The middle integral is then

.. math::

    \int_{y=0}^{\sqrt{R^2-x^2}} \sqrt{R^2 - x^2 - y^2} \ dy 


And this is where it gets interesting.  Notice that :math:`x` is constant here.  So, setting :math:`a^2 = R^2 - x^2`, the integral is of the form

.. math::

    \int \sqrt{a^2 - y^2} \ dy 


There are several different ways to write the answer to this one.  (We did this in the previous section).  Here, I am going to use:

.. math::

    \frac{a^2}{2} \sin^{-1} \frac{y}{a} + \frac{y \sqrt{a^2-y^2}}{2} 

The geometric explanation of these terms is really interesting, see the first book.

Plugging in :math:`a^2 = R^2 - x^2` as well as the upper limit :math:`y= \sqrt{R^2-x^2}` we obtain

.. math::

    \frac{R^2 - x^2}{2} \sin^{-1} \frac{\sqrt{R^2-x^2}}{\sqrt{R^2-x^2}} + \frac{\sqrt{R^2-x^2} \sqrt{R^2-x^2 - (R^2-x^2)}}{2} 


Luckily, the second term is zero.  And since :math:`\pi/2 =  \sin^{-1} (1)`, for this part we have just

.. math::

    = \frac{R^2 - x^2}{2} \cdot \frac{\pi}{2} 


At the lower, limit (:math:`y=0`), the first term includes :math:`\sin^{-1} (0)`, which equals zero, and the second term has a factor of :math:`y`, so the whole thing is just zero.

So with that dramatic simplification we come, finally, to the outer integral, which is

.. math::

    \frac{\pi}{4} \int_0^R R^2 - x^2 \ dx 


    = \frac{\pi}{4} \cdot \frac{2}{3} R^3 


    = \frac{\pi}{6} R^3 


Since there are eight such volumes in the complete sphere, we obtain the familiar answer.

==========================================
Triple integral in cylindrical coordinates
==========================================



The equation of the sphere in Cartesian coordinates is:

.. math::

    R^2 = x^2 + y^2 + z^2 


Converting to polar coordinates we have

.. math::

    r^2 = x^2 + y^2 


    R^2 = z^2 + r^2 


    z = \sqrt{R^2 - r^2} 


Recall that the area element in polar coordinates is :math:`dA = r \ dr \ d \theta`.

If we integrate first with respect to :math:`z` we have

.. math::

    \int \int \int dz \ r \ dr \ d \theta 


The limits on :math:`r` and :math:`\theta` are as usual:

.. math::

    \int_0^{2\pi} \int_0^R \int dz \ r \ dr \ d \theta 


In particular, we integrate over the entire shadow of the sphere on the :math:`xy`-plane.  Now, for each value of :math:`r` and :math:`\theta` we must find the limits on :math:`z`.  From above, we get

.. math::

    \int_0^{2\pi} \int_0^R \int_{-\sqrt{R^2 - r^2}}^{\sqrt{R^2 - r^2}} dz \ r \ dr \ d \theta 

The inner integral is just

.. math::

    z  \ \bigg |_{-\sqrt{R^2 - r^2}}^{\sqrt{R^2 - r^2}} = 2 \sqrt{R^2 - r^2}

So the middle integral is then

.. math::

    \int_0^R 2(\sqrt{R^2 - r^2}) \ r \ dr 

    = -\frac{2}{3}(R^2 - r^2)^{3/2}  \ \bigg |_0^R = \frac{2}{3} R^3 


The outer integral is trivial

.. math::

    \int_0^{2\pi} \frac{2}{3} R^3 \ d \theta = \frac{4}{3} \pi R^3  


========================================
Triple integral in spherical coordinates
========================================

Here is the figure from \emph{How to Ace Calculus}

.. image:: /figs/sphcoord.png
   :scale: 50 %

In spherical coordinates, we see that the volume element is

.. math::

    dV = \rho^2 \sin \phi \ d \rho \ d \phi \ d \theta 


And having used that, our work is essentially done.  We just set up the integral

.. math::

    \int_0^{2\pi} \int_0^{\pi} \int_0^R \rho^2 \sin \phi \ d \rho \ d \phi \ d \theta 


The very nice thing about this is that the limits on :math:`\rho` do not depend on the angles :math:`\phi` and :math:`\theta`.  So now the inner integral is just

.. math::

    = \int_0^R \rho^2 \sin \phi \ d \rho = \frac{1}{3}R^3 \sin \phi 


And the term :math:`R^3/3` is a constant.  So we put that aside and evaluate the middle integral

.. math::

    \int_0^{\pi} \sin \phi \ d \phi 


    = - \cos \phi \ \bigg |_0^{\pi} = - (- 2) = 2


So in the end we have

.. math::

    2 \pi \cdot 2 \cdot \frac{1}{3}R^3 = \frac{4}{3} \pi R^3 


=================
Method of spheres
=================

The last method is my favorite.  I'm not sure what it's official name is, so I just made one up.

This is an integral in a single variable.  We think about how the volume of the sphere depends on :math:`r` (:math:`r = 0 \rightarrow R`).  An incremental change :math:`dr` changes the volume by adding a thin shell (sphere?) of volume equal to the surface area of the sphere (:math:`4 \pi r^2`) times :math:`dr`.  That is

.. math::

    dV = 4 \pi r^2 \ dr 


    V = \int dV = \int_0^R 4 \pi r^2 \ dr 


    = 4 \pi \ \ \frac{1}{3}r^3 \ \bigg |_0^R = \frac{4}{3}\pi R^3 


Again.

============================
Deriving the formula we used
============================

Up above in the first section of volume integrals (Cartesian coordinates) we used this formula

.. math::

    \int \sqrt{a^2 - y^2} \ dy = \frac{a^2}{2} \sin^{-1} \frac{y}{a} + \frac{y \sqrt{a^2-y^2}}{2} 


Let me re-write it in a more familiar but equivalent form

.. math::

    \int \sqrt{a^2 - x^2} \ dx = \frac{a^2}{2} \sin^{-1} \frac{x}{a} + \frac{x \sqrt{a^2-x^2}}{2} 


We use a simple trig substitution.

.. math::

    \frac{x}{a} = \sin t 


    x = a \ \sin t 


    dx = a \ \cos t \ dt 


Using Pythagoras

.. math::

    \sqrt{a^2 - x^2} = a \cos t 


Substituting

.. math::

    \int \sqrt{a^2 - x^2} \ dx 


    = a \cos t \ a \cos t \ dt 


    = a^2 \cos^2 t \ dt 


An old friend!  I'm not going to work this one out from scratch, we've seen it in other write-ups.  One of the equivalent forms for this integral is

.. math::

    \int \cos^2 t \ dt = \frac{1}{2}(t + \sin t \cos t) 


Picking up the outside factor of :math:`a^2` and substituting we obtain

.. math::

    = a^2 \ \frac{1}{2} (\sin^{-1}\frac{x}{a} + \frac{x}{a} \frac{\sqrt{a^2-x^2}}{a} ) 


    = \frac{a^2}{2} \sin^{-1} \frac{x}{a} + \frac{x \sqrt{a^2-x^2}}{2} 

