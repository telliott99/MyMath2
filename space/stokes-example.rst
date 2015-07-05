.. _Stokes ex:

#########
Stokes ex
#########

State the theorem:

.. math::

    \oint_C \mathbf{F} \cdot \mathbf{r} = \iint_R (\nabla \times \mathbf{F}) \cdot \hat{\mathbf{n}} \ dS 

By the usual reasoning, since :math:`d\mathbf{r} = \langle dx,dy,dz \rangle`, the left-hand side is

.. math::

    P \ dx + Q \ dy + R \ dz 

Now, suppose we have

.. math::

    \mathbf{F} = \langle z,x,y \rangle 

and :math:`C` is the unit circle in the :math:`xy`-plane,

then

.. math::

    P \ dx + Q \ dy + R \ dz = \oint_C  z \ dx + x \ dy + y \ dz 
    
    =   \oint_C x \ dy 

Parameterize

.. math::

    x  = \cos t

    y  = \sin t

we have

.. math::

    \oint_C x \ dy = \int_0^{2\pi} \ \cos t \ \cos t \ dt 

    = \frac{1}{2}(t + \sin t \cos t) \ \bigg |_0^{2\pi} = \pi 

For the surface, we can use anything that passes through :math:`C`, let's use the paraboloid for fun.

.. math::

    z = 1 - x^2 - y^2 

We need the curl of :math:`\mathbf{F} = \ <z,x,y>`

.. math::

    \nabla \times \mathbf{F} = \ < 1,1,1> 

We need

.. math::

    \hat{\mathbf{n}} \ dS = \langle -f_x,-f_y,1 \rangle  \ dx \ dy =  \langle 2x,2y,1 \rangle  \ dx \ dy 

so

.. math::

    \iint_R (\nabla \times \mathbf{F}) \cdot \hat{\mathbf{n}} \ dS =  \iint_R \ 2x + 2y + 1 \ dx \ dy 

Again, :math:`C` is the unit circle in the :math:`xy`-plane.  To save effort, we can notice that

.. math::

    \int x \ dx = \overline{x} 

What is the *average* value of :math:`x` over the unit circle?  It is just equal to :math:`0`.  The same thing is true for the second integrand (reverse the order of integration).  So we have just

.. math::

    \iint_R \  1 \ dx \ dy = \pi 

which matches what we had above.

Suppose we hadn't seen this.  We could do

.. math::

    \int_{x=-1}^{1} \int_{y=-\sqrt{1-x^2}}^{\sqrt{1-x^2}} \ x \ dy \ dx 

    = \int_{x=-1}^{1} 2 \sqrt{1-x^2} \ x \ dy \ dx 

    = - \frac{2}{3} \ (1-x^2)^{3/2} \ \bigg |_{-1}^1 

At both bounds, :math:`1-x^2 = 0`, so the whole thing is :math:`0`.
