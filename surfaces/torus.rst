.. _torus:

#####
Torus
#####

The general theory which allows us to calculate surface areas includes a formula for parametrized surfaces.

For parametrization of a line or a curve we need only one variable.

.. math::

    x = \cos t \ \ \ \  y = \sin t \ \ \ \ z = ct 

where :math:`t` is the parameter and :math:`c` is a constant, is the parametrization of a helix.

For a surface (like a sphere, or a torus), we will need two parameters, which are usually called :math:`u` and :math:`v`.

.. image:: /figs/torus.png
   :scale: 50 %

To get the surface area, we will just calculate

.. math::

    V = \int \ du \ dv 

over the appropriate range of the two variables.  There is an additional constant:  we need to figure out the exchange rate for the surface area element :math:`dS`  (composed of sides :math:`du` and :math:`dv`) to units of :math:`dA` (composed of :math:`dx` and :math:`dy`).  More about that later.

A torus is like a small circle moved around in a larger circle.  The small circle is the cross-section of the donut (radius :math:`r`), while the large circle traces out the path of the donut (radius :math:`R`).  Our parameters will be the angles :math:`\theta` and :math:`\phi`.  :math:`\theta` describes the position of on the large circle (the position of the center of the small circle) as

.. math::

    x_c = R \cos \theta \ \ \ \  y_c = R \sin \theta 

In this approach, the donut's axis of symmetry is the :math:`z`-axis, and the body of the donut is centered half above the :math:`xy`-plane and half below it.  The second angle, :math:`\phi`, describes where we are on the small circle.  In particular, the distance above or below the :math:`xy`-plane will be

.. math::

    z = r \sin \phi 

The only tricky part is the finaly adjustment to obtain the actual :math:`x` and :math:`y` coordinates.  For :math:`x`, when :math:`\phi = 0`, we go out from the origin an additional distance :math:`r`, while when :math:`\phi = \pi`, we subtract the same distance.  Our first attempt is:

.. math::

    x = x_c + r \cos \phi 

    = R \cos \theta + r \cos \phi 

While this is correct for :math:`\theta = 0` it is not correct for other angles.  We need an additional factor of

:math:`\cos \theta`:

.. math::

    x = R \cos \theta + r \cos \phi \cos \theta 

    = \cos \theta (R + r \cos \phi) 

It may not be clear that this works for all angles, but if :math:`\theta = \pi/2` we add nothing additional to :math:`x_c`, and that is just what we want.  Similarly for :math:`y`

.. math::

    y = y_c + r \cos \phi \sin \theta 

    = \sin \theta (R  + r \cos \phi) 

Now, according to the theory, what we need to do is take the partial derivatives of these functions with respect to :math:`\theta` and :math:`\phi`.  For example:

.. math::

    x_{\theta} = \frac{dx}{d \theta} = \frac{d}{d \theta} \ \cos \theta (R + r \cos \phi) 

We find that

.. math::

    x = \cos \theta (R + r \cos \phi) 

    x_{\theta} = -\sin \theta (R + r \cos \phi) 

    x_{\phi} = -\cos \theta \ r \sin \phi 

while

.. math::

    y = \sin \theta (R  + r \cos \phi) 

    y_{\theta} = \cos \theta (R + r \cos \phi) 

    y_{\phi} = -\sin \theta \ r \sin \phi 

:math:`z` does not depend on :math:`\theta` so

.. math::

    z_{\theta} = 0 

    z_{\phi} = r \cos \phi 

The position vector to a point on the surface is

.. math::

    \mathbf{r} = \ \langle x,y,z \rangle 

    \mathbf{r_{\theta}} = \ \langle x_{\theta},y_{\theta},z_{\theta} \rangle 

    \mathbf{r_{\phi}} = \ \langle x_{\phi},y_{\phi},z_{\phi} \rangle 

The unit for conversion is called the Jacobian.  It is the length of the vector :math:`\mathbf{r_{\theta}} \times \mathbf{r_{\phi}}`.  It's a bit complicated, so let's do the pieces individually.  The vector product has three terms

.. math::

    \hat{\mathbf{i}} \ y_{\theta} z_{\phi} -  y_{\phi} z_{\theta} 

    = \hat{\mathbf{i}} \  \cos \theta (R + r \cos \phi) r \cos \phi - 0 

    \hat{\mathbf{j}} \ x_{\phi} z_{\theta} -  x_{\theta} z_{\phi} 

    = \hat{\mathbf{j}} \  0 - \sin \theta (R + r \cos \phi) r \cos \phi  

The third term is most complicated

.. math::

    \hat{\mathbf{k}} \ x_{\theta} y_{\phi} -  x_{\phi} y_{\theta} 

    = \hat{\mathbf{k}} \sin \theta (R + r \cos \phi) \sin \theta \ r \sin \phi + \cos \theta \ r \sin \phi \cos \theta (R + r \cos \phi) 

But notice that we have the same term times :math:`\sin^2 \theta` and :math:`\cos^2 \theta` so this reduces immediately to

.. math::

    = \hat{\mathbf{k}}  (R + r \cos \phi) \ r \sin \phi 

The next (and nearly the last) step is to calculate the length of this vector, by squaring each term and adding.  Before we do that, notice that all three components contain a factor of :math:`r (R + r \cos \phi)`.  We will leave that aside and remember it at the end.  The rest of the sum of squares is:

.. math::

    \cos^2 \theta \cos^2 \phi + \sin^2 \theta \cos^2 \phi + \sin^2 \phi   

    = \cos^2 \phi + \sin^2 \phi  = 1 

So the factor we held aside is all that's left

.. math::

    |\mathbf{r_{\theta}} \times \mathbf{r_{\phi}} | = r (R + r \cos \phi) 

And the surface integral is just

.. math::

    A_S = \int dS = \int_{\theta = 0}^{2 \pi} \int_{\phi = 0}^{2 \pi} |\mathbf{r_{\theta}} \times \mathbf{r_{\phi}}| \ d \phi \ d \theta 

    = \int_{\theta = 0}^{2 \pi} \int_{\phi = 0}^{2 \pi} r (R + r \cos \phi) \ d \phi \ d \theta 

Since :math:`\theta` is independent of :math:`\phi` and :math:`R` and :math:`r`, we get

.. math::

    = 2 \pi r  \int_{\phi = 0}^{2 \pi} (R + r \cos \phi) \ d \phi  

But the integral of :math:`\cos \phi` is just :math:`\sin \phi`, which is zero at the upper and lower bounds on :math:`\phi`, hence

.. math::

    = 2 \pi r  \int_{\phi = 0}^{2 \pi} R \ d \phi  

    = 2 \pi r  \ 2 \pi R 

Which is pretty amazing.  We go around the torus along what is called its centroid, traveling a distance :math:` 2 \pi R`.  At each point we have the circumference of the small circle, which is :math:` 2 \pi r`.

It seems strange that the curvature doesn't make any difference.  There is a theorem in geometry (the Theorem of Pappus), with the same result.

Pappus also allows us to calculate the volume as

.. math::

    V = \pi r^2 \ 2 \pi R 
