.. _Auroux23:

################
Auroux 23:  Flux
################

To review, we compute work as

.. math::

    W = \int_C \mathbf{F} \cdot d\mathbf{r} 

As a shorthand we say that

.. math::

    {W = \int_C M \ dx + N \ dy} 

We can get from one to the other by saying that :math:`\mathbf{F} = \langle M,N \rangle` and :math:`d \mathbf{r} = \langle dx, dy \rangle`, or by deconstructing :math:`d\mathbf{r}` (useful when we start with a parametrized curve):

.. math::

    d\mathbf{r} = \frac{d\mathbf{r}}{dt} \ dt = \mathbf{v} \ dt 
    
    = \langle \frac{dx}{dt}, \frac{dx}{dt} \rangle \ dt
    
    = \langle dx, dy \rangle
    
    = \hat{\mathbf{T}} \ \frac{ds}{dt} \ dt

These are all equivalent.  For example in the first one we have velocity times time, and in the last one we have speed, in the direction of the unit vector tangent to the curve, i.e. where we are pointing.  That's the same thing as velocity, times the time.

where

.. math::

    \frac{d\mathbf{r}}{dt} = \ \langle \frac{dx}{dt},\frac{dy}{dt} \rangle 

Hence, if we have :math:`\mathbf{F} =  \langle M,N \rangle` then

.. math::

    W = \int_C \mathbf{F} \cdot \frac{d\mathbf{r}}{dt} \ dt 
    
    = \int_C \langle M,N \rangle \cdot \langle \frac{dx}{dt},\frac{dy}{dt} \rangle \ dt 
    
    = \int_C M \ dx + N \ dy

=======
Example
=======

If

.. math::

    \mathbf{F} =  \langle -y,x \rangle 

    x = t, \ \ y = t^2 

we obtain

.. math::

    W = \int_C \langle M,N \rangle \cdot \langle \frac{dx}{dt},\frac{dy}{dt} \rangle \ dt 

    = \int_C \langle -t^2,t \rangle \cdot \langle 1,2t \rangle \ dt 

    = \int_C t^2 = \frac{1}{3}t^3 \ \bigg |_{P1}^{P2}  

====
Flux
====

In this write-up, we're concerned with flux, which also has a shorthand

.. math::

    \text{Flux} = \int_C -N dx + M dy 

We switched :math:`M` for :math:`N` and changed signs on the term with :math:`dx`.

(When we get to :math:`\mathbb{R^3}` we will see another notation for flux and for curl).

Work is done by the component of the force in the direction of :math:`\hat{\mathbf{T}}`.  It's the "tail wind", if you will.  

Flux is the "cross-wind", it is the perpendicular component in the direction normal to the curve (:math:`\hat{\mathbf{n}}\perp \hat{\mathbf{T}}`).

.. math::

    \text{Flux} = \int_C \mathbf{F} \cdot \hat{\mathbf{n}} \ ds 

We'll show a derivation below.

=======
Example
=======

Sometimes we don't need to calculate!  Suppose

.. math::

    \mathbf{F} = \ \langle x,y \rangle

This is a *radial* field.  

Let :math:`C` be a circle of radius :math:`a` centered at the origin.  In this situation the formula with :math:`\hat{\mathbf{n}}` is useful.

.. math::

    \mathbf{F}  \cdot \hat{\mathbf{n}} = |F| |n| cos \theta 
    
    = |F| 
    
    = \sqrt{x^2 + y^2} = a 

So

.. math::

    \text{Flux} = \int_C \mathbf{F} \cdot \hat{\mathbf{n}} \ ds 

    = \int_C a \ ds = a \int_C \ ds 

    = a \ 2\pi a 

    = 2\pi a^2 

Note that :math:`\hat{\mathbf{n}}` is just :math:`\hat{\mathbf{T}}` rotated by :math:`90^\circ` cw.  (The convention is that the integral should be positive if we move along the curve with the region on our left).  

Now

.. math::

    d \mathbf{r} = \langle dx,dy \rangle 

    = \hat{\mathbf{T}} \ ds 

so

.. math::

    \hat{\mathbf{n}} \ ds =  \langle dy, -dx \rangle

We test for orthogonality in the usual way: 

.. math::
    
    \hat{\mathbf{T}} \ ds \cdot \hat{\mathbf{n}} \ ds
    
    = \langle dx , dy \rangle \cdot \langle dy, -dx \rangle = 0

and

.. math::

    \int_C \mathbf{F} \cdot \hat{\mathbf{n}} \ ds 

    = \int_C \langle M,N \rangle \cdot \langle \frac{dy}{dt},-\frac{dx}{dt} \rangle \ dt 

which we can try to remember as

.. math::

    = \int_C -N dx + M dy 

as shown above.

Reversing the sign of the :math:`x` component corresponds to counter-clockwise rotation, which is our convention.  :math:`\hat{\mathbf{T}}` rotated counter-clockwise 90 degrees is :math:`\hat{\mathbf{n}}`, which is the normal component coming out of a "simply connected region" as we go around the curve in the counter-clockwise direction.

===============
Green's theorem
===============

Our statement of the theorem was that

.. math::

    \int_C M \ dx + N \ dy = \int \int_R (N_x - M_y) \ dA

We can use the "del" notation to make this shorter

.. math::

    \int_C M \ dx + N \ dy = \int \int_R (N_x - M_y) \ dA 

    = \int \int_R \nabla \times \mathbf{F} \ dA

I will come back to that cross-product in a minute.  But :math:`N_x - M_y` is the curl of :math:`\mathbf{F}`.

Now we just switch letters!  Put :math:`-N` for :math:`M` and :math:`M` for :math:`N`

.. math::

    \int_C -N \ dx + M \ dy = \int \int_R (M_x + N_y) \ dA 
    
    =  \int \int_R \nabla \cdot \mathbf{F} \ dA

This is Green's Theorem for Flux.  The left-hand side is the Flux, the right-hand side is a way to calculate the same quantity using :math:`\nabla \cdot \mathbf{F}`

=======
Example
=======

Suppose :math:`\mathbf{F}= \  \langle x,y \rangle` and the curve is a circle of radius :math:`a`, but centered at :math:`(0,2)`.  So now parametrization gets a little trickier..

But notice that

.. math::

    \nabla \cdot \mathbf{F} = 2 

So we can calculate the Flux by using Green's Thm (for Flux).  It is just

.. math::

    \int \int_R \nabla \cdot \mathbf{F} \ dA = 2 \int \int_R dA = 2\pi a^2 

and this is true regardless of where the circle is.

========
Notation
========

So we have the symbol :math:`\nabla` which we use as an operator

.. math::

    \nabla = \frac{\partial}{\partial x}, \frac{\partial}{\partial y}, \frac{\partial}{\partial z} 

We have already used this in defining the *gradient* of :math:`f`

.. math::

    \nabla f = \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z} =  \langle f_x, f_y, f_z \rangle 

Now we introduce a dot product and cross product employing :math:`\nabla`.  The first is the divergence of :math:`\mathbf{F}`

.. math::

    \mathbf{F} = \  \langle P,Q,R \rangle 

    \nabla \cdot \mathbf{F} = P_x + Q_y + R_z 

And the second is the curl of :math:`\mathbf{F}`

.. math::

    \nabla \times \mathbf{F} 
    =
    \begin{vmatrix}
    \hat{i}  &  \hat{j} & \hat{k} \\
    \frac{\partial}{\partial x}  &  \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
    P  &  Q & R \\
    \end{vmatrix}

This determinant has three components

.. math::

    \langle (\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}), - (\frac{\partial R}{\partial x} - \frac{\partial P}{\partial z}), (\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}) \rangle
    
    = \langle R_y - Q_z, P_z - R_x, Q_x - P_y \rangle

What we have in Green's Theorem (with different letters, substitute N for Q and M for P), is a vector with only :math:`x` and :math:`y` components and hence only one of the terms.

.. math::

    = \langle 0, 0, Q_x - P_y \rangle = \langle 0, 0, N_x - M_y \rangle
    