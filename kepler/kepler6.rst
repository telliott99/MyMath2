.. _kepler6:

#########
Varberg 2
#########

The last part of Varberg's derivation is about K3.  To prove:

.. math::

    T^2 = \frac{(2 \pi)^2}{GM} \ a^3 

where :math:`T` is the period, :math:`GM` is our constant from before, and :math:`a` is the length of the half-major axis of the ellipse.  In other words, the period of an orbit is the :math:`3/2` power of the "radius", technically the semi-major axis of the ellipse.

Start with K2

.. math::

    2 \ \frac{dA}{dt} =  h 

Integrate with respect to time over one revolution obtaining an ellipse with area :math:`\pi a b` and the period :math:`T` for the time

.. math::

    2 \pi a b = hT 

    T^2 = (\frac{2 \pi a b}{h})^2 

Now, go back to the equation for the orbit

.. math::

    r(1 + e \cos \theta) = \frac{h^2}{GM} 

Consider one-half an orbit between :math:`\theta = 0 \rightarrow \theta = \pi`.  The length of the axis is :math:`2a`, equal to :math:`2r` for this orbit, so

.. math::

    2a = \frac{h^2}{GM(1 + e \cos \pi)} +  \frac{h^2}{GM(1 + e \cos 0)} 

    = \frac{h^2}{GM} (\frac{1}{1 - e} +  \frac{1}{1 + e}) 

    = \frac{h^2}{GM} \ \frac{2}{1 - e^2} 

So

.. math::

    a = \frac{h^2}{GM} \ \frac{1}{1 - e^2} 

For an ellipse

.. math::

    \frac{b^2}{a^2} = 1 - e^2 

so

.. math::

    a = \frac{h^2}{GM} \ \frac{a^2}{b^2} 

    b^2 = \frac{ah^2}{GM}  

We had

.. math::

    T^2 = (\frac{2 \pi a b}{h})^2 

    = (\frac{2 \pi a }{h})^2 \  \frac{ah^2}{GM}  

    = \frac{(2 \pi)^2}{GM} a^3 

which is K3.  :math:`GM` is the gravitational constant times the mass of the sun.  The term due to the angular momentum :math:`h` has dropped out.

Note that we can get an estimate for :math:`GM` from observation of the orbits of the planets, and that :math:`G` can be determined very simply, allowing us to find :math:`M`, and "weigh the sun".
