.. _Summary2:

########
Summary2
########

Stokes' theorem applies to a curve in space (it does not have to lie in a plane).  The theorem says that the work going around the curve is equal to the integral over \emph{any surface} with that curve as its boundary, of the component of the curl of :math:`\mathbf{F}` normal to the surface.

An alternative form (using the fact that :math:`\mathbf{dr} = \langle dx,dy,dz \rangle`, and computing the curl :math:`\nabla \times \mathbf{F}`) is

.. math::

    \int_C P \ dx + Q \ dy + R \ dz = \iint_R   \ <R_y-Q_z,P_z-R_x,Q_x-P_y> \  \cdot  \hat{\mathbf{n}} \ dS 

When Stokes' theorem is applied to a region in the :math:`xy`-plane, :math:`\hat{\mathbf{n}} = \hat{\mathbf{k}}`, so only the third term of the curl is non-zero, and :math:`dS = dA`.  On the left-hand side :math:`dz=0`, so this just reduces to

.. math::

    \int_C P \ dx + Q \ dy  = \iint_R \ (Q_x-P_y) \ dA 

which is Green's theorem for work.

===================
Divergence in space
===================

The last theorem is called the divergence theorem, or Gauss's theorem (and there are other names).

.. math::

    \iint_S \mathbf{F} \cdot \mathbf{n} \ dS  = \iiint_V \ \nabla \cdot \mathbf{F} \ dV 

    =  \iiint_V \ (P_x + Q_y + R_z )\ dV 

As a simple example, consider the unit sphere and a radial field :math:`\mathbf{F} = \langle x,y,z \rangle`.  We can certainly do the surface integral, but notice that :math:`\nabla \cdot \mathbf{F} = 3`.  Using the theorem, the result (the flux out of the sphere) is simply :math:`3` times the volume of the unit sphere, or :math:`4 \pi`.

=================
Other coordinates
=================

Above, in :math:`R3`, the divergence was given as

.. math::

    \iiint_V \ \nabla \cdot \mathbf{F} \ dV 

The "del" operator is

.. math::

    \nabla = \ < \frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z} > 

The divergence of :math:`\mathbf{F}` is

.. math::

    \nabla \cdot \mathbf{F} 

if :math:`\mathbf{F} = \ <P,Q,R>`

.. math::

    \nabla \cdot \mathbf{F} = P_x + Q_y + R_z 

The divergence of a vector field is a scalar quantity.

In cylindrical and spherical coordinates, the divergence is more complicated.  Although the expression above is often given as the *definition* of divergence, Schey makes a big deal out of saying that he prefers this definition

.. math::

    div \ \mathbf{F} = \lim_{\Delta V \rightarrow 0} \frac{1}{\Delta V} \iint_S \ \mathbf{F} \cdot \hat{\mathbf{n}} \ dS 

As further illustration, the divergence has a more complicated form in cylindrical and spherical coordinates.  In the former it is

.. math::

    div \ \mathbf{\mathbf{F}} = \frac{1}{r} \frac{\partial}{\partial r} (rF_r) +  \frac{1}{r} \frac{\partial}{\partial \theta} (F_{\theta}) + \frac{\partial}{\partial z} (F_z) 

where :math:`F_{z}` is not a partial derivative but just the component of :math:`\mathbf{F}` in the z-direction, and so on.

Similarly, in spherical coordinates the divergence is

.. math::

    div \  \mathbf{\mathbf{F}} = \frac{1}{r^2} \frac{\partial}{\partial r} (r^2F_r) +  \frac{1}{r \ \sin \phi} \frac{\partial}{\partial \phi} (\sin \phi F_{\phi}) + \frac{1}{r \ \sin \phi} \frac{\partial}{\partial \theta} (F_{\theta}) 

=======
Example
=======

Here is an example to explore divergence in cylindrical coordinates.  Suppose we have a cylinder oriented along the :math:`z`-axis with its length equal to :math:`1` and its radius :math:`r=2`.

Further, we have a field with some divergence, like :math:`\mathbf{F} = \langle x,y,0 \rangle`.

This field is written in :math:`x,y,z` coordinates, when we switch to cylindrical coordinates (of course) :math:`x = r \cos \theta` and :math:`y = r \sin \theta`.

We want to check the divergence theorem

.. math::

    \iint_S \mathbf{F} \cdot \mathbf{n} \ dS  = \iiint_V \ \nabla \cdot \mathbf{F} \ dV 

(The integral above is an integral over a closed surface, in this case, the cylinder with top and bottom included).

When we rewrite :math:`\mathbf{F}` in cylindrical coordinates, we will have

.. math::

    \mathbf{F} = \langle r, \theta, z \rangle 

The given field is independent of :math:`\theta` and :math:`z` and and since

.. math::

    r = \sqrt{x^2 + y^2} 

    \mathbf{F} = \langle r, 0, 0 \rangle 

Using the definition of divergence from above, we have

.. math::

    div \ \mathbf{\mathbf{F}} = \frac{1}{r} \frac{\partial}{\partial r} (rF_r) +  \frac{1}{r} \frac{\partial}{\partial \theta} (F_{\theta}) + \frac{\partial}{\partial z} (F_z) 

since :math:`\mathbf{F}` has no :math:`z` or :math:`\theta` component and the :math:`r` component is :math:`F_r =r` (this is \emph{not} a derivative), we have

.. math::

    div \ \mathbf{\mathbf{F}} = \frac{1}{r} \frac{\partial}{\partial r} (r^2) = 2 

So the triple integral uses the cylindrical volume element and is just

.. math::

    \int_0^{2 \pi} \ \int_0^{1} \ \int_0^2 \ 2 \ r \ dr \ dz \ d \theta  

    = \int_0^{2 \pi} \ \int_0^{1} \ [ \ r^2 \ \bigg |_0^2 \ ] \ dz \ d \theta = 8 \pi 

Notice that the value of the integral scales linearly with :math:`z` and like :math:`r^2`.

Now for the surface integral.  In standard form, the cylinder has

.. math::

    \hat{\mathbf{n}} \ dS = \langle x, y, 0 \rangle \ d \theta \ dz 

    \iint_S \mathbf{F} \cdot \mathbf{n} \ dS  = \langle x, y, 0 \rangle \cdot \langle x, y, 0 \rangle \ d \theta \ dz 

    \iint_S x^2 + y^2  \ d \theta \ dz 

    \int_0^1 \ \int_0^{2 \pi} \ r^2  \ d \theta \ dz = 2 \pi r^2 = 8 \pi 

I almost forgot the top and bottom of the cylinder.  However the flux :math:`\mathbf{F} \cdot \hat{\mathbf{n}} = 0` everywhere on these two surfaces, so the total is still just :math:`8 \pi`.
