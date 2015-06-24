.. _stovepipe:

#########
Stovepipe
#########

I came across an interesting problem in a chapter of Strogatz's *The Joy Of x*.  He calls it the stovepipe problem.  We want to find the volume of the region formed from the intersection of two cylinders (of equal radius), that meet at right angles.

.. image:: /figs/stovepipe1.png
   :scale: 50 %

I really couldn't visualize it, but he told me that the horizontal cross sections of this solid are squares, and gave a picture.

.. image:: /figs/stovepipe2.png
   :scale: 50 %

and it makes sense, if you imagine cutting through a potato with a cylindrical bore, then repeating at right angles.  At each level, the side is formed by cutting along the edge of the cylinder, hence the opposite sides are parallel.  And since the two cuts use the same cylinder, all :math:`4` sides at any particular height are equal, giving a square.

So our problem is to find the length of the side at each value of the height.  We deal with the upper half of the solid, for simplicity.  If you draw a sketch of the vertical cross-section, at each distance :math:`h` from the base of the solid, extending up, the remainder of the height down to the base is :math:`R-h`, and the half-length of the side is :math:`s/2 = \sqrt{R^2 - h^2}`.

The volume is obtained by adding up all these slices

.. math::

    V = \int_0^R 2  \sqrt{R^2 -h^2} \ dh 

Let's simplify the problem further (for the moment) by dealing with the case where :math:`R=1`  We need the integral

.. math::

    \int \sqrt{1-h^2} \ dh 

I certainly didn't know that off the top of my head.

\section*{a new integral}

You know that the derivative of the inverse sine is:

.. math::

    \frac{d}{dx} \sin^{-1} x  = \frac{1}{\sqrt{1-x^2}} 

(The way we get this:  let :math:`x = x/1 = \sin t`, then :math:`t = \sin^{-1} x` and :math:`\sqrt{1-x^2} = \cos t` and

.. math::

    \frac{dx}{dt} = \cos t = \sqrt{1-x^2} 

    \frac{dt}{dx} = \frac{1}{\cos t} = \frac{1}{\sqrt{1-x^2}} 

Now, how about

.. math::

    \int \sqrt{1-x^2} \ dx 

It's the same term, but it's on top rather than in the denominator.  What happens if we multiply top and bottom by :math:`\sqrt{1-x^2}`?

.. math::

    = \int \frac{1-x^2}{\sqrt{1-x^2}} \ dx 

    = \int \frac{1}{\sqrt{1-x^2}} \ dx + \int \frac{-x^2}{\sqrt{1-x^2}} \ dx 

Is this progress?  Now we have an extra power of :math:`x` in the term on the right.  Since we know we can integrate the square root using one power of :math:`x`, and taking the derivative of the remaining factor of :math:`x` will make it go away, it sounds like we should try integration by parts

.. math::

    \int u \ dv = uv - \int v \ du 

Let :math:`x = u`, then :math:`dx = du`.  And let :math:`-x/\sqrt{1-x^2} \ dx` = :math:`dv`.  Then

.. math::

    v = \sqrt{1-x^2} 

So the integral of this part is

.. math::

    \int \frac{-x^2}{\sqrt{1-x^2}} \ dx = x \sqrt{1-x^2} - \int  \sqrt{1-x^2} \ dx  

We still can't integrate the term on the right, but now, we have two of them!  Putting it all together:

.. math::

    \int \sqrt{1-x^2} \ dx = \int \frac{1}{\sqrt{1-x^2}} \ dx + x \sqrt{1-x^2} - \int \sqrt{1-x^2} \ dx  

So

.. math::

    2 \int \sqrt{1-x^2} \ dx =   \sin^{-1} x + x \sqrt{1-x^2} 

    \int \sqrt{1-x^2} \ dx = \frac{1}{2}  \sin^{-1} x + \frac{x}{2} \sqrt{1-x^2}  

One more thing.  Suppose we have

.. math::

    \int \sqrt{a^2-x^2} \ dx 

We can pull out the :math:`a` as follows

.. math::

    = a \int \sqrt{1- (\frac{x}{a})^2} \ dx 

Let :math:`u = x/a`, then :math:`a \ du = dx` and we have

.. math::

    = a^2 \int \sqrt{1- u^2} \ du 

So the final answer is

.. math::

    \int \sqrt{a^2-x^2} \ dx = \frac{a^2}{2} \ [ \ \sin^{-1} \frac{x}{a} + \frac{x}{a} \sqrt{1-(\frac{x}{a})^2} \ ] 

which can be rearranged slightly

.. math::

    = \frac{a^2}{2} \ \sin^{-1} \frac{x}{a} + \frac{x}{2} \sqrt{a^2-x^2}  

I'll leave it to you to figure out the whole volume for the general case with radius :math:`R`.
