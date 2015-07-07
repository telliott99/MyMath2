.. _kepler9:

########
Ellipses
########

Now, a bit about ellipses.  We will not assume this for the derivations, since we are going the other way, from Newton to Kepler.  But it might help to clarify things.

This whole problem of the orbits would be trivial if they were circular.  Then, the velocity vector :math:`\mathbf{v} = \dot{\mathbf{r}}` would be perpendicular to the position vector :math:`\mathbf{r}`.  On an ellipse, that isn't true.  Newton's diagram is drawn above with :math:`AB` not perpendicular to :math:`AS`.

But in an elliptical orbit, the planet's velocity is in the same direction as the tangent vector to the ellipse at that position.  And the tangent vector has a nice relationship to the radial vector.  We can get to the point more quickly by writing the parametrization

.. math::

    x = \cos \theta = \cos \omega t 

    y = \sin \theta = \sin \omega t 

    \mathbf{r}(t) = \ \langle x(t),y(t) \rangle

    = \langle \cos \omega t ,\sin \omega t \rangle 

    \mathbf{v} = \dot{\mathbf{r}} 

    = \ \langle -\omega \sin \omega t, \omega \cos \omega t \rangle 

What follows is a longer presentation borrowed from my short write-up on parametrization of the ellipse.

.. image:: /figs/ellipse_draw.png
   :scale: 50 %

Learning how to draw an ellipse using two pins and a circular string holding a pencil is an early adventure in mathematics.  The ellipse is the set of all points whose combined distance to the two pins (foci) is the same.

.. image:: /figs/ellipse_wikipedia.png
   :scale: 50 %

The pin positions with respect to the origin or center are called the foci, lying at the points (:math:`\pm f,0`).  The lengths of the axes (called semi-major and semi-minor) are usually labeled :math:`a` and :math:`b`.  Consider the situation when the pencil is at the point :math:`(0,a)`.  The length :math:`L` of the string is equal to twice the distance to the left focus, :math:`L = 2(f+a)`, so

.. math::

    a = \frac{L}{2} - f 

We learn in algebra that the equation for an ellipse is

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 

Here are three ellipses drawn with the same center.

.. image:: /figs/ellipses_three.png
   :scale: 50 %

They were drawn by adjusting the value on the right-hand side of the equation

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = r^2 

where :math:`r = \{ 1/2,1,2 \}`.  This is equivalent to scaling both :math:`a` and :math:`b` by the same factor of :math:`r`

.. math::

    \frac{x^2}{(ra)^2} + \frac{y^2}{(rb)^2} = 1 

When :math:`r=2` we need to make the string a bit less than twice as long, because the length :math:`f` is also involved:

.. math::

    ra = r(\frac{L}{2} - f) 

===============
Parametrization
===============

An alternative view is the one below, which shows (black curves) the upper half of two circles of radius :math:`r=1` and :math:`r=2` and an ellipse whose equation is

.. math::

    \frac{x^2}{2^2} + \frac{y^2}{1} = 1 

.. image:: /figs/p_ellipse.png
   :scale: 50 %

Here :math:`a=2` and :math:`b=1`.

The standard parametrization of the ellipse is

.. math::

    x = a \cos t 

    y = b \sin t 

which I had trouble visualizing, until I drew the picture.  The point is that the parameter :math:`t` is \emph{not} the angle that a ray to :math:`P` makes with the :math:`x`-axis, as it is for the circle.  Instead, to find the :math:`x` value of :math:`P` corresponding to :math:`t`, we extend the ray with angle :math:`t` to the larger circle, with radius :math:`a`, where we read off the :math:`x`-value as

.. math::

    x=a \cos t 

We go back to find the intersection of the same ray with the small circle to get

.. math::

    y = b \sin t 

The algebraic way to do this is to show that the parametrization is equivalent to the original formulation

.. math::

    x^2 = a^2 \cos^2 t 

    y^2 = b^2 \sin^2 t 

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = \cos^2 t + \sin^2 t = 1 

as expected.

========
Rotation
========

Let's return to the diagram of the ellipse with two bounding circles of radius :math:`a` and radius :math:`b`.  I have a new diagram on the next page.

Consider the coordinates of the point :math:`P=(x,y)` (the red dot in the first quadrant) as functions of the angle :math:`t`.  As we said, :math:`t` is \emph{not} the angle of a ray from the origin to :math:`P`.

Let's draw a ray (blue dotted line) from the origin that does have angle :math:`t` with the :math:`x`-axis.  How to find :math:`x` and :math:`y` from the diagram.  For :math:`x`, extend the ray to the outer circle.  The radius is :math:`a`, the angle is :math:`t`, and

.. math::

    a \cos t = x 

This is the parametrization of the ellipse introduced above.

.. image:: /figs/ellipse_fancy.png
   :scale: 50 %

The ray drawn with angle :math:`t` has the same :math:`x`-intercept with the outer circle as our point :math:`P` on the ellipse.  Similarly, the intercept of the ray with the inner circle has the same :math:`y`-value as the point :math:`P` on the ellipse.

We estimate the point :math:`P=(1.2,0.8)=(6/5,4/5)`.  Using our algebraic equation:

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 

Recall that :math:`a=2` and :math:`b=1` so

.. math::

    x^2 + 4y^2 = 4 

Plugging in for :math:`x^2` and :math:`y^2` we get

.. math::

    \frac{36}{25} + 4 \ (\frac{16}{25}) = \frac{100}{25} = 4 

as expected.  Reading off the intercepts for the ray with angle :math:`t` (dotted blue line) with the outer circle, we have the point :math:`(1.2,1.6)` at a distance :math:`2` from the origin.  Thus,

.. math::

    \frac{1.2}{2} = 0.6 = \cos t 

    t \approx 0.927\ \text{rad} \approx 53^{\circ} 

Looking again at the figure, we want to consider what happens for the angle :math:`u = t + \pi/2`.  This is the dotted blue ray in the second quadrant.

We might calculate the values of sine and cosine for :math:`u`, but notice that if we view :math:`u` as a vector, its \emph{dot product} with :math:`t` must be equal to zero.  The coordinates of the intercept of the rotated vector with the outer circle are :math:`(-1.6,1.2)`, so the cosine of the angle :math:`u` is

.. math::

    \cos u = -0.8 

    u \approx 2.498 = t + \frac{\pi}{2} \ \text{rad} \approx 143^{\circ} 

We confirm that

.. math::

    2.498 - 0.927 = 1.57 = \frac{\pi}{2} 

The coordinates of the point on the ellipse are :math:`(-1.6,0.6)`, which we check against the formula

.. math::

    x^2 + 4y^2 = 4 

    (1.6)^2 + 4(0.6)^2 = 2.56 + 4(0.36) = 4 

(no clean fractions this for this one).

=======
Tangent
=======

Finally, and this is really the point of the write-up, the vector to the point, call it :math:`Q`, on the ellipse (red dot in the second quadrant) is the tangent to the ellipse for the point :math:`P` in the first quadrant, and vice-versa.

How did this happen?  Recall what we did.  We had

.. math::

    x = a \cos t 

    y = b \sin t 

The rotated point :math:`Q = (x',y')` is

.. math::

    x' = a \cos (t + \frac{\pi}{2}) 

    y' = b \sin (t + \frac{\pi}{2}) 

.. image:: /figs/sine_cosine_wikipedia.png
   :scale: 50 %

Sine is like cosine, but shifted to the right by :math:`\pi/2`

.. math::

    \cos \theta = \sin (\theta + \frac{\pi}{2}) 

    \sin \theta = - \cos (\theta + \frac{\pi}{2}) 

So

.. math::

    x' = a \cos (t + \frac{\pi}{2}) = -a \sin t 

    y' = b \sin (t + \frac{\pi}{2}) = b \cos t 

So what, you say.  Well, let's look at the position vector, which can be written :math:`\mathbf{r}(t)`, since it's a function of the angle :math:`t` or the time, but we will just use :math:`\mathbf{r}`.  It has components :math:`x` and :math:`y`.

.. math::

    \mathbf{r} = \langle x,y \rangle \ 
    
    = \langle a \cos t,b \sin t \rangle

Now, the tangent to the ellipse is precisely the direction in which a particle at :math:`(x,y)` is currently moving on the ellipse.  The tangent vector points in the same direction as the velocity vector, but :math:`\mathbf{v}` is just the time-derivative of the position vector.

.. math::

    \mathbf{v} = \frac{d\mathbf{r}}{dt} = \ \langle \frac{dx}{dt}, \frac{dy}{dt} \rangle \ = \ \langle -a \sin t,b \cos t \rangle = \ \langle x',y' \rangle 

And that's the point.   :)
