.. _Flux Space:

##########
Flux space
##########

By now you should be comfortable with Green's Theorem for work, in the plane.

.. math::

    \oint_C \mathbf{F} \cdot \mathbf{dr} = \oint_C \mathbf{F} \cdot \mathbf{\hat{t}} \ ds =  \iint\limits_{R}  curl(\mathbf{F}) \ dA 

Often :math:`curl \mathbf{F}` is written as :math:`\nabla \times \mathbf{F}`.  If

.. math::

    \mathbf{F} = \  \langle \  M, N \  \rangle

then we have the equivalent expression

.. math::

    \oint_C M \ dx + N \ dy  = \iint\limits_{R} (N_x - M_y) \ dA 

remembering that the integral on the left is a single integral, so we must eventually get :math:`x` in terms of :math:`y` or both in terms of :math:`t` to use the formula.  There is a great trick where if :math:`N_x = 1/2` and :math:`M_y = - 1/2` then the right-hand side is

.. math::

    \iint\limits_{R} (\frac{1}{2} - -\frac{1}{2}) \ dA = \iint\limits_{R} dA = A 

and this leads to a simple calculation of the area of an ellipse.

Sometimes, we can avoid a complicated line integral by converting it to the right-hand side.  And of course if :math:`\nabla \times \mathbf{F} = N_x-M_y = 0`, we are dealing with a conservative vector field and we just evaluate the potential at the end-points of the curve, obtaining zero for the example with a closed curve.

The second version of Green's Theorem involves the divergence of :math:`\mathbf{F}`

.. math::

    Flux =  \oint_C \mathbf{F} \cdot \mathbf{\hat{n}} \ ds = \iint\limits_{R} \nabla \cdot \mathbf{F} \ dx \ dy 

where

.. math::

    div(\mathbf{F}) = \nabla \cdot \mathbf{F} = M_x + N_y 
    
    = \frac{\partial M}{\partial x} + \frac{\partial N}{\partial y}


The term :math:`\mathbf{F} \cdot \mathbf{\hat{n}}\ ds` is the orthogonal counterpart (flow across the curve) of :math:`\mathbf{F} \cdot \mathbf{\hat{T}} \ ds = \mathbf{F} \cdot \mathbf{dr}`, the work done along :math:`C`.  :math:`\mathbf{n}` can be a little tricky to work with, but the point of this seems to be that we can convert the divergence (say, of a flow field) into a simpler calculation over the area of :math:`R`.  For reference

.. math::

    \mathbf{\hat{n}} = \frac{1}{| \mathbf{r}'(t) |} \  \langle \frac{dy}{dt},-\frac{dx}{dt}  \rangle 
    
Velocity is in the direction we're headed :math:`\mathbf{v} = \  \langle dx/dt,dy/dt \rangle`.  This vector is orthogonal to it (:math:`\mathbf{v} \cdot \mathbf{\hat{n}} = 0)`, and it's a unit vector.

========
In space
========

Moving on to the actual topic for this section, we start to think about space.  The flux of :math:`\mathbf{F}` across a surface :math:`S` is

.. math::

    Flux =   \iint\limits_{S}  \mathbf{F} \cdot \mathbf{\hat{n}} \ dS 

where :math:`\mathbf{\hat{n}}` is the unit normal to the surface.  Let's look more carefully at :math:`\mathbf{\hat{n}} \ dS`.  Back when we looked at parametrization of surfaces, we said that

.. math::

    dS = | \mathbf{r}_u \times \mathbf{r}_v | \ du \ dv 

but the unit normal to the surface is just

.. math::

    \mathbf{\hat{n}} = \frac{\mathbf{r}_u \times \mathbf{r}_v}{|\mathbf{r}_u \times \mathbf{r}_v|} 

so

.. math::

    \mathbf{\hat{n}} \ dS = \mathbf{r}_u \times \mathbf{r}_v \ du \ dv 

and

.. math::

    Flux =   \iint\limits_{S}  \mathbf{F} \cdot \mathbf{\hat{n}} \ dS =   \iint\limits_{S}  \mathbf{F} \cdot (\mathbf{r}_u \times \mathbf{r}_v) \ du \ dv 

=======
Example
=======

Suppose we have a unit sphere

.. math::

    x^2 + y^2 + z^2 = 1 

and :math:`\mathbf{F}= \  \langle x,y,z \rangle`.

The standard parametrization of the (unit) sphere is

.. math::

    \mathbf{r}(\phi, \theta) = \  \langle \sin \phi \cos \theta, \sin \phi \sin \theta, \cos \phi \rangle 

:math:`\mathbf{F}` is actually just the same.  The cross-product is

.. math::

    \mathbf{r}_{\phi} \times \mathbf{r}_{\theta}

where

.. math::

    \mathbf{r}_{\phi} = \langle  \cos \phi \cos \theta, \cos \phi \sin \theta, -\sin \phi \rangle 

and

.. math::

    \mathbf{r}_{\theta} = \langle  \sin \phi \sin \theta, \sin \phi \cos \theta, 0 \rangle

The cross-product is

.. math::

     \langle  -\sin^2 \phi \cos \theta, \sin^2 \phi \sin \theta, \sin \phi \cos \phi \rangle 

The dot product with :math:`\mathbf{F}` (with :math:`\mathbf{F}` expressed in spherical coordinates) is:

.. math::

    \sin \phi \cos \theta \sin^2 \phi \cos \theta +  \sin \phi \sin \theta \sin^2 \phi \sin \theta + \cos \phi \sin \phi \cos \phi 

    = \sin^3 \phi + \sin \phi \cos^2 \phi = \sin \phi 

So we have

.. math::

    \int_0^{2\pi} \int_0^{\pi}  \sin \phi \  d \phi \ d \theta = \int_0^{2\pi} 2 \ d \theta = 4 \pi 

==================
Divergence theorem
==================

There is an easier way to do this calculation!  It uses the divergence theorem in space, which states the following identity

.. math::

    flux =  \iint\limits_{S}  \mathbf{F} \cdot \mathbf{n} \ dS 
    
    = \iiint\limits_{V} \text{div} \ \mathbf{F} \ dV 
    
    = \iiint\limits_{V} \nabla \cdot \mathbf{F} \ dV 

Remember that

.. math::

    \mathbf{F}= \  \langle x,y,z \rangle 

    div(\mathbf{F} ) = \nabla \cdot \mathbf{F} = P_x + Q_y + R_z = 1 + 1 + 1 = 3 

So we have

.. math::

    = \iiint\limits_{V} 3 \ dV  = 3 V =  4 \pi 
