.. _Schey-line-integrals:

##############
Schey Examples
##############

We've seen a couple different types of line integrals.  In one type, we are just finding the length of a curve.  Say we are in :math:`\mathbb{R^2}` and we have :math:`y = f(x)`.  Pythagoras gives us the conversion rate between a little piece of arc :math:`ds` and :math:`dx` and :math:`dy`:

.. math::

    ds^2 = dx^2 + dy^2 

which leads to 

.. math::

    ds = \sqrt{1 + f'\ ^2} \ dx

The second type is an integral to find the work done in moving along a curve, which is defined as

.. math::

    W = \int_C \mathbf{F} \cdot d \mathbf{r}

We take the component of the force that is the same direction as we are moving right now, *tangent* to the curve and add up the force times the distance for each small piece.

Here we need to express :math:`d \mathbf{r}` in terms of :math:`x` and :math:`y` (and ultimately in terms of a single parameter).

In simple problems, a good approach is to recognize that

.. math::

    d \mathbf{r} = \langle dx, dy \rangle

If :math:`\mathbf{F} = \langle M, N \rangle`, this means that the dot product is

.. math::

    \langle M, N \rangle \cdot \langle dx, dy \rangle = M \ dx + N \ dy

and the work is then:

.. math::

    W = \int_C \langle M, N \rangle \cdot \langle dx, dy \rangle 
    
    = \int_C M \ dx + N \ dy

We are by no means done, but we can see the way forward.  Now, we need to somehow parametrize the curve we are given, if it is not provided in that form.

+++++++++
Example 1
+++++++++

Suppose

.. math::

    \mathbf{F} = y \mathbf{\hat{i}} - x \mathbf{\hat{i}} 
    
    = \langle y, -x \rangle

And then if the curve is the triangle from

.. math::

    (0,0) \rightarrow (1,0) \rightarrow (0,1) \rightarrow (0,0)

For each segment of the path, we need to compute

.. math::

    \int_C M \ dx + N \ dy = \int_C y \ dx - x \ dy

How to parametrize?  No need to worry about it for :math:`C_1` since :math:`y = 0 = dy` and the work is zero.  Similarly the work is zero for the third segment because :math:`x = 0 = dx`.  

Only the second matters:  we go from :math:`(1,0) \rightarrow (0,1)`.  Let :math:`t = 0 \rightarrow 1` and

.. math::

    y = t
    
    x = 1 - t

To check the parametrization I just check the values at the endpoints and depend on linearity.  Then

.. math::

    W = \int_C y \ dx - x \ dy 
    
    = \int_0^1 t \ (-dt) - (1-t) \ dt
    
    = (- \frac{t^2}{2} - t + \frac{t^2}{2}) \ \bigg |_0^1
    
    = -1

+++++++++
Example 2
+++++++++

Suppose

.. math::

    \mathbf{F} = \langle x^2 , - xy \rangle
    
and the path is the arc of the quarter-circle in the first quadrant (moving from :math:`(1,0) \rightarrow (0,1)`).

In this case we parametrize in terms of :math:`\theta` or :math:`t`.  The standard equations are:

.. math::

    x = R \cos t
    
    y = R \sin t
    
    dx = - R \sin t \ dt
    
    dy = R \cos t \ dt
    
    t = 0 \rightarrow \pi/2

The work integral is, again:

.. math::

    W = \int_C M \ dx + N \ dy
    
    = \int_C x^2 \ dx - xy \ dy
    
    = \int_0^{\pi/2} (R^2 \cos^2 t) (-R \sin t \ dt) - (R^2 \sin t \cos t) (R \cos t \ dt)
    
    = 2 R^3 \int_0^{\pi/2} - \cos^2 t \sin t \ dt
    
    = 2 R^3 \frac{\cos^3}{3} \ \bigg |_0^{\pi/2}
    
    = - \frac{2}{3} R^3
