.. _change-vars:

###################
Change of variables
###################

We usually pick a coordinate system with axes perpendicular, scaled in the same units, with the label :math:`x` for horizontal and :math:`y` for vertical.  But for some problems, it can be useful to change the coordinate system.  There are a number of different possible ways to do this, as we'll see.  Importantly, there are some basic rules to follow to insure that the areas determined in the new coordinate system match up with those in the standard one.

Probably the simplest example of this is a linear stretching of one dimension, say, the :math:`x`-axis.  Let's think about the problem of determining the area of the rectangle with one corner at :math:`(0,0)` and the other corner at :math:`(2,1)`.  Although it seems like overkill, we're going to use (single variable) calculus to do it.  The upper edge is :math:`y = f(x) = 1`.

.. math::

    A = \int_{x=0}^{x=2} f(x)\ dx 
    
    = \int_0^2 1\ dx = x  \ \bigg |_{0}^{2} = 2 


Now, let us define a new variable :math:`u` which is exchanged at a rate of 2 :math:`u`'s for every :math:`x`.  (If :math:`x=1` then :math:`u=2`, while if :math:`x=2` then :math:`u=4`, and so on).

.. math::

    u = 2x 

We take the exact same shape, (with no change in the area), but change the horizontal coordinate system to be defined in terms of :math:`u`.  The point :math:`(2,1)` becomes the point :math:`(4,1)` in the new coordinate system.  So we write

.. math::

    A = \int_{u=0}^{u=4} f(u)\ du  

(This is wrong, but bear with me).  You see we have adjusted the limits of integration, since before we had the upper limit of :math:`x=2`, now we have the upper limit of :math:`u=4`.  That part is correct.  :math:`f(x)` is a constant, so everywhere :math:`f(x) = f(u) = 1` no matter the value of :math:`x` (or :math:`u`).  Our mistake is that :math:`du \neq dx`.

.. math::

    du = 2\ dx 

    \frac{1}{2} du = dx 

so we substitute

.. math::

    A = \int_{x=0}^{x=2} f(x)\ dx 
    
    =  \int_{u=0}^{u=4} f(u)\ \frac{1}{2}du 
    
    =  \frac{1}{2} \int_0^4 f(u)\ du 
    
    = \frac{1}{2} \int_0^4 1\ du 
    
    =  \frac{1}{2} \times 4 = 2 

which is correct.

We can do the very same problem in an even more complicated way, using multi-variable calculus.  Above, we imagine that what we are doing is slicing the area vertically into many slices with tiny width :math:`dx` and height :math:`f(x)` and adding all these together.  We can also imagine that we divide the area up into many little boxes of :math:`dA` and do the summation this way:

.. math::

    A = \iint\limits_{R} 1 \ dA 

The little boxes of area :math:`dA` have width :math:`dx` and height :math:`dy`.

.. math::

    A = \iint\limits_{R} 1 \ dA 
    
    =   \int_{y=0}^{y=1} \int_{x=0}^{x=2} 1 \ dx \ dy  

We evaluate the inner integral first, keeping :math:`y` constant.

.. math::

    = \int_{y=0}^{y=1}  x  \ \bigg |_{0}^{2} \ \ \ dy  

    = \int_{y=0}^{y=1}  2 \ dy  
    
    = 2y   \ \bigg |_{0}^{1} = 2  

(The real advantage of this is that we can substitute another function for :math:`f(x,y) = 1`---see the Center of Mass write-up).  I introduce the two variable method as a way of approaching the next two problems.

=======
Ellipse
=======

Let's think about a standard ellipse

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 

Following the example above, we could think about trying to compute the area of this ellipse as follows

.. math::

    A = \iint\limits_{R} 1 \ dA = \iint\limits_{R} 1 \ dx \ dy 

The problem is that we do not know how to specify the region, at least, not simply.  However, a little trick can make that problem go away!

We will change both the horizontal and vertical dimensions by a constant factor.  We compress (well, the opposite of stretching) :math:`x` by the factor :math:`1/a` and similarly compress :math:`y` by the factor :math:`1/b`.  We make a change of variables

.. math::

    x = au

    y = bv 

    dx = a\ du 

    dy = b\ dv 

So

.. math::

    dx \ dy = ab \ du \ dv 

Substituting

.. math::

    \frac{(au)^2}{a^2} + \frac{(bv)^2}{b^2} = u^2 + v^2 = 1

The substitution has converted the ellipse into a circle of radius :math:`1` and area :math:`A = \pi`.

and

.. math::

    A = \iint\limits_{R} 1 \ dx \ dy =  \iint\limits_{R} ab \ du \ dv = ab \iint\limits_{R} 1 \ du \ dv 

Now, we know the area of the region in :math:`u,v` coordinates, it is a circle of radius :math:`1` and its area is just equal to :math:`\pi`.  So finally

.. math::

    A = ab \iint\limits_{R} 1 \ du \ dv = \pi a b 

This is a really simple, beautiful result.  The two :math:`r`'s in the formula :math:`A= \pi r^2` become :math:`a \times b`.  Both dimensions make equivalent contributions to the area, as we'd expect.

The more formal way to do this is to compute what's called the Jacobian.  It gives the ratio between areas determined in two different coordinate systems.  We take the partial derivative of :math:`x` with respect to :math:`u` and :math:`v`, and similarly for :math:`y`.

.. math::

    x_u = a 

    x_v = 0 

    y_u = 0 

    y_v = b 

The two partials (:math:`x_v` and :math:`y_u`) are zero because :math:`x` does not depend on :math:`v` and  :math:`y` does not depend on :math:`u`.

We evaluate the determinant of this matrix:

.. math::

    J =
    \begin{vmatrix}
    x_u & x_v \\
    y_u & y_v
    \end{vmatrix} =
    \begin{vmatrix}
    a & 0 \\
    0 & b
    \end{vmatrix} 
    =ab


And that's the factor for converting between the two coordinate systems.

Sometimes the Jacobian is written as

.. math::

    J =
    \begin{vmatrix}
    x_u & y_u \\
    x_v & y_v
    \end{vmatrix}


but this doesn't change anything, because :math:`det(A) = det(A^T)`.

To summarize:

.. math::

    dx \ dy = J \ du \ dv 

where

:math:`J` is computed as described.

======
Circle
======

Another simple example is to find the area of a circle of radius :math:`a`.  In terms of :math:`x` and :math:`y` we had previously

.. math::

    \iint\limits_{R}  \ dA = \int_{x=0}^{x=a} \int_{y=0}^{y=\sqrt{a^2-x^2}} \ dy \ dx 
    
    = \int_{x=0}^{x=a} \sqrt{a^2-x^2}  \ dx 

This integral can be computed by doing a trig substitution, but there is an easier way, and that is to change to polar coordinates.  A naive attempt is

.. math::

    \iint\limits_{R}  \ dA = \int_{\theta=0}^{\theta=2 \pi} \int_{r=0}^{r=a} \ dr \ d \theta 
    
    = \int_{\theta=0}^{\theta=2 \pi} a \ d \theta = 2 \pi a 

Obviously, this is wrong.

What happened is that the area element for a little bit of area :math:`dA` has an extra factor of :math:`r`:

.. math::

    dA = dx \ dy = r \ dr \ d \theta 

.. image:: /figs/polararea.png
   :scale: 50 %

As Strang says "areas always come from multiplying two lengths, and :math:`d\theta` is not a length."  He goes on to say that a wedge has area

.. math::

    A = \frac{1}{2} r^2 \Delta \theta 

The difference between wedges is :math:`\Delta A`, and centering the change :math:`\Delta r` at :math:`r` we have:

.. math::

    \Delta A = \frac{1}{2}(r + \frac{\Delta r}{2})^2 \Delta \theta - \frac{1}{2}(r - \frac{\Delta r}{2})^2 \Delta \theta 

    = \frac{1}{2}(r^2 + r \Delta r + \frac{\Delta r^2}{4}) \Delta \theta - \frac{1}{2}(r^2 - r \Delta r + \frac{\Delta r^2}{4}) \Delta \theta 

Neglecting the small term :math:`\Delta r^2`:

.. math::

    \Delta A =  r \Delta r \Delta \theta 

The length of the curvy segment of arc depends on how far out we are on the radius.

.. math::

    \iint\limits_{R}  \ dA = \int_{\theta=0}^{\theta=2 \pi} \int_{r=0}^{r=a} \ r \ dr \ d \theta 
    
    = \int_{\theta=0}^{\theta=2 \pi} \frac{1}{2}a^2 \ d \theta = \pi a^2 

The Jacobian is done like this:

.. math::

    x = r \cos \theta, \ \ y = r \sin \theta 

For convenience I'll define

.. math::

    x_r = \frac{\partial x}{\partial r} = \cos \theta
    
    x_{\theta} = \frac{\partial x}{\partial \theta} = -r \sin \ \theta 

and similarly for :math:`y`.  Then

.. math::

    J =
    \begin{vmatrix}
    x_r & x_{\theta} \\
    y_r & y_{\theta}
    \end{vmatrix} =
    \begin{vmatrix}
    \cos \theta & -r \sin \theta \\
    \sin \theta & r \cos \theta
    \end{vmatrix} 
    = r (\cos^2\ \theta + \sin^2 \theta) = r

This is the factor for the ratio of areas under the two systems, and that's why we have :math:`r\ dr \ d\theta` in the integral.  Notice that when we took the partial derivatives, they were partials of :math:`x,y` with respect to :math:`r,\theta`, and we end up multiplying :math:`dr \ d\theta` by J.

==============
General method
==============

Suppose we wish to determine an area by integration and we're working with the unit square :math:`x=0 \to x=1` and :math:`y=0 \to y=1`, sometimes written as :math:`[\ 0,1\ ] \times [\ 0,1\ ]`.  The area is clearly just :math:`1`.  Now we want to make a change of variables for some reason (to work on a function that's easier to deal with, or because we have some weird bounds in our problem).

.. math::

    u = 3x-2y , \ \ v = x + y 

We can figure out the "exchange rate" by tracing out the parallelogram formed by this linear transformation

.. math::

    & (0,0) \to (0,0) \\
    & (0,1) \to (3,1) \\
    & (1,1) \to (1,2) \\
    & (0,1) \to (-2,1)

If we think of the vectors :math:`<3,1>` and :math:`<-2,1>`, the area of the parallelogram formed by these vectors is given by the determinant

.. math::

    \begin{vmatrix}
    3 & -2 \\
    1 & \ \ 1
    \end{vmatrix} = 5

The other way to do this calculation is (as we've been doing)

.. math::

    u_x = 3 

    u_y = -2 

    v_x = 1 

    v_y = 1 

The Jacobian

.. math::

    J =
    \begin{vmatrix}
    u_x & u_y \\
    v_x & v_y
    \end{vmatrix} =
    \begin{vmatrix}
    3 & -2 \\
    1 & \ \ 1
    \end{vmatrix}

    = 3 - (-2) = 5

Or more simply

.. math::

    J = u_x v_y - u_y v_x = 3  - (-2) = 5 

And again, since we took the derivatives with respect to :math:`x` and :math:`y`, we multiply :math:`dx \ dy` by :math:`J`.

Each element of the area determined in :math:`uv` units is worth :math:`5` of an element in :math:`xy` units.

.. math::

    5 \iint\limits_{R}  f(x,y) \ dx \ dy = \iint\limits_{R}  f(u,v) \ du \ dv 

    du \ dv = J \ dx \ dy

To say the above one more time in slightly different language, we have

.. math::

    u = u(x,y) 

    v = v(x,y) 

If we change :math:`x` by a little bit :math:`\Delta x` and :math:`y` by a little bit :math:`\Delta y`, by how much do :math:`u` and :math:`v` change?

The linear approximation is

.. math::

    \Delta u = u_x \Delta x + u_y \Delta y 

    \Delta v = v_x \Delta x + v_y \Delta y 

So for :math:`\Delta x = 1`, the vector :math:`<1,0>` becomes

.. math::

    \ <u_x ,v_x> 

and :math:`<0,1>` becomes

.. math::

    \ <u_y ,v_y> 

and the area of the parallelogram formed by these two vectors (the area in :math:`uv`-coordinates) is the absolute value of the cross product (think of them as lying in the plane, so there is only one term)

.. math::

    <u_x ,v_x> \ \times  <u_y ,v_y > 

    J = u_x v_y - u_y v_x 

So for each unit :math:`dx \ dy` we get :math:`du \ dv = J \ dx \ dy` in the :math:`uv`-coordinate system.

==============
Tilted ellipse
==============

Here is the equation of an ellipse, although that may be hard to recognize at first.

.. math::

    x^2 + 4xy + 13y^2 = 16 

If you remember (or look up) the formula

.. math::

    Ax^2 + Bxy + Cy^2 + Dx + Ey + F = 0 

    A,B,C = 1,4,13 

The discriminant is

.. math::

    B^2 - 4AC = 16 - 52 = -36 < 0 

Since it's :math:`< 0`, this is an ellipse.  Or we could just get Grapher to plot it

.. image:: /figs/tilted_ellipse.png
   :scale: 50 %

If we knew the angle, and there is a method for that, we could rotate to a new coordinate system and just compute the area as :math:`\pi ab`.  

However, there is another way which I think is easier.  We "complete the square" to remove the term which "mixes" :math:`x` and :math:`y`.  Since

.. math::

    (x + 2y)^2 = x^2 + 4xy + 4y^2 

Our equation is transformed as follows

.. math::

    x^2 + 4xy + 13y^2 = 16 

    (x + 2y)^2 + 9y^2 = 16 

We do a substitution almost like before, but modified:

.. math::

    u = x + 2y 

    v = 3y 

so now we have

.. math::

    u^2 + v^2 = 16 

This is a circle of radius :math:`4` and area :math:`16\pi`.

Now we just need the Jacobian:

.. math::

    u_x = 1 

    u_y = 2 

    v_x = 0 

    v_y = 3 

    J =
    \begin{vmatrix}
    u_x & u_y \\
    v_x & v_y
    \end{vmatrix} =
    \begin{vmatrix}
    1 & 2 \\
    0 & 3
    \end{vmatrix}
    = 3

.. math::

    du \ dv = 3 \ dx \ dy 

When we took the partial derivatives, they were partials of :math:`u,v` with respect to :math:`x,y`, so we end up multiplying :math:`dx \ dy` by J.

.. math::

    \frac{1}{3} du \ dv = dx \ dy 

We need to multiply the area by this factor to give a final answer of :math:`16\pi/3`.

=================
Varberg's example
=================

The next example is from Varberg, 17.16.

.. image:: /figs/Varberg-17-16.png
   :scale: 50 %

We have the lines :math:`x=y` and :math:`x=2y` and the curves :math:`xy=1` and :math:`xy=5`.  Looks like :math:`xy` would be a good variable to have so

.. math::

    u = \frac{x}{y} 

    v = xy 

These suggestions come from Varberg, not me.  :)  The boundaries of the region are just :math:`u = 1 \rightarrow u = 2` and :math:`v = 1 \rightarrow v = 5`.

Rearranging:

.. math::

    x = uy 

    x = \frac{v}{y} 

    x^2 = xx = uy \ \frac{v}{y} =  uv 

For the Jacobian, it is important to solve for :math:`x,y` in terms of :math:`u,v`, and not the other way around, so that we'll have terms containing :math:`u` and :math:`v` in the final integral.

.. math::

    x = \sqrt{uv} 

    y^2 = \frac{x}{u} \frac{v}{x} = \frac{v}{u} 

    y = \sqrt{\frac{v}{u}} 

So

.. math::

    x_u = \frac{1}{2} \sqrt{\frac{v}{u}} 

    x_v =  \frac{1}{2} \sqrt{\frac{u}{v}} 

    y_u =  -\frac{1}{2u} \sqrt{\frac{v}{u}}

    y_v = \frac{1}{2} \sqrt{\frac{1}{uv}} 

The Jacobian is then

.. math::

    x_u y_v - x_v y_u 

    \frac{1}{2} \sqrt{\frac{v}{u}} \ \frac{1}{2} \sqrt{\frac{1}{uv}} + \frac{1}{2} \sqrt{\frac{u}{v}} \  \frac{1}{2u} \sqrt{\frac{v}{u}} 

    = \frac{1}{4u} + \frac{1}{4u} = \frac{1}{2u} 

The area is

.. math::

    A = \iint\limits_{R} 1 \ dx \ dy 
    
    =  \iint\limits_{R} \frac{1}{2u}  \ du \ dv 

    = \int_{u=1}^{2} \ \int_{v=1}^{5} \frac{1}{2u}  \ dv \ du 

    = 2 \int_{u=1}^{2} \ \frac{1}{u} \ du 
    
    = 2 \ln 2 

================================
Even weirder example from Auroux
================================

Suppose we have

.. math::

    \int_{y=0}^1 \int_{x=0}^1 x^2 y \ dx \ dy 

For some strange reason we've decided that we're going to change to

.. math::

    u = x, \ \ v = xy 

    u_x = 1, \ \ u_y = 0, \ \ v_x = y, \ \ v_y = x 

    J =
    \begin{vmatrix}
    1 & 0 \\
    y & x
    \end{vmatrix} = x

.. math::

    du \ dv = x \ dx \ dy 

    \iint\ xy \ x \ dx \ dy =  \iint\ v \ du \ dv  

That looks OK, but what are the limits?

.. image:: /figs/changevar1.png
   :scale: 50 %

The first integral is with :math:`v` constant.  That means :math:`xy=v` is a constant, so we have different curves :math:`xy = const` (i.e. hyperobolas) between some limits.  The slices look like those in the figure above.

We enter our region from the top

.. math::

    y= 1 \Longrightarrow u = x, v = xy = x = u 

We leave the region on the side

.. math::

    x= 1 \Longrightarrow u = 1 

    \int \int_{u=v}^{u=1} v \ du \ dv 

The smallest value of :math:`v` is

.. math::

    x = 0 \Longrightarrow v = 0 

The largest value of :math:`v` is

.. math::

    x = 1, y = 1 \Longrightarrow v = 1 

    \int_{v=0}^{v=1} \int_{u=v}^{u=1} v \ du \ dv 

The inner integral is

.. math::

    \int_{u=v}^{u=1} v \ du = uv \ \bigg |_{u=v}^{u=1} = v - v^2 

and the outer integral is

.. math::

    \int_{v=0}^{v=1} v - v^2 \ dv = \frac{1}{2}v^2 - \frac{1}{3}v^3 \ \bigg |_{0}^{1} 
    
    = \frac{1}{2} - \frac{1}{3} = \frac{1}{6} 

We may have some doubt about the answer, so going back to what we started with and doing the integral we have

.. math::

    \int_{y=0}^1 \int_{x=0}^1 x^2 y \ dx \ dy 

The inner integral is

.. math::

    \int_{x=0}^1 x^2 y \ dx = \frac{1}{3}x^3y \ \bigg |_{0}^{1} = \frac{1}{3}y  

and the outer integral is

.. math::

    \int_{y=0}^1  \frac{1}{3}y \ dy = \frac{1}{6}y^2 \ \bigg |_{0}^{1} = \frac{1}{6}  

which agrees.
