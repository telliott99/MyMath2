.. _average value:

#############
Average value
#############

We want to consider the idea of the *average value* of a function (over an interval).  One way to think of that would be, by analogy to a list of numbers, to collect the values of :math:`f(x)` at each point along the graph of the function, add them up, and then divide by :math:`N` to obtain the mean.  Of course, the fact that there are an infinite number of such points is a bit of an issue.

Let's think of it another way.  Suppose we integrate and find the total area under the curve between :math:`x=a \rightarrow b`.  Take the number calculated from the definite integral, divide by the distance :math:`b-a`, and plot the result as a height :math:`h` so as to form a rectangle above the :math:`x-axis`.

.. image:: /figs/avgvalue.png
   :scale: 50 %

Clearly :math:`h` is a reasonable stand-in for the average value of :math:`f(x)`, since the rectangle formed from :math:` [a,b] \times [0,h]` gives the same area as we found under the curve by integration.  Call this :math:`\bar{f}(x)`.  Define it to be

.. math::

    \bar{f}(x) = \frac{1}{b-a} \int_a^b f(x) \ dx 

The average value of a function over an interval is the integral of the function divided by the length of the interval.

This definition also works in 2D or more dimensions.  Consider the unit circle centered at the origin.  We compute the average value of :math:`x`:

.. math::

    \bar{x} = \frac{1}{Area} \ \iint_R x \ dA 

where the area is, of course, the same integral but without the function :math:`x` inside.

Since we do have the :math:`x`, we might want to keep Cartesian coordinates.  The limits on :math:`y` are the usual ones.  We set it up like so:

.. math::

    \int_{x=-1}^{1} \int_{y=-\sqrt{1-x^2}}^{\sqrt{1-x^2}} x \ dy \ dx 

The inner integral is just

.. math::

    xy \ \bigg |_{y=-\sqrt{1-x^2}}^{\sqrt{1-x^2}} 


    = 2 x \sqrt{1-x^2} 


And the outer integral is

.. math::

    \int_{x=-1}^{1} 2 x \sqrt{1-x^2} \ dx 


    = -(1-x^2)^{3/2} \ \bigg |_{-1}^1 = 0 

The area is :math:`\pi` but zero times :math:`1/\pi` is still zero.  And I suppose it is not a surprise that the average value of :math:`x` over a circle centered at :math:`0` is just :math:`0`.

+++++++
Example
+++++++

The reason I bring this up is a problem in Varberg that has an easy solution and a hard solution.  We've done part of the easy solution here, and the reason I know this is Auroux shows the answer.  Varberg does only the hard calculation, which is a little weird.

.. image:: /figs/Varberg17-12.png
   :scale: 50 %

The diagram shows the unit circle at the origin in blue with an inset missing circle in white.  The missing circle has radius :math:`1/2` and is centered at :math:`1/2,0`.  The problem is to find the average value of the function :math:`x` over the blue region.

We've just finished showing that the average value of :math:`x` over the unit circle is zero.  However, :math:`\bar{x}` over the small circle will not be zero, but :math:`1/2`.

We can use an important basic principle to solve this.  If we break a figure up into two (or more) parts, and compute an integral over each part, the parts should add up.

The integral we are computing is:

.. math::

    \iint_R x \ dA

so

.. math::

    \iint_{R} x \ dA = \iint_{w} x \ dA + \iint_{b} x \ dA

where :math:`b` is the blue region and :math:`w` is the white region.

Rearranging the general formula for average value slightly:

.. math::

    A \bar{x} = \iint_R x \ dA
    
where :math:`A` is the area of the region.

So:

.. math::

    A_{R} \bar{x}{}_{R} = A_w \bar{x}{}_w + A_b \bar{x}{}_b

We know that :math:`A \bar{x}` for the white region is :math:`\pi/8`, and that the same thing over the entire region is zero.  So we calculate that 

.. math::

    A_b \bar{x}{}_b = - \frac{\pi}{8}

Let's try to do the problem the way its done in Varberg.

The idea is to use polar coordinates.  It's really hard to see how you could possibly do it in Cartesian coordinates, except in the way that we already used them.  How do we describe the :math:`x`-dependence of the bounds on :math:`y`?  I suppose we could try, but lets go with polar.  We will integrate the top half of the circle, and we'll do it separately for the first and second quadrants.

.. math::

    \int \int x \ r \ dr \ d \theta 

    x = r \cos \theta 

    \int \int r \cos \theta \ r \ dr \ d \theta 

Pretty standard.  We will integrate with respect to :math:`\theta` last.  So, now our job is to figure out how what the lower limit is on :math:`r` as :math:`\theta` varies.  And I don't know how you would see it if you didn't know the answer, but it is just :math:`\cos \theta`.

We can check that this gives the correct lower limit on :math:`r` for the two extremes :math:`\theta = 0` and :math:`\theta = \pi/2`.  We'll come back to the issue of how this was found later.  Let's calculate:

.. math::

    \int_0^{\pi/2} \int_{\cos \theta}^{1} r \cos \theta \ r \ dr \ d \theta 

The inner integral is

.. math::

    \frac{r^3}{3} \cos \theta \ \bigg |_{\cos \theta}^{1} 

So the outer integral is then

.. math::

    \frac{1}{3} \int_0^{\pi/2} \cos \theta - \cos^4 \theta  \ d \theta 

So we will have an outside factor of :math:`1/3` and :math:`\sin \theta` between :math:`0` and :math:`\pi/2`, which is just 1, but we have to deal with the fourth power of the cosine.  Yecch...  Recall the double-angle formula:

.. math::

    \cos^2 s = \frac{1}{2} (1 + \cos 2s) 


    \cos^4 s = \frac{1}{4} (1 + \cos 2s)^2 


    = \frac{1}{4} (1 + 2 \cos 2s + \cos^2 2s)

Substitute :math:`t = 2s`

.. math::

    \cos^2 2s = \cos^2 t = \frac{1}{2} (1 + \cos 2t) 

    = \frac{1}{2} (1 + \cos 4s) 

Substitute back to the previous version

.. math::

    \frac{1}{4} (1 + 2 \cos 2s + \cos^2 2s) 

    = \frac{1}{4} (1 + 2 \cos 2s + \frac{1}{2} (1 + \cos 4s)) 


Rearrange slightly

.. math::

    = \frac{3}{8} + \frac{1}{2} \cos 2s + \frac{1}{8} \cos 4s 

Substitute :math:`\theta`, integrate and get

.. math::

    = \frac{3}{8}\theta + \sin 2 \theta + \frac{1}{2} \sin 4 \theta 

With limits of :math:`\theta = 0 \rightarrow \pi/2` we have only the first term and that one only at the upper limit

.. math::

    = \frac{3}{16} \pi 


Combine it with the rest of the integral to obtain

.. math::

    \frac{1}{3}(1 - \frac{3}{16} \pi ) 

Now, on to the second quadrant.

.. math::

    \int_{\pi/2}^{\pi} \int_{0}^{1} r \cos \theta \ r \ dr \ d \theta 

The inner integral is

.. math::

    \frac{1}{3} r^3 \cos \theta \ \bigg |_0^1  

    = \frac{1}{3} \cos \theta 

And the outer integral is then

.. math::

    \frac{1}{3}  \int_{\pi/2}^{\pi} \cos \theta \ d \theta 

which is just :math:`-1/3`.  So finally, we add them up:

.. math::

    \frac{1}{3}(1 - \frac{3}{16} \pi ) - \frac{1}{3} = - \frac{\pi}{16} 

Recall that we integrated only the top half of the figure, so multiply by :math:`2` to obtain the same answer that we had much more simply before!

=======
Insight
=======

The part I like about this problem is seeing the limits on :math:`r`.  Varberg do not give a clue about this.

The equation of a circle in polar coordinates is given as

.. math::

    r = a \cos \theta + b \sin \theta 

where :math:`(a/2,b/2)` is the center of the circle.  Thus our small circle has the equation

.. math::

    r = \cos \theta 

How to check that?  Well, we can convert from polar to Cartesian like this:

.. math::

    x = r \cos \theta 

    x = r^2 = x^2 + y^2 

    x^2 - x + y^2 = 0 


Complete the square:

.. math::

    x^2 - x + \frac{1}{4} + y^2 = \frac{1}{4} 

    (x - \frac{1}{2})^2 + y^2 = \frac{1}{4} 

This is indeed our circle.

So we can think of this as having :math:`\theta` in sync for the two circles.  As we advance the parameter for the large circle, we can find the position of :math:`r` (where the point is with respect to the origin), at the same value of :math:`\theta` for the small circle.  At least, that's how it seems to me.

We have to remember that for an off-center circle (not at the origin) in polar coordinates the :math:`r` parameter is still with respect to the origin, rather than with respect to the center of the circle.
