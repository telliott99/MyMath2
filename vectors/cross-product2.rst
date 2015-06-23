.. _cross-product2:

####################
Cross Product:  more
####################

===============
Triple products
===============

Suppose we have

.. math::

    \mathbf{a} = \ \langle p,q,r \rangle

    \mathbf{b} = \ \langle s,t,u \rangle

    \mathbf{c} = \ \langle x,y,z \rangle

And

.. math::

    \mathbf{a} \times \mathbf{b} =  \ \langle qu-rt, rs-pu, pt-qs \rangle

    \mathbf{b} \times \mathbf{c} =  \ \langle tz-uy, ux-sz, sy-tx \rangle

    \mathbf{a} \times \mathbf{c} =  \ \langle qz-ry, rx-pz, py-qx \rangle

Algebraically

.. math::

    \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = p(tz-uy) + q(ux-sz) + r(sy-tx)

    \mathbf{b} \cdot (\mathbf{c} \times \mathbf{a}) = s(ry-qz) + t(pz-rx) + u(qx-py)

    \mathbf{c} \cdot (\mathbf{a} \times \mathbf{b}) = x(qu-rt) + y(rs-pu) + z(pt-qs)

So

.. math::

    \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = \mathbf{b} \cdot (\mathbf{c} \times \mathbf{a}) = \mathbf{c} \cdot (\mathbf{a} \times \mathbf{b})

The way to remember this is that these are all the same cyclic permutation.

A much simpler proof is to remember that the cross-product :math:`\mathbf{a} \times \mathbf{b}` is the area of the parallelogram formed by :math:`\mathbf{a}` and :math:`\mathbf{b}` and the *scalar* triple product is the signed volume of the parallelepiped formed by the three vectors. 

"Signed" means that :math:`\mathbf{c} \cdot (\mathbf{a} \times \mathbf{b}) = -\mathbf{c} \cdot (\mathbf{b} \times \mathbf{a})` so the area may come out negative, if we order :math:`\mathbf{a}` and :math:`\mathbf{b}` differently.

.. image:: /figs/ppd_volume.png
   :scale: 50 % 

Recall that the direction of :math:`\mathbf{a} \times \mathbf{b}` is perpendicular to both vectors.   If we are careful to write the cross-product in the correct order using the right-hand rule, the result of the dot product will always be positive, with the projection of :math:`\mathbf{c}` onto the cross-product equal to the height of the solid.  In particular, for this arrangement, we must write one of these three expressions:  :math:`\mathbf{a} \times \mathbf{b}`, :math:`\mathbf{b} \times \mathbf{c}`, or :math:`\mathbf{c} \times \mathbf{a}`.

It doesn't matter which two vectors we choose as the base of our solid, the volume has to come out the same.

.. math::

    \mathbf{a} \cdot (\mathbf{b} \times \mathbf{c}) = \mathbf{b} \cdot (\mathbf{c} \times \mathbf{a}) = \mathbf{c} \cdot (\mathbf{a} \times \mathbf{b})

The other triple product is

.. math::

    \mathbf{a} \times (\mathbf{b} \times \mathbf{c})

The components are, in order,

.. math::

    q(sy-tx) - r(ux-sz)

    r(tz-uy) - p(sy-tx)

    p(ux-sz) - q(tz-uy)

"BACK CAB"

.. math::

    = \mathbf{b} (\mathbf{a} \times \mathbf{c}) - \mathbf{c} (\mathbf{a} \times \mathbf{b})

needs more work

===========================
Kepler and time-derivatives
===========================

In analysis of Kepler's laws, the vectors that we are thinking about are special because those vectors (and their components) are functions of time.  In this work, we will need the time derivative of a cross-product.

For example,

.. math::

    \mathbf{r}(t) = \langle x(t), y(t), z(t) \rangle

At any particular time :math:`t`, we get three numbers, and :math:`\mathbf{r}` reduces to a vector of the familiar type.  We should keep this in mind, it's why it makes sense to take the derivative with respect to time of :math:`\mathbf{r}`, but we will drop the :math:`(t)` to make the notation simpler.

.. math::

    \mathbf{r} = \langle x, y, z \rangle

A second simplification to the notation is to use the dot notation to denote the time derivative, which we do term by term in the vector.  For example:

.. math::

    \mathbf{v} = \frac{d}{dt} \mathbf{r} =  \dot{\mathbf{r}} = \langle  \dot{x},\dot{y},\dot{z} \rangle

So now we want to compute 

.. math::

    \frac{d}{dt} (\mathbf{r} \times \mathbf{v}) =  \frac{d}{dt} (\mathbf{r} \times \dot{\mathbf{r}} )

Set up the matrix as before

.. math::

    \begin{bmatrix} 
      \mathbf{\hat{i}}  &  \mathbf{\hat{j}}  &  \mathbf{\hat{k}} \\
      x  &  y & z \\
      \dot{x}  &  \dot{y} & \dot{z}
    \end{bmatrix}

and compute the "determinant."

.. math::

    (y \dot{z} - \dot{y} z) \hat{\mathbf{i}}  + (\dot{x}z - x\dot{z} )  \hat{\mathbf{j}}  + (x \dot{y} - \dot{x} y)  \hat{\mathbf{k}}

The critical step is to now compute the time-derivative, but we just follow our rules.  First, we go through the vector one component at a time.  For each component we have two terms, and each term is the product of two ordinary functions.  So we use the standard product rule, and obtain

.. math::

    \frac{d}{dt} (\mathbf{r} \times \dot{\mathbf{r}} ) = \frac{d}{dt} \ [ \ (y \dot{z} - \dot{y} z) \hat{\mathbf{i}}  + (\dot{x}z - x\dot{z} )  \hat{\mathbf{j}}  + (x \dot{y} - \dot{x} y)  \hat{\mathbf{k}} \ ]

    = (\dot{y} \dot{z} + y \ddot{z} - \ddot{y} z - \dot{y}\dot{z}) \hat{\mathbf{i}} 
    
    + (\ddot{x}z + \dot{x} \dot{z} - \dot{x}\dot{z} - x\ddot{z}) \hat{\mathbf{j}} 

    + (\dot{x} \dot{y} + x \ddot{y} - \ddot{x} y - \dot{x}\dot{y}) \hat{\mathbf{k}}
  
Notice that each component has two terms that cancel.  If you set up the matrix you will see that these are the terms that arise from :math:`\dot{\mathbf{r}} \times \dot{\mathbf{r}}`.  The terms that remain are then

.. math::

    = (y \ddot{z} - \ddot{y} z) \hat{\mathbf{i}} 
    
    + ( \ddot{x}z - x\ddot{z}) \hat{\mathbf{j}} 
    
    + ( x \ddot{y} - \ddot{x} y) \hat{\mathbf{k}}

(Being careful with the sign on the :math:`\hat{\mathbf{j}}` component)

I hope you will recognize that as resulting from :math:`\mathbf{r} \times \ddot{\mathbf{r}}`.  In summary, by going through term by term, we have shown that

.. math::

    \frac{d}{dt} (\mathbf{r} \times \dot{\mathbf{r}} ) = \mathbf{r}\times \ddot{\mathbf{r}} + \dot{\mathbf{r}} \times \dot{\mathbf{r}}  
    
    =  \mathbf{r}\times \ddot{\mathbf{r}}

which makes sense since any vector's cross product with itself is zero.

================================
Product rule for the dot product
================================

Going back to differentiation, it's worth mentioning that this is also true for the dot product:

.. math::

    \frac{d}{dt} (\mathbf{u} \cdot \mathbf{v}) = \dot{\mathbf{u}}  \cdot \mathbf{v} + \mathbf{u} \cdot \dot{\mathbf{v}}

As before, the components are

.. math::

    \mathbf{u} = \langle p,q,r \rangle

    \mathbf{v} = \langle x,y,z \rangle

    \mathbf{u} \cdot \mathbf{v} = px + qy + rz

By the standard product rule, the time-derivative is

.. math::

    \frac{d}{dt} (\mathbf{u} \cdot \mathbf{v}) = \dot{p}x + x \dot{p} + \dot{q}y + q \dot{y} + \dot{r}z + r \dot{z}

    = (\dot{p}x + \dot{q}y + \dot{r}z) + (x \dot{p} + q \dot{y} + r \dot{z})

    = (\dot{\mathbf{u}}  \cdot \mathbf{v}) + (\mathbf{u} \cdot \dot{\mathbf{v}})
