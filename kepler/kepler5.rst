.. _kepler5:

#########
Varberg 1
#########

K2 says that orbits "sweep out equal areas in equal times" or equivalently, that :math:`dA/dt = 0`.  So we start from Newton's force directed toward the sun, the centripetal force, and we will show that the motion stays in a plane, and also implies K2.

Again, this is Feynman's argument (and notation)

.. math::

    \frac{d}{dt} ( \mathbf{r} \times \mathbf{v}) = \frac{d}{dt} ( \mathbf{r} \times \dot{\mathbf{r}}) = 0 

This is zero because you get two terms from the derivative of the cross-product:  one is :math:`\dot{\mathbf{r}} \times \dot{\mathbf{r}} = 0` , and the second one is :math:`\mathbf{r} \times \ddot{\mathbf{r}}`, which is zero because these two vectors point in opposite directions by the centripetal force postulate.

Therefore,  :math:`\mathbf{r} \times \dot{\mathbf{r}}` is constant.  We will say that

.. math::

    \mathbf{r} \times \dot{\mathbf{r}} = \mathbf{h} 

    |\mathbf{h}| = h = 2 \ \frac{dA}{dt} 

If :math:`\mathbf{h} = 0`, there is no force, and just straight-line motion.  But for  :math:`\mathbf{h} \ne 0`, then :math:`\mathbf{r}` and :math:`\dot{\mathbf{r}}` are in a plane that doesn't change with time, and :math:`\mathbf{h}` is the normal vector of that plane.

.. math::

    h = | \mathbf{r} \times \dot{\mathbf{r}} | = |\mathbf{r} \times \frac{d\mathbf{r}}{dt} | 

by the discussion about area previously (Varberg's Example :math:`14.5`)

.. math::

    h =  r^2 \ \frac{d \theta}{dt} = 2 \ \frac{dA}{dt} 

This is the statement of K2.  :math:`dA/dt` is constant, equal to :math:`h/2`.

At this point, Varberg reverse the argument and show that planar motion and K2 imply a centripetal force.  But this is just Feynman's dots, which we already went through.

=====================
Kepler's first law k1
=====================

Now, we make an additional hypothesis due to Newton, which is that the acceleration is proportional to the inverse square of the distance from the sun (origin), and pointed toward it.

.. math::

    \mathbf{a} = \ddot{\mathbf{r}} = - \frac{GM}{r^2} \mathbf{u_r} 

where (as before) :math:`\mathbf{u_r}` is the unit vector in the :math:`\mathbf{r}` direction (i.e. equal to :math:`\mathbf{r}/|\mathbf{r}|`), and :math:`GM` is a constant.

The first of three main steps in the proof is to take the cross-product with :math:`\hat{\mathbf{k}}` (as the text says, "this allows us to introduce the area information in vectorial form")

.. math::

    \ddot{\mathbf{r}} \times \hat{\mathbf{k}} = - \frac{GM}{r^2} \ \mathbf{u_r} \times \hat{\mathbf{k}} = \frac{GM}{r^2} \ \mathbf{u_\theta} 

(recall that we "go to the left" for :math:`\mathbf{u_\theta}`).  It should not be surprising that the cross-product brings us back to :math:`\mathbf{u_\theta}`, since we aligned :math:`\mathbf{u_r} \times \mathbf{u_{\theta}}` with :math:`\hat{\mathbf{k}}`.

From our discussion of the unit vectors and parametrization,

.. math::

    \frac{d}{dt} \ \mathbf{u_r} = \dot{\mathbf{u}}_\mathbf{r} = \frac{d\theta}{dt} \ \mathbf{u_\theta} = \omega \mathbf{u_\theta} 

    \mathbf{u_\theta} = \frac{\dot{\mathbf{u}}_{\mathbf{r}}}{\omega} 

and from K2

.. math::

    \frac{d \theta}{dt} = \omega = \frac{h}{r^2} 

Hence

.. math::

    \mathbf{u_\theta} =  \frac{\dot{\mathbf{u}}_{\mathbf{r}}}{\omega} = \frac{\dot{\mathbf{u}}_{\mathbf{r}}}{h/r^2} 

So the cross-product which we had as

.. math::

    \ddot{\mathbf{r}} \times \hat{\mathbf{k}} = \frac{GM}{r^2} \  \mathbf{u_\theta} 

is equal to

.. math::

    = \frac{GM}{r^2} \  \frac{\dot{\mathbf{u}}_{\mathbf{r}}}{h/r^2} 

    = \frac{GM}{h} \ \dot{\mathbf{u}}_{\mathbf{r}}  

This is really the key step in our whole adventure.

The second clever thing we do here is to integrate with respect to time

.. math::

    \int \ddot{\mathbf{r}} \times \hat{\mathbf{k}} = \int \frac{GM}{h} \ \dot{\mathbf{u}}_{\mathbf{r}}  

(remember that :math:`GM`, :math:`h` and :math:`\hat{\mathbf{k}}` are all constant)

.. math::

    \dot{\mathbf{r}} \times \hat{\mathbf{k}} = \frac{GM}{h} \ ( \mathbf{u_r} + \mathbf{E}) 

where :math:` \mathbf{E}` is a constant (vector) of integration.

The third step is to form the dot product of both sides with :math:`\mathbf{r}`

.. math::

    \mathbf{r} \cdot ( \dot{\mathbf{r}} \times \hat{\mathbf{k}}) = \frac{GM}{h} \ \mathbf{r} \cdot ( \mathbf{u_r} + \mathbf{E}) 

using a vector identity, the left-hand side is

.. math::

    \mathbf{r} \cdot ( \dot{\mathbf{r}} \times \hat{\mathbf{k}}) = (\mathbf{r} \times \dot{\mathbf{r}}) \cdot \hat{\mathbf{k}} 

but

.. math::

    \mathbf{r} \times \dot{\mathbf{r}} = \mathbf{h} =  h \ \hat{\mathbf{k}} 

so we have

.. math::

    h \ \hat{\mathbf{k}} \cdot \hat{\mathbf{k}} = h 

Putting it all together

.. math::

    \mathbf{r} \cdot (\ddot{\mathbf{r}} \times \hat{\mathbf{k}}) = h = \frac{GM}{h} \ \mathbf{r} \cdot ( \mathbf{u_r} + \mathbf{E}) 

    \frac{h^2}{GM} =  \mathbf{r} \cdot ( \mathbf{u_r}+ \mathbf{E}) 

Recall that :math:` \mathbf{u_r}` is the unit vector in the same direction as :math:`\mathbf{r}` so that :math:`\mathbf{r} \cdot  \mathbf{u_r} = r`.

We can take :math:`\mathbf{E}` to be in the direction of :math:`\mathbf{r}` at time-zero so :math:`\mathbf{r} \cdot \mathbf{E}` is equal to :math:`r` times :math:`e` times the cosine of the angle between them at some later time.  (Since :math:`\mathbf{E}` is a constant vector of integration, its magnitude :math:`e` can be anything we want).

Thus, in polar coordinates this becomes

.. math::

    r(1 + e \cos \theta) = \frac{h^2}{GM} 

These curves are conic sections.  If :math:`e < 1` it's an ellipse.

.. image:: /figs/quick_ellipse.png
   :scale: 50 %

The curve above is an ellipse with the formula

.. math::

    r(1 + 0.8 \cos \theta) = 1 

:math:`e` is the eccentricity of the ellipse

.. math::

    e^2 +  \frac{b^2}{a^2} = 1 

In the figure

.. math::

    e^2 = 0.8^2 = 0.64 

    \frac{b^2}{a^2} = 1 - 0.64 = 0.36 

    \frac{b}{a} = \sqrt{0.36} = 0.6 
