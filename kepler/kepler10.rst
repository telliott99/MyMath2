.. _kepler10:

####################
Kepler Quick Summary
####################

The position vector (from the sun to the planet) is :math:`\mathbf{r}`.  Starting from our definition of the unit vector in the :math:`\mathbf{r}` direction as

.. math::

    \mathbf{u_r} = \ \langle \cos \theta, \sin \theta \rangle 

where :math:`\theta` is the angle with the positive :math:`x`-axis, we find :math:`\mathbf{u_{\theta}} \perp \mathbf{u_r}`

.. math::

    \mathbf{u_{\theta}} = \ \langle -\sin \theta, \cos \theta \rangle 

and confirm orthognality

.. math::

    \mathbf{u_r} \cdot \mathbf{u_{\theta}} = 0 

Remembering that :math:`\theta = \theta(t)`, we easily obtain by the chain rule

.. math::

    \dot{\mathbf{u}}_\mathbf{r} = \dot{\theta} \mathbf{u_{\theta}} 

    \dot{\mathbf{u}}_\mathbf{\theta} = -\dot{\theta} \mathbf{u_{r}} 

:math:`r` is the magnitude of :math:`\mathbf{r}`

.. math::

    \mathbf{r} = r \mathbf{u_r} 

The velocity :math:`\mathbf{v}`

.. math::

    \mathbf{v} = \dot{\mathbf{r}} = \dot{r} \mathbf{u_r} + r \dot{\mathbf{u}}_\mathbf{r}  =  \dot{r} \mathbf{u_r} +  r \dot{\theta}  \mathbf{u_{\theta}}

We use a vector identity that is easy to prove

.. math::

    \frac{d}{dt} \ (\mathbf{a} \times \mathbf{b}) = \dot{\mathbf{a}} \times \mathbf{b} + \mathbf{a} \times \dot{\mathbf{b}} 

to calculate with Feynman's "dots"

.. math::

    \frac{d}{dt} \ (\mathbf{r} \times \mathbf{v}) 

    =  \frac{d}{dt} \ (\mathbf{r} \times \dot{\mathbf{r}}) 

    =  \dot{\mathbf{r}} \times \dot{\mathbf{r}} +  \mathbf{r} \times \ddot{\mathbf{r}} = 0

because any vector's cross-product with itself is zero (including minus itself), which is true for the second term involving the acceleration.

============
Acceleration
============

An actual expression for the acceleration is just a matter of working through the dots

.. math::

    \mathbf{a} = \dot{\mathbf{v}} = \ddot{\mathbf{r}} = \frac{d}{dt} \ (\dot{r}\mathbf{u_r} + r \dot{\theta} \mathbf{u_{\theta}}) 

    = \ddot{r}\mathbf{u_r} + \dot{r}\dot{\mathbf{u}}_\mathbf{r} + \dot{r} \dot{\theta} \mathbf{u_{\theta}} + r \ddot{\theta} \mathbf{u_{\theta}} + r \dot{\theta}  \dot{\mathbf{u}}_\mathbf{\theta}

substituting for :math:`\dot{\mathbf{u}}_\mathbf{r}` and :math:`\dot{\mathbf{u}}_\mathbf{\theta}` from above

.. math::

    = \ddot{r}\mathbf{u_r} + \dot{r}\dot{\theta} \mathbf{u_{\theta}} + \dot{r} \dot{\theta} \mathbf{u_{\theta}} + r \ddot{\theta} \mathbf{u_{\theta}} - r \dot{\theta}^2  \mathbf{u}_\mathbf{r}

    = (\ddot{r} - r \dot{\theta}^2)  \mathbf{u}_\mathbf{r} + (2\dot{r} \dot{\theta} + r \ddot{\theta}) \mathbf{u_{\theta}}  

Rewrite the coefficient for :math:`\mathbf{u_{\theta}}` as

.. math::

    \frac{1}{r}(2r \dot{r} \dot{\theta} + r^2\ddot{\theta}) = \frac{1}{r} \frac{d}{dt} (r^2\dot{\theta})  

================
Angular momentum
================

We find that the acceleration :math:`\mathbf{a} = \dot{\mathbf{v}}` has two parts of which the second (in :math:`\mathbf{u_{\theta}}`)

.. math::

    \frac{1}{r} \ \frac{d}{dt} \ r^2 \dot{\theta} = 0 

is zero because :math:`\mathbf{a}` is all radial.  Hence :math:`r^2 \dot{\theta} = h` where :math:`h` is a constant.  Multiplied by the mass :math:`m`, :math:`mh` becomes the conserved quantity, angular momentum.  It is also twice the area "swept out" and this is the statement of K2.

We get the vector :math:`\mathbf{h}` by defining the plane of motion as the :math:`xy`-plane (:math:`\mathbf{u_r} \times \mathbf{u_{\theta}} = \hat{\mathbf{k}}`) and

.. math::

    \mathbf{h} = \mathbf{r} \times \mathbf{v} = r \mathbf{u_r} \times (\dot{r} \mathbf{u_r} +  r \dot{\theta}  \mathbf{u_{\theta}}) 

the first term is zero so

.. math::

    = r^2  \dot{\theta} ( \mathbf{u_r} \times \mathbf{u_{\theta}} ) = r^2  \dot{\theta}  \ \hat{\mathbf{k}} 

========
Key step
========

With these preliminary steps we come to the key part of the derivation.  I like Varberg's version best.  The radial acceleration is

.. math::

    \mathbf{a} = -\frac{GM}{r^2} \mathbf{u_r} 

Compute :math:`\mathbf{a} \times \hat{\mathbf{k}}` (recall that :math:`\mathbf{a}` is in the :math:`-\mathbf{u_r}` direction) by recognizing that :math:`-\mathbf{u_r} \times \hat{\mathbf{k}} = \mathbf{u_{\theta}}` so

.. math::

    \mathbf{a} \times \hat{\mathbf{k}} = \frac{GM}{r^2} \mathbf{u_{\theta}} 

but from above :math:`\dot{\mathbf{u}}_\mathbf{r} = \dot{\theta} \mathbf{u_{\theta}}` so we have the crucial substitution:

.. math::

    \mathbf{a} \times \hat{\mathbf{k}} = \frac{GM}{r^2 \dot{\theta} } \dot{\mathbf{u}}_\mathbf{r} 

    \mathbf{a} \times \hat{\mathbf{k}} = \frac{GM}{h} \dot{\mathbf{u}}_\mathbf{r} 

Now we just integrate with respect to time and get

.. math::

    \int \mathbf{a} \times \hat{\mathbf{k}} = \int \frac{GM}{h} \dot{\mathbf{u}}_\mathbf{r}  

    \mathbf{v} \times \hat{\mathbf{k}} = \frac{GM}{h} \mathbf{u}_\mathbf{r} + \mathbf{d} 

where :math:`\mathbf{d}` is a constant \emph{vector} of integration.

One last trick, we dot with :math:`\mathbf{r}` and simplify the left-hand side dramatically

.. math::

    \mathbf{r} \cdot ( \mathbf{v} \times \hat{\mathbf{k}}) = (\mathbf{r} \times \mathbf{v}) \cdot  \hat{\mathbf{k}} = \mathbf{h} \cdot \hat{\mathbf{k}} = h 

So

.. math::

    h = \mathbf{r} \cdot (\frac{GM}{h} \mathbf{u}_\mathbf{r} + \mathbf{d}) 

    \frac{h^2}{GM} = \mathbf{r} \cdot (\mathbf{u}_\mathbf{r} + \frac{h}{GM} \mathbf{d} ) 

Define :math:`k = h^2/GM` and :math:`e = hd/GM` and :math:`\theta` as the angle between the constant vector :math:`\mathbf{d}` and :math:`\mathbf{u}_\mathbf{r}`, so finally

.. math::

    k = r (1 + e \cos \theta) 

which for :math:`e < 1` is an ellipse.
