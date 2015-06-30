.. _Auroux22:

########################
Auroux:  Green's Theorem
########################

The curl of :math:`\mathbf{F}` is:

.. math::

    curl(\mathbf{F}) = N_x - M_y

for :math:`\mathbf{F}=\ <M,N>`.  It measures how far the field is from being conservative:  i.e. how much net work must be done to move around a closed curve in the field.

Green's Theorem is

.. math::

    \oint_C \mathbf{\mathbf{F}} \cdot \mathbf{\mathbf{dr}} = \int \int_R curl(\mathbf{F}) \ dA

.. math::

    \oint_C M \ dx + N \ dy  = \int \int_R (N_x - M_y) \ dA


where :math:`\oint` is an integral over a *closed path*, defined as traveling in a ccw direction.  The left-hand side "lives on the curve," whereas the right-hand side "lives over the whole region."

He gives an example where this is very useful.  Suppose

.. math::

    M = ye^{-x}, \ \ N=\frac{1}{2}x^2 - e^{-x} 

and our curve is a shifted unit circle, centered at :math:`(2,0)`, so :math:`x=2 + cos\theta` and :math:`y=sin\theta`.  This is trouble to parametrize, because of :math:`e^{-x}`.  Instead do

.. math::

    \int \int_R (N_x - M_y) dA 

    M = ye^{-x}, \ \ M_y = e^{-x} 

    N=\frac{1}{2}x^2 - e^{-x}, \ \ N_x = x + e^{-x} 

    \int \int_R x dA 

From lecture 21, we had :math:`\bar{x} = (1/Area) \int \int x dA`

.. math::

    \int \int_R x \ dA = Area(R) \ \bar{x} = 2 \pi

Alternatively, we could calculate this directly

.. math::

    x = 2 + cos\theta, \ \ dx = -2 sin\theta \ d\theta 

    y = sin \theta, \ \ dy = cos\theta d\theta 

    \int \int_R x \ dA =  \int_{\theta=0}^{2\pi} \int_{r=0}^{r=1} (2 + cos\theta) \ r \ dr \ d\theta 

inner

.. math::

    (2 + cos\theta)\frac{r^2}{2} \ \bigg |_0^1 = 1 + \frac{1}{2}cos\theta 

outer

.. math::

    \int_{\theta=0}^{2\pi} (1 + \frac{1}{2}cos\theta) \ d\theta = (\theta + \frac{1}{2}sin \theta) \ \bigg |_0^{2\pi} =   2\pi 

==========
Derivation
==========

We will show that

.. math::

    \oint_C M \ dx = \int \int_R -M_y \ dA 

we look at the special case where N = 0, so there is only an x-component in the vector field.  but by symmetry

.. math::

    \oint_C N \ dy = \int \int_R N_x \ dA 

and the sum is then equivalent to the theorem.

Almost any complex curve (with some exceptions) can be decomposed into a set of regions, we do the integrals for each one, and the boundary curves between regions cancel.

.. image:: /figs/regions.png
   :scale: 50 %

So now, we start formally, to prove:

.. math::

    \oint_C M dx = \int \int_R -M_y \ dA 

For a vertically simple region, we have a total of four curves going around

.. image:: /figs/Auroux22b.png
   :scale: 50 %

but two of them are vertical and have :math:`dx=0`, the other two are

.. math::

    \oint_C M \ dx = \oint_{C1} M \ dx + \oint_{C2} M \ dx =\int_a^b M(x, f_1(x)) \ dx - \int_a^b M(x,f_2(x)) \ dx 

where :math:`f_1` is the lower curve and :math:`f_2` the upper one.  At each point along the curve, we have :math:`y=f(x)`, so we can evaluate what :math:`M(x,y)` is at that point and then integrate with respect to :math:`x`.  Notice that we have switched the bounds on the second integral, and added a minus sign.

Leaving that aside, now look at the right-hand side in the theorem, the integral over the region

.. math::

    \int \int_R -M_y \ dA = \int \int_R -M_y \ dy \ dx 
    
    = - \int \int_R M_y \ dy \ dx

where

.. math::

    M_y = \frac{\partial M}{\partial y}

so

.. math::

    - \int_{x=a}^{x=b} \int_{f_1(x)}^{f_2(x)} \frac{\partial M}{\partial y} \ dy \ dx 

but

.. math::

    \frac{\partial M}{\partial y} \ dy = M 

so (remembering the minus sign) the inner integral is just

.. math::

    \int_{f_1(x)}^{f_2(x)} M dy = M(x, f_2(x)) - M(x, f_1(x)) 

and the outer integral is

.. math::

    - \int_a^b \ [ \ M(x, f_2(x)) - M(x, f_1(x)) \ ] \ dx 

but that is the same as what we had above (taking account of sign).  That completes the proof.
