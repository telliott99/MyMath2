.. _paraboloid sarea:

#######################
Paraboloid Surface Area
#######################

A paraboloid is a solid whose vertical cross-section is a parabola (usually, it is centered along the :math:`z`-axis).  It may be oriented opening up, or down.  The cross-sections parallel to the :math:`xy`-plane are typically circles, though the shape factors for the parabolas in the :math:`xz`- and :math:`yz`-planes could be different, giving ellipses in cross-section.

Consider

.. math::

    z = 2 - x^2 - y^2 

This is a paraboloid that opens down (it gets large and negative when either :math:`x` or :math:`y` get large).  The vertex is at :math:`z=2`.  When :math:`z=0`, the cross-section is a circle of radius :math:`r^2=2`.

Usually, cylindrical coordinates are good for dealing with this solid.  For example, the volume element is :math:`dV = \ dz \ r \ dr \ d \theta`.

As with the volume, there are two ways (at least) to do the surface area.  The first is to lay the parabola down as :math:`f(x)`.

.. math::

    f(x) = \sqrt{x} 

    f'(x) = \frac{1}{2} \frac{1}{\sqrt{x}} 

    f'(x)^2 = \frac{1}{4x} 

For the surface area of a volume of revolution, we take the circumference of the solid at each value of :math:`x` times the path element :math:`ds` (\emph{not} :math:`dx`).  This element is

.. math::

    ds = \sqrt{1 + f'(x)^2} \ dx 

    = \sqrt{1 + \frac{1}{4x}} \ dx 

So the surface area is

.. math::

    SA = \int_a^b C(x) \ dx 

    = 2 \pi \int _a^b\sqrt{x} \ \sqrt{1 + \frac{1}{4x}} \ dx 

    = 2 \pi \int_a^b \ \sqrt{x + \frac{1}{4}} \ dx 

    = \frac{4}{3} \pi \ (x + \frac{1}{4})^{3/2} \ \bigg |_a^b 

    = \frac{4}{3} \pi \ [  \ (b + \frac{1}{4})^{3/2} -  (a + \frac{1}{4})^{3/2} \  ] 

If :math:`a=0`

.. math::

    = \frac{4}{3} \pi \ [  \ (b + \frac{1}{4})^{3/2} -  \frac{1}{4})^{3/2} \  ] 

    = \frac{4}{3} \pi \ [  \ (b + \frac{1}{4})^{3/2} -  \frac{1}{8} \  ] 

For this problem, :math:`b=2` and the answer simplifies a bit

.. math::

    = \frac{4}{3} \pi \ [  \ (2 + \frac{1}{4})^{3/2} -  \frac{1}{8} \  ] 

    = \frac{4}{3} \pi \ [ \frac{27}{8} -  \frac{1}{8} \  ] 

    = \frac{26}{6} \pi 

Let's try to do this by integrating over two variables.  We have

.. math::

    f(x,y) = 2 - x^2 - y^2 

    f_x = -2x 

    f_y = -2y 

The surface area element is

.. math::

    dS = \sqrt{1 + f_x^2 + f_y^2} \ dx \ dy 

The surface area integral is

.. math::

    SA = \iint_R \sqrt{1 + f_x^2 + f_y^2} \ dx \ dy 

    = \iint_R \sqrt{1 + 4x^2 + 4y^2} \ dx \ dy 

Now is a good time to switch to polar coordinates (remember the extra factor of :math:`r`):

.. math::

    SA = \int_{\theta = 0}^{2 \pi} \int_{r=0}^{R}  \sqrt{1 + 4r^2} \ r \  dr \ d \theta 

    = 2 \pi  \int_{r=0}^{R}  \sqrt{1 + 4r^2} \ r \  dr  

    = 2 \pi \  \frac{1}{12} \ [ \ (1 + 4r^2)^{3/2} \ ] \ \bigg |_0^R  

Here, recall that :math:`R = \sqrt{2}`, so

.. math::

    = \frac{\pi}{6} ( 27 - 1)  

    = \frac{26}{6} \pi 
