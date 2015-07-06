.. _kepler4:

###########
Kepler Area
###########

At this point, we have almost all the tools we need to follow the derivation of Kepler's laws.  We just need a bit more discussion of area "swept out" by a planet in a short time.  Our approach is based on Varberg *Calculus* (online version only, Chapter 14).

We revisit the triangle formed by the motion of the planet, and confirm that twice the area of the triangle is equal to

.. math::

    h =  r^2 \ \frac{d \theta}{dt} 

The thing that makes it confusing is that whereas Feynman used the velocity for one of the sides of the triangle and showed that

.. math::

    \mathbf{r} \times \mathbf{v} = \mathbf{r} \times \dot{\mathbf{r}} = \mathbf{h}  

is a constant, Varberg use :math:`d\mathbf{r}` for their triangle.  It leads to some confusing aspects in the presentation, which I want to work through since I like everything else about their derivation.

Here is their diagram

.. image:: /figs/Varberg14_3.png
   :scale: 50 %

They use :math:`\mathbf{X}` for the position vector, but I will label it as :math:`\mathbf{r}`, following Feynman.  This vector "stays always in the :math:`xy`-plane."  Also, I will use :math:`\mathbf{u_r}` for the vector they call :math:`\mathbf{L}` and similarly :math:`\mathbf{u_\theta}` for the vector they call :math:`\mathbf{L}^{\perp}`.

We are asked to show that

.. math::

    2 \ \frac{dA}{dt} = \ | \frac{d\mathbf{r}}{dt} \times \mathbf{r} | 

This presentation is a bit different than Feynman's, and it confused me for a while, because, just for starters, we proved before that :math:`dA/dt = 0` but that will not be the case here, because now :math:`dA/dt` means something different.

What I'm going to do is to change the notation a bit and say that in a short time :math:`\Delta t`, the area that is swept out is :math:`\Delta A`, corresponding to a length :math:`d\mathbf{r} = \mathbf{v} \Delta t`, and that by the geometry we have

.. math::

    2 \ \Delta A = |\mathbf{r} \times \mathbf{v} \Delta t | 

I assert that it is OK to bring :math:`\Delta t` out of the cross product (by the rule of scalar multiplication), since it is a scalar quantity, and is a constant at any stage of its future journey to the limit when :math:`\Delta t \rightarrow 0`, so I write

.. math::

    2 \ \Delta A = |\mathbf{r} \times \mathbf{v} | \Delta t 

Now we have

.. math::

    2 \ \frac{\Delta A}{\Delta t} = |\mathbf{r} \times \mathbf{v} | 

and in the limit

.. math::

    2 \ \frac{dA}{dt} = |\mathbf{r} \times \mathbf{v} | 

Now this is not quite what we were asked to prove, but recall that

.. math::

    \frac{d\mathbf{r}}{dt} \times \mathbf{r} = \dot{\mathbf{r}}  \times \mathbf{r} = - \mathbf{r} \times \dot{\mathbf{r}} 

so the absolute values are the same.  Again, the result is that

.. math::

    2  \ \frac{dA}{dt} =  | \dot{\mathbf{r}} \times \mathbf{r} | = | \mathbf{r} \times \dot{\mathbf{r}} | = | \mathbf{h} | = h 

If you're not completely happy with the argument allowing this step:

.. math::

    2 \ \Delta A = |\mathbf{r} \times \mathbf{v} \Delta t | = |\mathbf{r} \times \mathbf{v} | \Delta t 

recall that

.. math::

    \mathbf{r} \times \mathbf{v} = \mathbf{r} \times \dot{\mathbf{r}} = \mathbf{h}  

so

.. math::

    |\mathbf{r} \times \mathbf{v} \Delta t | = |\mathbf{c} \Delta t | = h \Delta t  

Varberg *et al.* also give a second argument which which we will go through because it gives us the term

.. math::

    r^2 \ \frac{d \theta}{dt} = h 

By the geometry of the triangle, the area is

.. math::

    2 \ dA = r \ r d \theta = r^2 d \theta 

where :math:`r` is :math:`|\mathbf{r}|`.  And then they say

.. math::

    2 \ \frac{dA}{dt} = r^2 \ \frac{d\theta}{dt}  

They do this without comment, but this result assumes that :math:`r` does not vary with time, although clearly it does (that's the whole point of everything we are doing here).  The product rule would give us:

.. math::

    \frac{d}{dt} \ r^2 d \theta = 2 r \ d \theta  \ \frac{dr}{dt} + r^2 \ \frac{d\theta}{dt}  

This looks a little weird because of the single differential :math:`d\theta`, but I think what it means is that in the limit, the first term goes to zero.

Another way of explaining this is to break the area into two parts.

.. image:: /figs/kepler_area_calc.png
   :scale: 50 %

The first part is :math:`(1/2) r` times :math:`r \ d\theta`, the length of (almost straight) arc perpendicular to :math:`\mathbf{r}`.  This is the part we get by assuming that :math:`r` is constant.  And in the limit as :math:`t \rightarrow 0`, the resulting :math:`d\theta/dt` has some value, namely, the angular velocity.

The second part is :math:`(1/2) r \ d\theta` times :math:`dr`.  This is the part that accounts for the change in :math:`r`, but it contains two differentials, only one of which gets rescued into some quantity by :math:`dt`.  The other just goes to zero, so the whole thing is zero.

Anyway, let's continue with the argument.

Go back to the right-hand side of what we were asked to prove above

.. math::

    2 \ \frac{dA}{dt} =  | \frac{d\mathbf{r}}{dt} \times \mathbf{r} | 

and show that it turns into :math:`r^2 d\theta/dt`.  Using :math:`\mathbf{u_r}` for the unit vector in the :math:`\mathbf{r}` direction, we have

.. math::

    \frac{d\mathbf{r}}{dt}  = \frac{d}{dt} (r \mathbf{u_r}) = \frac{dr}{dt} \mathbf{u_r} + r \dot{\mathbf{u}}_\mathbf{r} 

where the first part is just separating the scalar and unit vector part of :math:`\mathbf{r}` and the rest is from the product rule.  At this point we recall the result that :math:`\dot{\mathbf{u}}_\mathbf{r}  = d \theta/dt \ \mathbf{u_\theta}`, so we have

.. math::

    = \frac{dr}{dt} \mathbf{u_r} + r  \frac{d \theta}{dt} \ \mathbf{u_\theta} 

So now this is what we need to cross with :math:`\mathbf{r}`, also known as :math:`r \mathbf{u_r}`.  We write

.. math::

    (\frac{dr}{dt}  \mathbf{u_r} + r  \frac{d \theta}{dt} \  \mathbf{u_\theta}) \times r  \mathbf{u_r} 

    = (\frac{dr}{dt}  \mathbf{u_r} \times  r  \mathbf{u_r}) + (r  \frac{d \theta}{dt} \  \mathbf{u_\theta} \times r  \mathbf{u_r}) 

The first term is zero (the cross-product of :math:`\mathbf{u_r}` with itself), and because these are unit vectors the absolute value of the second term's vector cross-product is :math:`1`

.. math::

    | r  \frac{d \theta}{dt} \ \mathbf{u_\theta} \times r \mathbf{u_r} | =  r^2 \frac{d \theta}{dt} \ |  \mathbf{u_\theta} \times  \mathbf{u_r} | =  r^2 \frac{d \theta}{dt} 

So what we've shown is that

.. math::

    2 \ \frac{dA}{dt} =  | \mathbf{r} \times \dot{\mathbf{r}} | 

and

.. math::

    2 \ \frac{dA}{dt} =  r^2 \ \frac{d \theta}{dt} 

This term (:math:`r^2 \ d\theta/dt`) is what Hartig calls :math:`c` and the other guys call :math:`h`.  As the vector :math:`\mathbf{h}`, it points in the :math:`\hat{\mathbf{k}}` direction and is the angular momentum but without the mass component.
