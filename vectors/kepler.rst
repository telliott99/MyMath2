.. _kepler:

################
Kepler's 2nd Law
################

Kepler deduced three laws governing the motion of the planets around the sun.  The second one is that equal areas are "swept out" by the orbit in equal times.

.. image:: /figs/equal-areas.png
   :scale: 50 % 

Newton explained this in terms of the inverse square law for the force of gravity.

We'll try to put it in terms of vectors.  Let :math:`\mathbf{r}(t)` (or just :math:`\mathbf{r}`)  be the position vector coming from the sun to the planet and then :math:`\Delta \mathbf{r}` will be the vector in the direction of motion during a small time :math:`\Delta t`.

We want to calculate the area of the triangle with two sides :math:`\mathbf{r}` and :math:`\Delta \mathbf{r}` and whose third side is very nearly :math:`\mathbf{r}`.

By a standard application of the cross product, the area of this triangle is

.. math::

    A = \frac{1}{2} |\mathbf{r} \times \Delta \mathbf{r}|

The velocity of the planet is :math:`\Delta \mathbf{r}/\Delta t` so that

.. math::

    \Delta \mathbf{r} = \mathbf{v} \ \Delta t

Substituting, and remembering that :math:`\Delta t` is just a number, the area is

.. math::

    A = \frac{1}{2} |\mathbf{r} \times \mathbf{v}| \ \Delta t

So what Kepler's 2nd Law says is that this area is a constant, that its time-derivative is equal to zero.

Now, the orbit lies in a single plane.  The reason for this is that if we consider the plane containing :math:`\mathbf{r}` and :math:`\mathbf{v}`, the force on the planet is in the same direction as :math:`\mathbf{r}`, with reversed sign.  The force lies in the same plane, so there is no force to move the planet's orbit out of that plane.

In terms of cross products, the direction of :math:`\mathbf{n} = \mathbf{r} \times \mathbf{v}` is :math:`\perp` to the plane of motion and constant.

Does that seem reasonable?

Let's determine

.. math::

    \frac{d}{dt} \mathbf{r} \times \mathbf{v}
    
Using the dot notation

.. math::

    \frac{d}{dt} \mathbf{r} \times \mathbf{\dot{r}}

We showed :ref:`here <cross-product2>` that the derivative of a cross product follows the familiar product rule, thus:

.. math::

    \frac{d}{dt} \mathbf{r} \times \mathbf{\dot{r}} = \mathbf{\dot{r}} \times \mathbf{\dot{r}} + \mathbf{r} \times \mathbf{\ddot{r}}

But the cross product of any vector with itself is zero.  And :math:`\mathbf{\ddot{r}}` is the acceleration, which points along the line of the force, which is toward the sun.  This is exactly the opposite direction from :math:`\mathbf{r}`.  

So :math:`\mathbf{r}` and :math:`\mathbf{\ddot{r}}` point in the same direction (within sign) and their cross product is therefore zero.  So the whole thing is zero, and the law is proved. 









