.. _kepler8:

###########
Fitzpatrick
###########

This is a derivation of Kepler's laws from a book I found on the web for Fitzpatrick's course on Mechanics.

He starts by establishing unit vectors in polar coordinates as :math:`\mathbf{e_r}` and :math:`\mathbf{e_{\theta}}` and then parametrically (see :ref:`here <kepler3>`)

.. math::

    \mathbf{e_r} =  \ \langle \cos \theta, \sin \theta \rangle 

    \mathbf{e_{\theta}} =  \ \langle -\sin \theta, \cos \theta \rangle 

    \mathbf{e_{\theta}} \perp \mathbf{e_r} 

So

.. math::

    \dot{\mathbf{e}}_\mathbf{r} = \dot{\theta} \mathbf{e_{\theta}} 

    \dot{\mathbf{e}}_\mathbf{\theta} = -\dot{\theta} \mathbf{e_{r}} 

Writing the position vector as

.. math::

    \mathbf{r} = r \ \mathbf{e_r}  

    \mathbf{v} = \dot{\mathbf{r}} = \dot{r}\mathbf{e_r} + r \dot{\mathbf{e}}_\mathbf{r} =\dot{r}\mathbf{e_r} + r \dot{\theta} \mathbf{e_{\theta}} 

For the acceleration

.. math::

    \mathbf{a} = \dot{\mathbf{v}} = \ddot{\mathbf{r}} = \frac{d}{dt} \ (\dot{r}\mathbf{e_r} + r \dot{\theta} \mathbf{e_{\theta}}) 

    = \ddot{r}\mathbf{e_r} + \dot{r}\dot{\mathbf{e}}_\mathbf{r} + \dot{r} \dot{\theta} \mathbf{e_{\theta}} + r \ddot{\theta} \mathbf{e_{\theta}} + r \dot{\theta}  \dot{\mathbf{e}}_\mathbf{\theta}

    = \ddot{r}\mathbf{e_r} + \dot{r}\dot{\theta} \mathbf{e_{\theta}} + \dot{r} \dot{\theta} \mathbf{e_{\theta}} + r \ddot{\theta} \mathbf{e_{\theta}} - r \dot{\theta}^2  \mathbf{e}_\mathbf{r}

    = (\ddot{r} - r \dot{\theta}^2)  \mathbf{e}_\mathbf{r} + (2\dot{r} \dot{\theta} + r \ddot{\theta}) \mathbf{e_{\theta}}  

As before we recognize the coefficient for :math:`\mathbf{e_{\theta}}` as

.. math::

    \frac{1}{r} \frac{d}{dt} (r^2\dot{\theta}) = \frac{1}{r}(2r \dot{r} \dot{\theta} + r^2\ddot{\theta})  

and this term is also equal to zero because the acceleration is all radial and so the term in parentheses must be zero and so

.. math::

    2 r \dot{r} \dot{\theta} + r\ddot{\theta} =  0 

if we integrate

.. math::

    \int 2 r \dot{r} \dot{\theta} + r\ddot{\theta} = r^2 \dot{\theta} =  h 

where :math:`h` is a constant.

The physical interpretation comes from angular momentum, which is defined as

.. math::

    \mathbf{l} = m \mathbf{r} \times \dot{\mathbf{r}} 

    = m (r \mathbf{e}_\mathbf{r} \times (\dot{r}\mathbf{e_r} + r \dot{\theta} \mathbf{e_{\theta}}) 

    = mr^2  \dot{\theta} \ \hat{\mathbf{k}} 

That is,

.. math::

    mh \ = | \mathbf{l} | 

At this point he goes through the standard analysis to obtain that the area swept out in a small time :math:`\delta A/\delta t = h/2`.  I think we can skip this part.

======
part 2
======

This derivation has an unusual approach to using the information from the inverse square law.  Define a new radial variable, the inverse of :math:`r`

.. math::

    r= \frac{1}{u} 

Differentiate with respect to time

.. math::

    \dot{r} = - \frac{\dot{u}}{u^2} 

obviously.  But what is :math:`\dot{u}`?

.. math::

    \dot{u}= \frac{du}{dt} =  \frac{du}{d\theta} \frac{d\theta}{dt} =  \dot{\theta} \ \frac{du}{d\theta} 

So

.. math::

    \dot{r}= -\frac{1}{u^2} \dot{u} =  -\frac{\dot{\theta}}{u^2} \frac{du}{d\theta} 

Recall :math:`r^2 \dot{\theta} = \dot{\theta}/u^2 = h` so

.. math::

    = -h \ \frac{du}{d \theta}

Differentiate again with respect to time

.. math::

    \ddot{r} = -h \frac{d}{dt} \ (\frac{du}{d \theta}) = -h \dot{\theta} \ \frac{d^2 u}{d\theta^2} 

but :math:`\dot{\theta} = hu^2` so

.. math::

    = - h^2 u^2 \  \frac{d^2 u}{d\theta^2} 

Now, go back to our previous expression for the acceleration, it is

.. math::

    - \frac{GM}{r^2}  =  \ddot{r} - r \dot{\theta}^2 

Plug in for :math:`\ddot{r}` and multiply everything by :math:`-1`:

.. math::

    \frac{GM}{r^2}  = h^2 u^2 \  \frac{d^2 u}{d\theta^2} + r \dot{\theta}^2 

Rearrange (:math:`ru=1`):

.. math::

    \frac{GM}{h^2}  =  \frac{d^2 u}{d\theta^2} + \frac{r^3}{h^2} \dot{\theta}^2 

but :math:`h = r^2 \dot{\theta}` and :math:`h^2 = r^4 \dot{\theta}^2` so

.. math::

    \frac{GM}{h^2}  =  \frac{d^2 u}{d\theta^2} + \frac{1}{r}  

    \frac{GM}{h^2}  =  \frac{d^2 u}{d\theta^2} + u 

How about that?  Now we have a basic differential equation in :math:`u`

We guess the solution has, say :math:`\cos \theta` and constants :math:`A` and :math:`C`.

.. math::

    u = A \cos \theta + C 

because

.. math::

    \frac{d^2 u}{d\theta^2} = -A \cos \theta  

So

.. math::

    C = \frac{GM}{h^2} 

    u = A \cos \theta + \frac{GM}{h^2} 

Technically, we should have :math:`\theta_0` in the solution, but we can just set that equal to zero, since we don't care about where we start.  Go back to :math:`r`

.. math::

    1 = r(A \cos \theta + \frac{GM}{h^2}) 

    \frac{h^2}{GM} = r(A \frac{h^2}{GM} + A \cos \theta) 

Define

.. math::

    e = A = \frac{GM}{h^2} 

so now we have

.. math::

    \frac{h^2}{GM} = r(1 + e \cos \theta) 

which is exactly what we had with Varberg.
