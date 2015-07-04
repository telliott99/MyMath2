.. _marsden-line-integrals:

########################
Marsden:  Line integrals
########################

Marsden (p. 141) talks about a "path", denoted by :math:`\mathbf{c}(t)`, and a curve :math:`C` as 

    the set of values of a function that maps an interval of real numbers into the plane or space.  We shall call such a map a **path**.

So, for example,

.. math::

    \mathbf{c}(t) = (x_0,y_0,z_0) + t \mathbf{v}

where :math:`\mathbf{v}` is a vector in space.  And

    the unit circle C: x^2 + y^2 = 1 in the plane is the image of the path

A *curve* is an **image** of a path

.. math::

    \mathbf{c}:  \mathbb{R} \rightarrow \mathbb{R^2}, \ \ \ = (\cos t, \sin t), \ \ \ 0 \le t \le 2 \pi.

This is not too different from Auroux's use of :math:`\mathbf{r}(t)`, the distinction being that the former is a point in space and the latter is a vector.  Then on p. 275 Marsden gives this as a definition:

.. math::

    L(\mathbf{c}) = \int_a^b \lVert \mathbf{c}'(t) \rVert \ dt

They don't really justify the definition.  The way I think of it is:  speed :math:`\times` time :math:`=` distance.  And if the speed varies, then we integrate over little elements of :math:`dt`.

.. math::

    \text{speed} \ = \lVert \mathbf{v} \rVert

The speed is the norm of the velocity.  And the velocity is the time derivative of the position:

.. math::

    \lVert \mathbf{v} \rVert = \lVert \mathbf{c}'(t) \rVert

Since

.. math::

    \mathbf{c}(t) = \langle x(t), y(t) \rangle
    
    \mathbf{c}'(t) = \langle \frac{dx}{dt}, \frac{dy}{dt} \rangle
    
    \lVert \mathbf{c}'(t) \rVert = \sqrt{(\frac{dx}{dt})^2 + (\frac{dy}{dt})^2}

+++++++
Example
+++++++

A circle of radius :math:`r`, centered at the origin.  We have

.. math::

    x = r \cos t
    
    dx = - r \sin t \ dt
    
    y = r \sin t
    
    dy = r \cos t \ dt

    \lVert \mathbf{c}'(t) \rVert = \sqrt{(-r \sin t)^2 + (r \cos t)^2 }
    
    = r
    
    L(\mathbf{c}) = \int_a^b \lVert \mathbf{c}'(t) \rVert \ dt
    
    = r \int_a^b dt
    
Say, once around the circle, :math:`t = 0 \rightarrow 2 \pi` and the result is just :math:`2 \pi r`.




