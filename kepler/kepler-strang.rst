.. _kepler-strang:

######
Strang
######

Strang starts by deriving the unit vectors as we've seen before:

.. math::

    \mathbf{u_{r}} = \langle \cos \theta, \sin \theta \rangle
    
    \mathbf{u_{\theta}} = \langle -\sin \theta, \cos \theta \rangle
    
    \frac{d}{d \theta} \mathbf{u_{r}} = \mathbf{u_{\theta}}
    
    \frac{d}{d \theta} \mathbf{u_{\theta}} = - \mathbf{u_{r}}
    
then

.. math::

    \mathbf{r} = r \ \mathbf{u_{r}}
    
    \mathbf{v} = \frac{d}{dt} \mathbf{r} = r \frac{d \mathbf{u_{r}}}{dt} + \frac{dr}{dt} \mathbf{u_{r}}

but

.. math::

    \frac{d \mathbf{u_{r}}}{dt} = \frac{d  \mathbf{u_{r}}}{d\theta} \ \frac{d \theta}{dt} = \frac{d \theta}{dt} \ \mathbf{u_{\theta}}

so

.. math::
        
    \mathbf{v} = r \frac{d \theta}{dt} \ \mathbf{u_{\theta}} + \frac{dr}{dt} \mathbf{u_{r}}
    
=============
Cross-product
=============

As we've seen before, :math:`\mathbf{r} \times \mathbf{v}` is a constant:

.. math::

    \mathbf{r} \times \mathbf{v} = h
    
because its time-derivative is zero:

.. math::

    \frac{d}{dt} \ ( \mathbf{r} \times \mathbf{v} ) = \dot{\mathbf{r}} \times \mathbf{v} + \mathbf{r} \times \dot{\mathbf{v}} = 0

The first term is the velocity vector crossed with itself, and the second term is the radial vector crossed with the acceleration, which is in the minus :math:`\mathbf{r}` direction.

If we work out the terms of the cross-product:

.. math::

    | \mathbf{r} \times \mathbf{v} | = h
    
    = r \mathbf{u_{r}} \times (r \frac{d \theta}{dt} \ \mathbf{u_{\theta}} + \frac{dr}{dt} \mathbf{u_{r}})

the term with :math:`\mathbf{u_{r}} \times \mathbf{u_{r}}` is just zero so we end up with

.. math::

    = r^2 \frac{d \theta}{dt} \mathbf{u_{r}} \times \mathbf{u_{\theta}}

    h = r^2 \frac{d \theta}{dt}

And this constant is equal to (twice) the area swept out by an arc of radius :math:`r` times the angular distance :math:`r d \theta` in a small time.

============
Acceleration
============

Something else we've seen before is to compute the acceleration:

.. math::

    \mathbf{a} = \frac{d}{dt} \ \mathbf{v} =  \frac{d}{dt} \ ( r \frac{d \theta}{dt} \ \mathbf{u_{\theta}} + \frac{dr}{dt} \mathbf{u_{r}} )

See :ref:`here <kepler3>`.

We get two terms, one in the :math:`\mathbf{u_{\theta}}` direction, which is equal to zero by the central force hypothesis and gives us the same result as above about the area "being swept out" is constant.

The other one is:

.. math::

    \ [ \ \frac{d^2r}{dt^2} + r (\frac{d\theta}{dt})^2 \ ] \ \mathbf{u_r}

We will need this below.

=======
Ellipse
=======

At this point, Strang reminds us that we are heading for the equation of an ellipse.  In polar coordinates, an ellipse has the general equation:

.. math::

    \frac{1}{r} = C - D \cos\theta

We will define

.. math::

    q = \frac{1}{r}

He says we will find that :math:`q` obeys the differential equation:

.. math::

    \frac{d^2q}{d \theta^2} + q = C

and that 

.. math::

    q = C - D \cos\theta

is a solution of that equation (which is trivial to verify).

We have

.. math::

    h = r^2 \frac{d \theta}{dt} = \frac{1}{q^2} \ \frac{d \theta}{dt}

but we want :math:`dq/d\theta`.  How to get there?

Use the chain rule to write:

.. math::

    \frac{dr}{dt} = \frac{d}{dt} \ (\frac{1}{q}) = -\frac{1}{q^2} \ \frac{dq}{dt}
    
    = -\frac{1}{q^2} \ \frac{dq}{d\theta} \ \frac{d\theta}{dt} 
    
    = - h \ \frac{dq}{d\theta}

(the last step follows from :math:`hq^2 = d\theta/dt` above).

The second derivative is:

.. math::

    \frac{d}{dt} \frac{dr}{dt} = - h  \frac{d}{dt} \frac{dq}{d\theta}
    
since we can take the derivatives in either order

.. math::
   
    \frac{d^2 r}{dt^2} =  - h  \frac{d}{d\theta} \ ( \frac{dq}{dt})
    
    = - h \frac{d}{d\theta} \ (\frac{dq}{d\theta} \ \frac{d \theta}{dt})

and using :math:`hq^2 = d\theta/dt` again (and that it doesn't depend on :math:`\theta`):

.. math::

    \frac{d^2 r}{dt^2} = - h^2q^2 \ \frac{d^2q}{d\theta^2}

===================
Putting it together
===================

By Newton's second law we have that the acceleration is:

.. math::

     \frac{\mathbf{F}}{m} = - \frac{GM}{r^2} \mathbf{u_r}

We combine that with the result from differentiating the velocity that we referenced above:

.. math::

    - \frac{GM}{r^2} \mathbf{u_r} = \ [ \ \frac{d^2r}{dt^2} - r (\frac{d\theta}{dt})^2 \ ] \ \mathbf{u_r}
    
    - \frac{GM}{r^2} = \frac{d^2r}{dt^2} - r (\frac{d\theta}{dt})^2

    - GMq^2 = \frac{d^2r}{dt^2} - \frac{1}{q} (\frac{d\theta}{dt})^2


and then recalling the recent results regarding time-derivatives:

.. math::

    hq^2 = \frac{d \theta}{dt}

    \frac{d^2 r}{dt^2} = - h^2q^2 \ \frac{d^2q}{d\theta^2}
     
so

.. math::

    - GMq^2 = \frac{d^2r}{dt^2} - \frac{1}{q} (\frac{d\theta}{dt})^2

    - GMq^2 = - h^2q^2 \ \frac{d^2q}{d\theta^2} - \frac{1}{q} (hq^2)^2
    
Sort out the :math:`q`'s and multiply by :math:`-1`:

.. math::

    GM = h^2 \ \frac{d^2q}{d\theta^2} + h^2q
        
    \frac{GM}{h^2} = \frac{d^2q}{d\theta^2} + q

and this is our differential equation, as promised.

We will flesh this out later.  I just wanted to show that once again, Strang finds a different route to the answer.  A quicker route.

In the parametric equation of the ellipse:

.. math::

    \frac{1}{r} = C - D \cos\theta

    C = \frac{GM}{h^2} = \frac{GM}{r^2 \omega}

the constant :math:`C` controls..

