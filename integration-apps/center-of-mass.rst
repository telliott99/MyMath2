.. _Center of mass:

##############
Center of mass
##############

As you know, in single variable calculus we can interpret

.. math::

    \int_a^b f(x) dx 

as the area underneath the curve :math:`y=f(x)` between the lines :math:`x=a` and :math:`x=b` (our limits).  In multi-variable calculus we compute the double integral over the same region as follows

.. math::

    \int_{x=a}^{x=b} \int_{y=0}^{y=f(x)} dy \ dx =  \int_{x=a}^b y \bigg |_0^{f(x)}  \ dx = \int_a^b f(x) \ dx 

To be more general, we'd just say that we compute the double integral over the region :math:`R`

.. math::

    \iint\limits_{R} dx \ dy  

with the understanding that we can compute the inner integral with respect to either :math:`x` or :math:`y`, whichever is more convenient.

Another difference from the single-variable approach is that we can extend this approach by computing

.. math::

    \iint\limits_{R} g(x,y) \ dx \ dy  

Suppose, for example, that :math:`g(x,y)` is a function that gives the density of a flat object for each coordinate :math:`x,y`.  In this case we usually use the label :math:`\rho (x,y)`.  This integral gives the total mass of the object:

.. math::

    M = \iint\limits_{R} \rho (x,y) \ dx \ dy  

To find the center of mass we compute

.. math::

    M_x = \iint\limits_{R} \rho (x,y)\  y \ dx \ dy  

    M_y = \iint\limits_{R} \rho (x,y) \ x \ dx \ dy 

And then finally

.. math::

    \bar{x} = \frac{M_x}{M} 

    \bar{y} = \frac{M_y}{M} 

\vspace{5 mm}

Let's do a simple example.  Suppose our region is a rectangle with the origin as one corner and the point :math:`(1,2)` as the opposite corner.  It's just a 2D box of width :math:`1` and height :math:`2`.  And let's say our density function is :math:`\rho (x,y) = xy`.  Then

.. math::

    M = \iint\limits_{R} \rho (x,y) \ dx \ dy =  \int_{y=0}^{y=2} \int_{x=0}^{x=1} xy \ dx \ dy  

The inner integral is

.. math::

    \frac{1}{2} x^2 y \ \bigg |_0^{1} = \frac{1}{2} y 

and the rest is

.. math::

    M = \int_{y=0}^{y=2} \frac{1}{2} y \ dy = \frac{1}{4} y^2 \  \bigg |_0^{2} = 1 

Now

.. math::

    M_x =  \int_{y=0}^{y=2} \int_{x=0}^{x=1} xy^2 \ dx \ dy  

The inner integral is

.. math::

    \frac{1}{2} x^2 y^2 \ \bigg |_0^{1} = \frac{1}{2} y^2 

and the rest is

.. math::

    M_x  = \int_{y=0}^{y=2} \frac{1}{2} y^2 \ dy = \frac{1}{6} y^3 \  \bigg |_0^{2} = \frac{4}{3} 

Last, :math:`M_y` can be done in the same order

.. math::

    M_y =  \int_{y=0}^{y=2} \int_{x=0}^{x=1} x^2y \ dx \ dy  

The inner integral is

.. math::

    \frac{1}{3} x^3 y \ \bigg |_0^{1} = \frac{1}{3} y 

and the rest is

.. math::

    M_y  = \int_{y=0}^{y=2} \frac{1}{3} y \ dy = \frac{1}{6} y^2 \  \bigg |_0^{2} = \frac{2}{3} 

Thus our center of mass is at the point :math:`2/3,4/3`.  If it had made our lives easier, either integral could be computed with respect to :math:`y` before :math:`x`.

The answer makes sense.  The density increases as we go to the right and up, so the center of mass is offset from the geometric center in the same direction.
