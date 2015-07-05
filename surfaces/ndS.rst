.. _ndS:

#############
N ds six ways
#############

In the :math:`xy`-plane things are really easy.  The normal vector points straight up.  It is :math:`\hat{\mathbf{k}}` or

.. math::

    \hat{\mathbf{n}} = \  \langle 0,0,1 \rangle 

Similarly, the surface element is just :math:`dA`, so we have

.. math::

    \hat{\mathbf{n}} \ dS = \  \langle 0,0,1 \rangle  \ dx \ dy 

========
Cylinder
========

On the surface of a cylinder the normal vector points straight out (no :math:`z` component).  If we look down from the top at the circular cross-section, the normal vector points out with components

.. math::

    \mathbf{n} =  \langle x,y,0 \rangle 

The length of :math:`\mathbf{n}` is :math:`a`, the radius of the cylinder, so

.. math::

    \hat{\mathbf{n}} = \frac{1}{a} \  \langle x,y,0 \rangle 

The surface area element in the vertical direction is just :math:`\Delta z`, while in the horizontal direction it is :math:`r` or :math:`a` times :math:`\Delta \theta`, thus

.. math::

    \Delta S = a \ \Delta \theta \ \Delta z 

    dS = a \ d \theta \ dz 

    \hat{\mathbf{n}} \ dS = \  \langle x,y,0 \rangle  \ d \theta \ dz 

Although it seems weird to mix :math:`x,y` with :math:`\theta`, the idea is to keep things like this until we do the dot product with the field as will usually happen.

======
Sphere
======

On the surface of a sphere, the normal vector again points straight out.  It is

.. math::

    \mathbf{n} =  \langle x,y,z \rangle 

as we've seen before.  If the sphere has radius :math:`a`, then the length of :math:`\mathbf{n}` is :math:`a`, and

.. math::

    \hat{\mathbf{n}} = \frac{1}{a} \  \langle x,y,z \rangle 

The surface of the sphere is parametrized by just :math:`\phi` and :math:`\theta` (no :math:`r` since it is fixed :math:`r=a`).  Looking down at the horizontal circular cross-section for a given :math:`\phi`, the radius of that circle is :math:`a \sin \phi`, so the horizontal component of the surface area element is :math:`a \sin \phi \ \Delta \theta`.  The vertical component is a great circle (radius :math:`r = a`), so its length is just :math:`a \ \Delta \phi`.

.. math::

    \Delta S = a^2 \ \sin \phi \ \Delta \phi \ \Delta \theta 

    dS = a^2 \ \sin \phi \ d \phi \ d \theta 

    \hat{\mathbf{n}} \ dS = a \  \langle x,y,z \rangle   \ \sin \phi \ d \phi \ d \theta 

===================
Graph of a function
===================

If our surface is the graph of a function :math:`g(x,y)` then we can just remember the formula

.. math::

    \hat{\mathbf{n}} \ dS = \  \langle -f_x,-f_y,1 \rangle  \ dx \ dy  

If we forget and need to work it out, the deal is that we get a linear approximation to the plane surface using :math:`f_x` and :math:`f_y` so that

.. math::

    \mathbf{r_x} =  \langle 1,0,f_x \rangle

    \mathbf{r_v} =  \langle 0,1,f_y \rangle 

The cross-product :math:`\mathbf{r_x} \times \mathbf{r_v}` gives

.. math::

    \mathbf{n} = \  \langle -f_x,-f_y,1 \rangle

The length of this is

.. math::

    |\mathbf{n}| = \sqrt{f_x^2 + f_y^2 + 1}

so

.. math::

    \hat{\mathbf{n}} = \frac{\mathbf{n}}{|\mathbf{n}|} = \ \frac{ \langle -f_x,-f_y,1 \rangle}{\sqrt{f_x^2 + f_y^2 + 1}}  

However, :math:`dS` is larger than its shadow in the :math:`xy`-plane by exactly this same factor

.. math::

    dS \ \cos \theta = dA 

where

.. math::

    \cos \theta = \frac{\mathbf{n} \cdot \hat{\mathbf{k}} }{|\mathbf{n}| \ |\mathbf{k}|}=  \frac{1}{\sqrt{f_x^2 + f_y^2 + 1}} 

Hence

.. math::

    \hat{\mathbf{n}} \ dS =  \hat{\mathbf{n}} \ \frac{1}{\cos \theta} \ dA = \ \frac{ \langle -f_x,-f_y,1 \rangle}{\sqrt{f_x^2 + f_y^2 + 1}} \ \sqrt{f_x^2 + f_y^2 + 1} \ dA 

    = \  \langle -f_x,-f_y,1 \rangle  \ dA  

    = \  \langle -f_x,-f_y,1 \rangle  \ dx \ dy  

Depending on whether :math:`\mathbf{n}` points up or down we may change the sign.

==================================
Parametrization (parameterization)
==================================

More generally, we may have only a parametrization of the surface (it's not a function :math:`f(x,y)`).

.. math::

    S =
    
    x  = x(u,v)  \\

    y  = y(u,v)  \\

    z  = z(u,v)


Then

.. math::

    \hat{\mathbf{n}} \ dS = (\mathbf{r_u} \times \mathbf{r_v}) \ du \ dv 

=============
Normal vector
=============

Auroux has a last example, in which we only know a normal vector :math:`\mathbf{N}` to the surface :math:`S`.  Examples include a plane

.. math::

    ax + by + cz = d  

    \mathbf{N} = \  \langle a,b,c \rangle 

or :math:`S` is given by

.. math::

    g(x,y,z) = 0 

    \mathbf{N} = \nabla g 

Then

.. math::

    dS = \frac{1}{\cos \theta} \ dA = \frac{|\mathbf{N}|}{\mathbf{N} \cdot \hat{\mathbf{k}}} \ dA 

    \hat{\mathbf{n}} \ dS  = \frac{|\mathbf{N}| \ \hat{\mathbf{n}}}{\mathbf{N} \cdot \hat{\mathbf{k}}} \ dA 

As Auroux says, what happens if I take the unit normal :math:`\mathbf{n}`, and I multiply it by the length of my other normal :math:`|\mathbf{N}|`?  It's just :math:`\mathbf{N}`.

.. math::

    \hat{\mathbf{n}} \ dS  = \frac{\mathbf{N}}{\mathbf{N} \cdot \hat{\mathbf{k}}} \ dA
    
    = \frac{\mathbf{N}}{\mathbf{N} \cdot \hat{\mathbf{k}}} \ dx \ dy 

Again, this is "within sign", depending on how :math:`\hat{\mathbf{n}}` is oriented.

We could modify this last approach to project onto the :math:`x,z`-plane or the :math:`y,z`-plane.  In the latter case we would substitute:

.. math::
    
    \frac{\mathbf{N}}{\mathbf{N} \cdot \hat{\mathbf{i}}} \ dy \ dz

But I usually prefer to just rotate the problem so that it has the standard orientation.


