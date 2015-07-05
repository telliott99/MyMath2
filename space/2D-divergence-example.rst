.. _2D-divergence-example:

##################
Divergence example
##################

Verify the divergence theorem for a hemisphere of radius :math:`a` with :math:`\mathbf{F} = \langle x,y,z \rangle`.

Restate the theorem

.. math::

    \iint_S \ \mathbf{F} \cdot \hat{\mathbf{n}} \ dS = \iiint_D \ \nabla \cdot \mathbf{F} 

Noting that the field is given in :math:`x,y,z`-coordinates, recall that

.. math::

    \hat{\mathbf{n}} \ dS = a^2 \ \langle x,y,z \rangle   \ \sin \phi \ d \phi \ d \theta 

So on the left side

.. math::

    \mathbf{F} \cdot \hat{\mathbf{n}} \ dS = \langle x,y,z \rangle \cdot a^2 \langle x,y,z \rangle = a^3  

and

.. math::

    = \iint_S a^3  \ \sin \phi \ d \phi \ d \theta 

    = \int_S a^3  \ [ \ - \cos \phi \ \bigg |_0^{\pi/2}  \ ] \ d \theta 

    = \int_S a^3  \ d \theta  = 2 \pi a^3 

Don't forget the bottom surface.  In this problem, there is a component of the field in the :math:`z` direction

.. math::

    \mathbf{F} \cdot \hat{\mathbf{n}} \ dS =  \langle x,y,z \rangle \cdot  \langle 0,0,-1 \rangle \ dx \ dy = -z \ dx \ dy

however, the value of this field on the :math:`xy`-plane is :math:`z=0` so there is no flux.

For the divergence,

.. math::

    \nabla \cdot \mathbf{F} = 1 + 1 + 1 = 3 

which is pretty easy!.  Now, integrate

.. math::

    \iiint_D \ 3 \ dV 

Well, the volume is :math:`\frac{2}{3} \pi a^3` so we obtain :math:`2 \pi a^3`.

===========
Osu example
===========

A problem from OSU asks us to verify the divergence theorem for

.. math::

    \mathbf{F} = \ \langle y,x,z \rangle 

where the region is

.. math::

    0 \le z \le 16 -x^2 -y^2 

The graph of :math:`z=16 -x^2 -y^2` is a paraboloid which opens downward and has its vertex at :math:`z=16`.  When :math:`z=0` we have a circle of radius :math:`r=4`.

Recall that

.. math::

    \hat{\mathbf{n}} \ dS = \langle -f_x,-f_y,1 \rangle  \ dA 

so for this paraboloid surface we have

.. math::

    z = f(x,y) = 16 - x^2 - y^2 

    \hat{\mathbf{n}} \ dS = \ \langle 2x,2y,1 \rangle  \ dA 

This corresponds to :math:`\hat{\mathbf{n}}` pointing out of the surface.

Then

.. math::

    \iint_S \mathbf{F} \cdot \hat{\mathbf{n}} \ dS  = \iint_R 4xy + z \ dA 

    =  \int_{-4}^{4} \int_{-\sqrt{16-y^2}}^{\sqrt{16-y^2}} \ 4xy + 16 - x^2 - y^2 \ dx \ dy 

:math:`xy`-coordinates are not a good way to do this problem.  Convert to polar coordinates

.. math::

    x = r \cos \theta 

    y = r \sin \theta 

    dA = r \ dr \ d\theta 

    \iint_R (4r^2 \sin \theta \cos \theta + 16 - r^2) \ r \ dr \ d\theta 

The region of integration is the disk of radius :math:`r=4`

.. math::

    \int_0^{2\pi} \ \int_0^4 \ (4 r^2 \sin \theta \cos \theta + 16 - r^2) \ r \ dr \ d \theta 

The inner integral is

.. math::

    \int_0^4 \ 4 r^3 \sin \theta \cos \theta + 16r - r^3 \ dr 

    r^4  \sin \theta \cos \theta + 8r^2 - \frac{1}{4}r^4 \ \bigg |_0^4 

    = 256   \sin \theta \cos \theta + 128 - 64 

    = 256   \sin \theta \cos \theta + 64 

The outer integral is

.. math::

    \int_0^{2\pi} 64 +  256  \sin \theta \cos \theta \ d \theta 

    = 128 \pi + 256 \sin^2 \theta \bigg |_0^{2\pi} 

    = 128 \pi  

There is another part of our solid.  That is the disk in the :math:`xy`-plane.  For this disk, the unit normal (pointing out) is just :math:`\langle 0,0,-1 \rangle`.

.. math::

    \iint_S \mathbf{F} \cdot \hat{\mathbf{n}} \ dS  = -\iint_R z \ dA 

but remember that we're on the :math:`xy`-plane so :math:`z=0` and the whole integral is :math:`0`.

We're not done yet!  We still have to compute

.. math::

    \iiint_R \ \nabla \cdot \mathbf{F} 

    = \iiint_R P_x + Q_y + R_z \ dV 

since :math:`\mathbf{F} = \ \langle y,x,z \rangle` this is just equal to :math:`3`.  So we need

.. math::

    3 \iiint_R  \ dV 

If we convert to cylindrical coordinates, we will integrate over the disk of radius :math:`r=4`.  What is the upper bound on :math:`z`?

.. math::

    z = 16 - x^2 - y^2 = 16 - r^2 

So we have

.. math::

    \int_0^{2\pi} \ \int_0^4 \ \int_0^{16 - r^2} \ dz \ r \ dr \ d \theta 

The inner integral is just :math:`16 - r^2`.  The middle integral is

.. math::

    \int_0^4 16r - r^3 \ dr 

    = 8r^2 - \frac{1}{4}r^4 \ \bigg |_0^4 

    = 128 - 64 = 64 

Finally, we pick up :math:`2 \pi` from the outer integral for a final result of :math:`128 \pi`, which matches what we had above.
