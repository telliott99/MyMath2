.. _cross-product:

#############
Cross Product
#############

Suppose we have two vectors :math:`\mathbf{a}` and :math:`\mathbf{b}`.  These must be in :math:`\mathbb{R}3` because the cross-product is only defined for vectors in :math:`\mathbb{R}3`.

We write the cross-product as

.. math::

    \mathbf{a} \times \mathbf{b} = \mathbf{w}

The simple part of the definition is that the magnitude of :math:`\mathbf{w}` is 

.. math::

    |\mathbf{w}| = |\mathbf{a}| |\mathbf{b}| \sin \theta

The symmetry with the dot product is obvious.

If you look at these two vectors :math:`\mathbf{a}` and :math:`\mathbf{b}`, where the angle between them is :math:`\theta`:

.. image:: /figs/dot2.png
   :scale: 50 % 

we can see that the part of :math:`\mathbf{b}` which is perpendicular to :math:`\mathbf{a}` is :math:`|\mathbf{b}| \sin \theta` which, multiplied by :math:`|\mathbf{a}|`, is equal to the area of the parallelogram formed by :math:`\mathbf{a}` and :math:`\mathbf{b}`, and is twice the area of the triangle formed by them.  This is the geometric meaning of the magnitude of the cross-product.

.. math::

    A_{\text{parallelogram}}= |\mathbf{a} \times \mathbf{b}| = |\mathbf{a}| |\mathbf{b}| \sin \theta

However, the cross product is *defined* to be a vector.

The direction of the vector is orthogonal to the plane which contains both :math:`\mathbf{a}` and :math:`\mathbf{b}`, and its sign is given by the right-hand rule.  Curl the fingers of your right hand around in the direction from :math:`\mathbf{a}` to :math:`\mathbf{b}`.  Your thumb points in the direction of :math:`\mathbf{w}`.

=====================
Dot and Cross product
=====================

Let's just look at the dot product again:

.. math::

    \mathbf{a} \cdot \mathbf{b} = |\mathbf{a}| |\mathbf{b}| \cos \theta
    
We said that the cross product is:

.. math::

    \mathbf{a} \times \mathbf{b} = |\mathbf{a}| |\mathbf{b}| \sin \theta
    
Do you see it?

We have :math:`\sin \theta` and :math:`\cos \theta` and the same coefficients so of course:

.. math::

    (\mathbf{a} \times \mathbf{b})^2 + (\mathbf{a} \cdot \mathbf{b})^2 = |\mathbf{a}|^2 |\mathbf{b}|^2 \sin^2 \theta + |\mathbf{a}|^2 |\mathbf{b}|^2 \cos^2 \theta

    (\mathbf{a} \times \mathbf{b})^2 + (\mathbf{a} \cdot \mathbf{b})^2 = |\mathbf{a}|^2 |\mathbf{b}|^2

We will use this identity below.

===========
Computation
===========

The term :math:`\sin \theta` means that the cross-product of any vector with itself is zero.

.. math::

    \mathbf{a} \times \mathbf{a} = \mathbf{0}

To make the notation simpler, we define

.. math::

    \mathbf{u} = \langle p,q,r \rangle

    \mathbf{v} = \langle x,y,z \rangle

and in order to compute the cross product, we form what looks like a really weird matrix

.. math::

    \begin{bmatrix} 
      \mathbf{\hat{i}}  &  \mathbf{\hat{j}}  &  \mathbf{\hat{k}} \\ 
      p  &  q & r \\
      x  &  y & z
    \end{bmatrix}

and calculate its "determinant"

.. math::

    \mathbf{u} \times \mathbf{v}  = (qz - ry) \ \hat{\mathbf{i}} + (rx - pz) \  \hat{\mathbf{j}}  + (py - qx) \ \hat{\mathbf{k}}

We can easily verify one of its properties by showing that the resulting vector is orthogonal to the two starting vectors, :math:`\mathbf{u}` and :math:`\mathbf{v}`.  

Test that by forming the dot product with :math:`\mathbf{u}`.

.. math::

    \mathbf{u} \cdot (\mathbf{u} \times \mathbf{v})  =  p(qz - ry) + q(rx - pz)   + r(py - qx)

The first and fourth terms cancel, the second and fifth terms cancel, and the third and sixth terms also cancel.  

So :math:`\mathbf{u} \cdot (\mathbf{u} \times \mathbf{v}) = 0`, and :math:`\mathbf{v} \cdot (\mathbf{u} \times \mathbf{v}) = 0` as well.  

In fact, we use the cross-product to find the normal vector a plane in vector calculus.

As an aside, we could have skipped this calculation.  The following rule holds for vectors:

.. math::

    \mathbf{a} \cdot ( \mathbf{b} \times \mathbf{c} ) = ( \mathbf{a} \times \mathbf{b} ) \cdot \mathbf{c}

(we will explore triple products :ref:`here <cross-product2>`).

So

.. math::

    \mathbf{u} \cdot (\mathbf{u} \times \mathbf{v}) = (\mathbf{u} \times \mathbf{u}) \cdot \mathbf{v} = 0
    
because :math:`\mathbf{u} \times \mathbf{u} = \mathbf{0}`,

and

.. math::

    \mathbf{v} \cdot (\mathbf{u} \times \mathbf{v}) = - \mathbf{v} \cdot (\mathbf{v} \times \mathbf{u}) = - (\mathbf{v} \times \mathbf{v}) \cdot \mathbf{u}) = 0

=================
Area in the plane
=================

We can also use the cross-product to find the area of the parallelogram formed by two vectors in the plane (:math:`\mathbb{R}2`).  We do this by writing vectors in :math:`\mathbb{R}3` that have :math:`0` for the :math:`z`-component:

.. math::

    \mathbf{a} = \langle a_x, a_y, 0 \rangle

    \mathbf{b} = \langle b_x, b_y, 0 \rangle
    
    A = |\mathbf{a}| |\mathbf{b}| \sin \theta

This is a nice simple expression except that it seems we have no easy way to calculate :math:`\sin \theta`.

However, for these two vectors, :math:`\mathbf{a} \times \mathbf{b}` is particularly simple

.. math::

    = a_x b_y - a_y b_x
    
If you recall the identity we found above:

.. math::

    (\mathbf{a} \times \mathbf{b})^2 + (\mathbf{a} \cdot \mathbf{b})^2 = |\mathbf{a}|^2 |\mathbf{b}|^2

we find that the area squared is equal to 

.. math::

    A^2 = |\mathbf{a}|^2 |\mathbf{b}|^2 - (\mathbf{a} \cdot \mathbf{b})^2
    
    = (a_x^2 + a_y^2)(b_x^2 + b_y^2) - (a_x b_x + a_y b_y)^2
    
    = a_x^2 b_x^2 + a_x^2 b_y^2 + a_y^2 b_x^2 + a_y^2 b_y^2 - a_x^2 b_x^2 - 2 a_x b_x a_y b_y - a_y^2 b_y^2
    
    =  a_x^2 b_y^2 + a_y^2 b_x^2 - 2 a_x b_x a_y b_y
    
    = (a_x b_y - a_y b_x)^2

which checks.
