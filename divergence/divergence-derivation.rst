.. _divergence-derivation:

##########
Derivation
##########

Following Schey's presentation in *Div, grad, curl*, we're interested in Gauss's Law, which says that:

.. math::

    \iint_S \mathbf{E} \cdot \mathbf{\hat{n}} \ dS = \frac{q}{\epsilon_0}

The surface integral of the normal component of the electric field is equal to the charge enclosed by the surface, divided by a constant.

The problem is that we don't know how to calculate this integral, except for cases with great symmetry.  For example, if our surface is a sphere with radius :math:`r`, and we have a point charge or a smaller sphere inside with an evenly distributed charge, we know that the field must be be radial.

So the dot product is just :math:`E = |\mathbf{E}|` and we have

.. math::

    \iint_S \mathbf{E} \cdot \mathbf{\hat{n}} \ dS = E \iint_S \ dS = 4 \pi r^2 E
    
and so

.. math::

    E(r) = \frac{1}{4 \pi \epsilon_0} \ \frac{q}{r^2}

Progress depends on thinking about the charge in some small volume :math:`\Delta V`, with charge density :math:`\rho`:

.. math::

    \frac{q}{\epsilon_0} = \frac{\rho \ \Delta V}{\epsilon_0}

So we can re-write Gauss's Law as

.. math::

    \lim_{\Delta V \rightarrow 0} \ \frac{1}{\Delta V} \ \iint_S \mathbf{E} \cdot \mathbf{\hat{n}} \ dS = \frac{\rho(x,y,z)}{\epsilon_0}

The left-hand side above is *by definition* the divergence of :math:`\mathbf{E}`.  

It will turn out that we can show that this integral is equal to

.. math::

    = \iiint_V \nabla \cdot \mathbf{E} \ dV

(strictly speaking, this is true only in Cartesian coordinates, the formula is a bit different for spherical and cylindrical coordinates).

We'll work on that in the rest of this section.

For generality, we switch back to using :math:`\mathbf{F}` for the field and write:

.. math::

    \text{div} \ \mathbf{F} = \lim_{\Delta V \rightarrow 0} \ \frac{1}{\Delta V} \ \iint_S \mathbf{F} \cdot \mathbf{\hat{n}} \ dS

Now, think about a small volume in space, :math:`\Delta V`, as a cube (or "cuboid").  We need to calculate :math:`\iint_S \mathbf{F} \cdot \mathbf{\hat{n}} \ dS` over all six faces of the cube.  

Let :math:`x,y,z` be the point at the center of the cube, with edge widths :math:`\Delta x,\Delta y,\Delta z`.  Let the first face :math:`S_1` be the face whose coordinates at the center are :math:`(x + \Delta x/2, y, z)`.

In this small region, :math:`\Delta V`, the orientation we've chosen for the faces means that the normal vector for this face is just :math:`\mathbf{\hat{i}}`, so the dot product with the field :math:`\mathbf{F}` is just the :math:`x`-component of the field, which Schey writes as :math:`F_x`, but we would normally write as :math:`P` where

.. math::

    \mathbf{F} = \langle P, Q, R \rangle

We have to find :math:`P` at the center of the face so we will need to evaluate:

.. math::

    P(x + \frac{\Delta x}{2},y,z)

Finally, :math:`dS` is the surface area element of the face, which in this case is :math:`\Delta y \Delta z` and so we have that the whole thing is:

.. math::

    \iint_{S_1} \ \mathbf{F} \cdot \mathbf{\hat{n}} \ dS \approx P(x + \frac{\Delta x}{2},y,z) \ \Delta y \ \Delta z

and for the face parallel to this one whose :math:`x`-coordinate is :math:`x - \Delta x` we have that

.. math::

    \iint_{S_2} \ \mathbf{F} \cdot \mathbf{\hat{n}} \ dS \approx - P(x - \frac{\Delta x}{2},y,z) \ \Delta y \ \Delta z

The sign change on :math:`P` is because the normal vector is :math:`- \mathbf{\hat{i}}`, pointing in the opposite direction.  The sum of the two integrals is 

.. math::

    \iint_{S_1 + S_2} \ \mathbf{F} \cdot \mathbf{\hat{n}} \ dS \approx P(x + \frac{\Delta x}{2},y,z) \ \Delta y \ \Delta z - P(x - \frac{\Delta x}{2},y,z) \ \Delta y \ \Delta z

If we multiply and divide on the right by :math:`\Delta x`, we end up with :math:`\Delta V = \Delta x \ \Delta y \ \Delta z` in the numerator, which we will move to the right-hand side.  We obtain

.. math::

    \frac{1}{\Delta V} \iint_{S_1 + S_2} \ \mathbf{F} \cdot \mathbf{\hat{n}} \ dS \approx \frac{P(x + \frac{\Delta x}{2},y,z) - P(x - \frac{\Delta x}{2},y,z)}{\Delta x} 

On the right-hand side, as :math:`\Delta V \rightarrow 0` *so does* :math:`\Delta x`, so that part is just the partial derivative of :math:`P`:

.. math::

    \text{div} \ \mathbf{F} = \lim_{\Delta x \rightarrow 0} \frac{P(x + \frac{\Delta x}{2},y,z) - P(x - \frac{\Delta x}{2},y,z)}{\Delta x}
    
    = \frac{\partial P}{\partial x}

We repeat the same process on the other four faces of the cube, just substituting :math:`y` or :math:`z` as appropriate.  

Adding up all six parts, in the limit as :math:`\Delta V \rightarrow 0`, the left-hand side is the divergence of :math:`\mathbf{F}`.

The right-hand side is

.. math::

    \frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}
    
    = \nabla \cdot \mathbf{F}

+++++++
Example
+++++++

Just to be clear, if 

.. math::

    \mathbf{F} = \langle P, Q, R \rangle
    
    = \langle x^2, xy, yz \rangle
    
    \nabla \cdot \mathbf{F} = 2x + x + y = 3x + y

And going back to Gauss's Law we have that

.. math::

    \nabla \cdot \mathbf{E} = \frac{\rho}{\epsilon_0}

========================
Other coordinate systems
========================

In cylindrical coordinates, radial coordinates :math:`r,\theta` in the plane are combined with a vertical :math:`z`-coordinate.  As we've seen before, a little piece of area in the plane :math:`dA` has sides :math:`\Delta r` and :math:`r \Delta \theta`.  (:math:`\Delta \theta` is an *angle* not a *length*).

So 

.. math::

    \Delta V = r \Delta \theta \ \Delta r \ \Delta z

So when we consider the face of our cube which has its normal vector in the radial :math:`\pm r` direction, we take the :math:`r` component of :math:`\mathbf{F}` evaluated at

.. math::

    \mathbf{F}_r (r + \frac{\Delta r}{2}, \theta, z)

times the area element for that face, which is 

.. math::

    \Delta A = r \Delta \theta \ \Delta z

We multiply and divide by :math:`\Delta r` to obtain the volume element:

.. math::

    \Delta V = r \Delta \theta \ \Delta r \ \Delta z

The right-hand side is

.. math::

    F_r( r + \frac{\delta r}{2}, \theta, z) - F_r( r - \frac{\delta r}{2}, \theta, z)

In the limit as :math:`\Delta V` and :math:`\Delta r` approach zero becomes:

.. math::

    \frac{1}{r} \ \frac{\partial}{\partial r} (r F_r)

If we follow this procedure for all six faces, we will obtain:

.. math::

    \text{div} \ \mathbf{F} = \frac{1}{r} \ [ \ \frac{\partial}{\partial r} (r F_r) + \frac{\partial F_{\theta}}{\partial \theta} + \frac{\partial}{\partial z} (r F_z) \ ] 

In spherical coordinates, the divergence is

.. math::

    \text{div} \ \mathbf{F} = \frac{1}{{\rho}^2} \ \frac{\partial}{\partial \rho} ({\rho}^2 F_{\rho}) + \frac{1}{\rho \sin \phi} \ \frac{\partial}{\partial \phi} \ (\sin \phi F_{\phi}) + \frac{1}{\rho \sin \phi} \frac{\partial F_{\theta}}{\partial \theta}



    