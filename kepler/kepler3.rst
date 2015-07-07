.. _kepler3:

#######
Vectors
#######

Here is a sketch of the situation.

:math:`\mathbf{r}` is the position vector, extending radially out from the sun to the planet.  :math:`\mathbf{u_r}` is a unit vector in the :math:`\mathbf{r}` direction, so that

.. math::

    \mathbf{r} = r \mathbf{u_r} 

By the central force hypothesis, the acceleration :math:`\mathbf{a} = \dot{\mathbf{v}} = \ddot{\mathbf{r}}` is in the :math:`- \mathbf{u_r}` direction.  The source of all our complexity is that the velocity :math:`\mathbf{v} = \dot{\mathbf{r}}` is not perpendicular to :math:`\mathbf{u_r}` but makes an angle :math:`\theta` with it.

Earlier we proved that

.. math::

    \mathbf{r} \times \mathbf{v} = \mathbf{r} \times \dot{\mathbf{r}} = \mathbf{c} 

is a constant.  Here we give that vector the label :math:`\mathbf{c}` and a direction.  We align :math:`\mathbf{c}` with :math:`\hat{\mathbf{k}}`.  All the motion takes place in the :math:`xy`-plane.  Finally, we define :math:`\mathbf{u_{\theta}}` as orthogonal to :math:`\mathbf{u_{r}}` (and to :math:`\hat{\mathbf{k}}`).  :math:`\mathbf{u_{\theta}}` is aligned with :math:`\hat{\mathbf{j}}`.

As a result of these definitions:

.. math::

    \mathbf{u_r} \times \mathbf{u_{\theta}} = \hat{\mathbf{k}} 

    \hat{\mathbf{k}} \times \mathbf{u_r} = \mathbf{u_{\theta}} 

    \mathbf{u_{\theta}} \times \hat{\mathbf{k}} = \mathbf{u_r} 

At any given time, :math:`\mathbf{r}` makes an angle :math:`\theta` with the :math:`x`-axis, and is at a distance :math:`r` from the origin, so we write:

.. math::

    \mathbf{r} = \ \langle r \cos \theta, r \sin \theta \rangle 

    \mathbf{u_r} =  \ \langle \cos \theta, \sin \theta \rangle 

    \mathbf{u_{\theta}} \perp \mathbf{u_r} 

    \mathbf{u_{\theta}} =  \ \langle -\sin \theta, \cos \theta \rangle 

We verify that the cross-product is zero and that both vectors are unit length.

Now, differentiate :math:`\mathbf{u_r}` and :math:`\mathbf{u_{\theta}}` (recalling that :math:`\theta` is a function of time as well):

.. math::

    \frac{d}{dt} \ \mathbf{u_r} = \dot{\mathbf{u}}_\mathbf{r} = \frac{d\theta}{dt} \ \langle -\sin \theta, \cos \theta \rangle =  - \frac{d\theta}{dt} \ \mathbf{u_{\theta}} 

    \frac{d}{dt} \ \mathbf{u_{\theta}} = \dot{\mathbf{u}}_\mathbf{\theta} =  \frac{d\theta}{dt} \ \langle -\cos \theta, -\sin \theta \rangle =  \frac{d\theta}{dt} \ \mathbf{u_r} 

With this preparation, we can get an expressions for the velocity

.. math::

    \mathbf{v} = \dot{\mathbf{r}} = \frac{d}{dt} \ (r \mathbf{u_r}) 
    
    = \frac{dr}{dt} \mathbf{u_r} + r \frac{d \theta}{dt}  \mathbf{u_{\theta}} 

and (with a little work) we can get the acceleration

.. math::

    \mathbf{a} = \dot{\mathbf{v}} = \ddot{\mathbf{r}} 
    
    = \frac{d}{dt} \ (\frac{dr}{dt} \mathbf{u_r} + r \frac{d \theta}{dt}  \mathbf{u_{\theta}}) 

    = \frac{d^2r}{dt^2} \mathbf{u_r} + \frac{dr}{dt} \dot{\mathbf{u}}_\mathbf{r} + \frac{dr}{dt} \frac{d \theta}{dt}  \mathbf{u_{\theta}} + r \frac{d^2\theta}{dt^2} \mathbf{u_{\theta}} + r \frac{d\theta}{dt} \dot{\mathbf{u}}_\mathbf{\theta}  

We get three terms from differentiating the triple product :math:`r \ d\theta/dt  \ \mathbf{u_{\theta}}`, by a variation on the product rule.  Substitute for the dotted terms from above

.. math::

    = \frac{d^2r}{dt^2} \mathbf{u_r} + \frac{dr}{dt} \frac{d\theta}{dt} \ \mathbf{u_{\theta}} + \frac{dr}{dt} \frac{d \theta}{dt}  \mathbf{u_{\theta}} + r \frac{d^2\theta}{dt^2} \mathbf{u_{\theta}} + r \frac{d\theta}{dt} \frac{d\theta}{dt} \ \mathbf{u_r}  

Group common terms together

.. math::

    = \ [ \ \frac{d^2r}{dt^2} + r (\frac{d\theta}{dt})^2 \ ] \ \mathbf{u_r}  + \ [ \ 2 \ \frac{dr}{dt} \frac{d\theta}{dt} + r \frac{d^2\theta}{dt^2} \ ] \ \mathbf{u_{\theta}}  

Now for a trick, look at the factors multiplying :math:`\mathbf{u_{\theta}}` and recognize that

.. math::

    \frac{d}{dt} ( r^2 \frac{d\theta}{dt}) = 2 r \frac{dr}{dt} \frac{d\theta}{dt} + r^2 \frac{d^2\theta}{dt^2}

Therefore, the cofactors for :math:`\mathbf{u_{\theta}}` can be re-written as

.. math::

    \frac{1}{r} \ [ \ \frac{d}{dt} ( r^2 \frac{d\theta}{dt}) \ ]

and since if the acceleration is to be only radial (pointed toward the sun), this term must be equal to zero.

.. math::

    \frac{1}{r} (\frac{d}{dt} ( r^2 \frac{d\theta}{dt}) = 0 

    \frac{d}{dt} ( r^2 \frac{d\theta}{dt}) = 0 

    r^2 \frac{d\theta}{dt} = h = \text{constant} 

If we write :math:`d\theta/dt = \omega`, the angular velocity, then :math:`r \omega` is the speed of the planet, and :math:`r` times that, times the mass, is the angular momentum.  This result is the conservation of angular momentum.
